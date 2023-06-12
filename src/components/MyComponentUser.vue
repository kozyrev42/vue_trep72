<script>

// импортируем компонент
import Dochernii3 from './Dochernii3.vue';
import Employee  from './Employee.vue';


export default {

  components: {
    Dochernii3,
    Employee
  },

  data() {
    return {
      name: 'aleksandr',
      profession: 'программист',
      myObjectCar: {
        brand: 'toyota',
        model: 'corolla'
      },
      employees:[
        {
          id: 1,
          name: 'name1',
          salary: 100,
          age: 30,
        },
        {
          id: 2,
          name: 'name2',
          salary: 200,
          age: 40,
        },
        {
          id: 3,
          name: 'name3',
          salary: 300,
          age: 50,
        },
      ],
    }
  },

  methods: {
    functionHelloMyComponentUser() {
      alert('привет из MyComponentUser');
    },

    outputInConsole(argument1) {
      console.log(argument1);
    }
  },



}

</script>


<template>
  <div class="MyComponentUser">
    <h1>MyComponentUser</h1>
    <p>{{ name }}</p>

    <!-- // передаем данные в компонент, где будем принимать их через "props" -->
    <!-- @show="functionHelloMyComponentUser" // передача метода в дочерний компонент   -->
    <Dochernii3
        :name="name"
        :profession="profession"
        :myObjectCar="myObjectCar"
        @showHello="functionHelloMyComponentUser"
        @outputInConsoleParent="outputInConsole"
    />


    <!--  // в цикле выведем компонент "Employee", передавая в него данные-->
    <!--  // компонент выведется столько раз, сколько объектов в массиве "employees"-->
    <Employee v-for="employee in employees" :key="employee.id" :employee="employee"/>

  </div>




</template>


<style scoped>
  .MyComponentUser {
    background-color: #c9ee48;
    /*// высота блока*/
    height: 1000px;
  }


</style>