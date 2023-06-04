<script>
// import HelloWorld from './components/HelloWorld.vue'
// import TheWelcome from './components/TheWelcome.vue'
export default {
  // name: 'App', // имя компонента
  name: 'App',

  // data() - это функция, которая возвращает объект
  // в этом объекте мы можем хранить свойства, которые будут доступны в шаблоне
  // в шаблоне мы можем обращаться к свойствам через {{ свойство }}
  // в шаблоне мы можем обращаться к методам через @click="метод"
  // в шаблоне мы можем обращаться к вычисляемым свойствам через {{ вычисляемое_свойство }}
  // в шаблоне мы можем обращаться к условиям через v-if="условие"
  // в шаблоне мы можем обращаться к циклам через v-for="элемент in массив"
  // в шаблоне мы можем обращаться к директивам через v-директива
  // в шаблоне мы можем обращаться к директивам через v-директива="значение"
  // в шаблоне мы можем обращаться к директивам через v-директива:модификатор="значение"

  data() {
    return {
      // свойства для шаблона (выводятся через {{ свойство }})
      // свойства можно использовать в шаблоне, в вычисляемых свойствах и в методах
      // свойства можно изменять в методах
      // свойства можно изменять в вычисляемых свойствах

      text: 'page',
      hrefMy: 'page.html',

      num1: 4,
      num2: 5,

      myArray: [111, 222, 333],

      myObject: {a: 111, b: 222, c: 333},

      visible: true,

      isAuth: false,

      message: 'message: hello!',

      numberPreview: 0,

      numberPreviewSquare: 0,

      numberSquare: 0,

      checked: true,

      // массив для хранения значений чекбоксов
      checkedArray: [],

      // свойство для хранения значения радиокнопки
      radioValue: '',

      // свойство для хранения значения селекта
      selectedCar: '',

      // массив для хранения значения селекта
      animals : [
        'cat',
        'dog',
        'cow',
      ],

      // свойство для хранения выбора юзера
      agree: false,

      // массив хранит буквы
      letters: ['a', 'b', 'c', 'd', 'e', 'f'],
      newLetter: '',



      // массив объектов
      // в шаблоне выводим через {{ user.name }}
      users: [
        {
          id: 1,
          name: 'name1',
          surname: 'surname1',
        },
        {
          id: 2,
          name: 'name2',
          surname: 'surname2',
        },
        {
          id: 3,
          name: 'name3',
          surname: 'surname3',
        },
      ],

      // свойство хранит 2 css класса
      classesRedBold: 'myRed myBold',

      // Объект с CSS классами предназначен для того, чтобы удобно было реактивно назначать классы элементам
      objectClasses: {
        done: true,         // класс применится
        selected:  false,   // класс не применится
      },

      // объект хранит свойство, через имя которого к тегу будет подставляться css-класс !!!
      stylesObj: {
        //
        myRed: false,
      },

    }
  },

  // в "computed" храняться вычисляемые свойства
  // вычисляемые свойства - это свойства, которые зависят от других свойств
  computed: {
    // вычисляемое свойство
    // в шаблоне выводим через {{ numSum }}
    // вычисляемое свойство не принимает параметров
    // вычисляемое свойство не принимает аргументов
    numSum: function () {
      return this.num1 + this.num2;
    },

  },

  // в "methods" храняться методы
  // методы - это функции, которые можно вызывать в шаблоне
  // методы можно вызывать в шаблоне через @click="метод(аргумент)"
  // методы можно вызывать в шаблоне через @click="метод(свойство)"
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

    setRed: function () {
      // обращаемся к свойству объекта
      this.stylesObj.myRed = true;
    },

    noRed: function () {
      // обращаемся к свойству объекта
      this.stylesObj.myRed = false;
    },

    getNumberSquare: function () {
      this.numberSquare = this.numberPreviewSquare ** 2;
    },

    addLetter: function () {
      // добавляем букву в массив
      this.letters.push(this.newLetter);
    },

    removeLetter: function (index) {
      // удаляем букву из массива
      this.letters.splice(index, 1);
    },

    removeUser: function (id) {
      // удаляем юзера из массива
      this.users = this.users.filter((user) => {
        return user.id !== id;
      });
    },
  }
}

</script>


