<script>
// import HelloWorld from './components/HelloWorld.vue'
// import TheWelcome from './components/TheWelcome.vue'
export default {
  data() {
    return {
      text: 'page',
      href: 'page.html',

      num1: 4,
      num2: 5,

      myArray: [1, 2, 3],

      myObject: {a: 111, b: 222, c: 333},


    }
  },

  // кастомные методы
  methods: {
    myMethod: function () {
      alert(new Date());
    },

    myMethodHi: function () {
      alert(this.num1 + this.num2);
    },

    x2method: function (num) {
      return num * 2;
    },

    // вызов метода через this
    show: function () {
      alert(this.x2method(10));
    },
  }
}

</script>


<template>
  <!-- формирование ссылки -->
  <a v-bind:href="href">{{ text }}</a>


  <!-- выполнение js кода в фигурных скобках -->
  <p>суммирование свойств из 'data': {{ num1 + num2 }}</p>


  <!-- вывод из массива по индексу -->
  <p> вывод из массива:
    {{ myArray[0] }},
    {{ myArray[2] }}
  </p>

  <!-- вывод из объекта -->
  <p>вывод из объекта: {{ myObject.a }}</p>
  <p>сумма свойств объекта: {{ myObject.a + myObject.b }}</p>

  <!-- вызов метода -->
  <!-- {{ myMethod() }} -->

  <!-- вызов обработчика по клику-->
  <button v-on:click="myMethod">кнопка</button>
  <button @:click="myMethodHi">кнопка#2</button>
  <button @:click="show">кнопка#3</button>

</template>

<style>

</style>
