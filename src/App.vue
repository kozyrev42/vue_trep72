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

      visible: true,

      isAuth: false,
    }
  },

  // в "computed" храняться вычисляемые свойства
  computed: {
    numSum: function () {
      return this.num1 + this.num2;
    },

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

    showX2: function (num) {
      alert(num ** 2);
    },

    showX3: function (num) {
      alert(num ** 3);
    },

    change: function () {
      this.text = 'новый текст';
    },

    changeNum1: function () {
      this.num1 = 14;
    },

    hideText: function () {
      this.visible = false;
    },

    showText: function () {
      this.visible = true;
    },

    toggle: function () {
      this.visible = !this.visible;
    },

    auth: function () {
      this.isAuth = true;
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

  <!-- передача параметров в метод -->
  <!-- при клике вызываем метод и передаём в метод число -->
  <button @click="showX2(5)">5 в квадрате</button>
  <button @click="showX3(5)">5 в кубе</button>
  <hr>

  <!-- просто вывод свойства из data() -->
  <p>вывод свойтва из data(): {{ text }}</p>

  <!-- изменим свойство на "новый текст" -->
  <button @click="change">изменим на "новый текст"</button>

  <!-- вычисленное значение -->
  <p>вычисляемое свойство: {{ numSum }}</p>
  <button @click="changeNum1">изменить num1</button>
  <hr>
  <!-- УСЛОВИЯ ------------------------------------------------------------------------------------- -->
  <h5>УСЛОВИЯ</h5>
  <p v-if="visible">ТЕКСТ ПОКАЗАН, так как в "v-if" передано "true"</p>
  <button @click="hideText">скрыть текст</button>
  <button @click="showText">показать текст</button>
  <button @click="toggle">
    {{ visible ? 'скрыть' : 'показать' }}
  </button>

  <!-- работа директив -->
  <p v-if="isAuth">вы вошли в приложение</p>
  <p v-else>войти в приложение</p>
  <hr>

  <!-- условие для группы тегов -->
  <button @click="auth">ВХОД</button>
  <div v-if="!isAuth">
    <p>нужно войти</p>
    <p>чтобы</p>
    <p>отправить сообщение</p>
  </div>

  <!-- Циклы -------------------------------------------------------------------------------------- -->


</template>

<style>

</style>