<template>
  <!-- формирование ссылки в атребуте -->
  <a v-bind:href="hrefMy">{{ text }}</a>


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
  <!-- v-on: и @: - равнозначны -->
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
  <hr>

  <!-- Циклы -------------------------------------------------------------------------------------- -->
  <h5>Циклы</h5>

  <!-- вывод элементов массива -->
  <p v-for="elem in myArray">
    {{ elem }}
  </p>

  <!-- вывод элементов объекта с ключами -->
  <p v-for="(elem, key, index) in myObject">
    индекс: {{ index }}, ключ: {{ key }} >> значение: {{ elem }}
  </p>
  <hr>

  <!-- перебор массива объектов -->
  <!-- чтобы переиспользовать и упорядочивать существующие элементы, необходимо указать уникальный атрибут key -->
  <h5> перебор массива объектов: </h5>
  <p v-for="user in users" :key="user.id">
    {{ user.name }}
    {{ user.surname }}
  </p>
  <hr>

  <!-- использование условия в цикле -->
  <h5> использование условия в цикле: рендер тех элементов, которые делятся на 2, без остатка </h5>
  <ul v-for="elem in myArray">
    <li v-if="elem % 2 === 0">
      {{ elem }}
    </li>
  </ul>
  <hr>
  <hr>

  <h1> Применение стилей</h1>
  <div>
    <p :class="classesRedBold">применение стилей через свойство</p>

    <p :class="objectClasses">применение объекта с классами</p>
    <hr>

    <p :class="stylesObj">"ТЕКСТ"</p>
    <button @click="setRed">покрасить ТЕКСТ в красный, через свойство объекта</button> <br>
    <button @click="noRed">вернуть исходный цвет ТЕКСТА, через свойство объекта</button>

    <p :style="{color: 'green', 'font-size': '24px'}">
      стили прописаны в теге
    </p>
  </div>
  <hr>
  <hr>


  <h1>Формы</h1>
  <!-- //  input связан с переменной "message", с помощью директивы v-model -->
  <input v-model="message">

  <!--  // выводим значение переменной "message"-->
  <p>выводим значение переменной "message": {{ message }}</p>

  <!--// выводим значение переменной "message", в верхнем регистре-->
  <p>выводим значение переменной "message", в верхнем регистре: {{ message.toUpperCase() }}</p>
  <hr>

  <!--// ввод числа, для получения квадрата числа-->
  <input v-model.number="numberPreview">
  <p>квадрат числа: {{ numberPreview * numberPreview }}</p>
  <hr>


  <p>по нажатию на кнопку выведем квадрат введенного в инпут числа</p>
  <!-- // примаем данные из инпута -->
  <input v-model.number="numberPreviewSquare">

  <!-- // вызываем обработчик события, которые вычисляет квадрат числа -->
  <button @click="getNumberSquare">вывести квадрат числа</button>

  <!-- // выводим вычисленное значение -->
  <p>квадрат числа: {{ numberSquare }}</p>
  <hr>


  <h5>Работа с чекбоксами</h5>
  <!-- // примаем данные из инпута -->
  <input type="checkbox" v-model="checked">
  <p>значение переменной "checked": {{ checked }}</p>
  <p> чекбокс отмечен: {{ checked ? 'да' : 'нет' }}</p>
  <hr>

  <div>
  <!-- // группа чекбоксов, связанные с одной переменной "checkedArray" -->
    <input type="checkbox" id="ru" value="русский" v-model="checkedArray">русский
    <input type="checkbox" id="en" value="английский" v-model="checkedArray">английский
    <input type="checkbox" id="ger" value="немецкий" v-model="checkedArray">немецкий

    <p>значение переменной "checkedArray": {{ checkedArray }}</p>

    <p></p> выводим выбранные языки в виде списка
    <ul>
      <li v-for="lang in checkedArray">
        {{ lang }}
      </li>
    </ul>
  </div>
  <hr>


  <h5>Работа с радиокнопками</h5>
  <!--  Работа с радиокнопками происходит аналогичным образом-->
  <div>
    <input type="radio" id="bmw" value="bmw" v-model="radioValue">BMW
    <input type="radio" id="audi" value="audi" v-model="radioValue">Audi
    <input type="radio" id="mercedes" value="mercedes" v-model="radioValue">Mercedes

    <p>значение переменной "radioValue": {{ radioValue }}</p>
  </div>
  <hr>


  <h5>Работа с выпадающим списком</h5>
  <!--  Работа с выпадающим списком происходит аналогичным образом-->
  <div>
  <!--  // привязываем переменную "selectedCar" к выпадающему списку-->
    <select v-model="selectedCar">
      <option disabled value="">выберите машину</option>
      <option value="bmw">BMW</option>
      <option value="audi">Audi</option>
      <option value="mercedes">Mercedes</option>
    </select>

    <p>значение переменной "selected": {{ selectedCar }}</p>
  </div>
  <hr>

  <p>Теги option можно также создавать не в ручную, а с помощью цикла.</p>
  <div>
    <select v-model="animals">
      <option v-for="animal in animals" >
        {{ animal }}
      </option>
    </select>
  </div>
  <!--  // выведем выбранный элемент-->
  <p>выбранный элемент: {{ animals }}</p>
  <hr>


<!--    // Можно реактивно блокировать элементы формы с помощью атрибута disabled-->
  <div>
    <input type="checkbox" id="checkbox" v-model="agree">
    <label for="checkbox">согласен с условиями</label>
<!--    // если не согласен с условиями, то кнопка отправить блокируется-->
    <button v-bind:disabled="!agree">отправить</button>
  </div>
  <hr>


<!--  // Выведем содержимое массива в виде списка:-->
  <ul>
    <li v-for="(item, index) in letters" :key="index">
      {{ item }}
    </li>
  </ul>

<!--  // Давайте теперь сделаем инпут и кнопку, по нажатию на которую текст инпута добавится в конец списка в качестве нового пункта:-->
  <input type="text" v-model="newLetter">
  <button @click="addLetter">добавить</button>

<!--// Давайте сделаем кнопку реактивного удаления элементов из списка-->
  <ul>
    <li v-for="(item, index) in letters" :key="index">
      {{ item }}
      <button @click="removeLetter(index)">удалить</button>
    </li>
  </ul>
  <hr>


<!--  // Давайте сделаем кнопку реактивного удаления элементов из объекта-->
  <ul>
    <li v-for="(user, index) in users" :key="user.id">
      {{ user.name }}
      {{ user.surname}}
      <br>
      <button @click="removeUser(user.id)">удалить</button>
      <br>
<!-- редактирование -->
      <input v-model="user.name">
      <input v-model="user.surname">
      <br><br>

    </li>
  </ul>




</template>

<style>
/* стили для шаблона, будут применены только к этому шаблону */
.myRed {
   color: #ff0000;
}

.myBold {
  font-weight: bold;
}

p.done {
  text-decoration: line-through;
}

</style>
