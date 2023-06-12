<script>
export default {

  // получаем данные из родительского компонента
  // получение "props" с указание типа данных
  props: {
    name: String,
    profession: String,
    myObjectCar: Object,
    employees: Array,
  },

  // получение методов из родительского компонента
  emits: ['showHello','outputInConsoleParent'],

  data() {
    return {

    }
  },

  methods: {
    handle() {
      // вызов метода из родительского компонента
      this.$emit('showHello');
    },

    outputInConsoleChild () {
      // первый аргумент - название события, второй - данные для передачи в родительский компонент
      this.$emit('outputInConsoleParent', 'привет из дочернего компонента');
    }
  }
}

</script>


<template>
  <div class="Dochernii3">
    <h1>Dochernii3</h1>


    <!--выводим данные, полученные из родительского компонента-->
    <p>{{ name }}</p>
    <p>{{ profession }}</p>
    <hr>


    <ul>
      <p>получение объекта из родительского компонента</p>
      <li>{{ myObjectCar.brand }}</li>
      <li>{{ myObjectCar.model }}</li>
    </ul>
    <hr>


    <!--    // выведем в цикле данные из "employees"-->
    <ul>
      <p>получение массива из родительского компонента</p>
      <li v-for="employee in employees" :key="employee.id">
        {{ employee.name }} - {{ employee.salary }} - {{ employee.age }}
      </li>
    </ul>


    <button @click="handle">вызов метода из родительского компонента</button>
    <button @click="outputInConsoleChild">вызов метода из родительского компонента</button>
  </div>

</template>


<style scoped>
  .Dochernii3 {
    background-color: #fdbf67;
    height: 400px;
    width: 500px;
    margin: 40px;
  }


</style>