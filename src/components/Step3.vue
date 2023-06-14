<template>
  <div class="Step3">
    <h3>Step-3</h3>

  </div>

</template>


<style scoped>
  .Step3 {
    background-color: #84e359;
    height: 400px;
    width: 500px;
    margin: 30px;
    padding: 20px;
  }
</style>

<script>
export default {

  props: {

  },

  // получение методов из родительского компонента
  emits: [],

  data() {
    return {

    }
  },

  methods: {

  }
}

// массив с именами
const names = ['Вася', 'Петя', 'Маша'];

// пройдем по массиву, выведем каждый элемент
names.forEach(function(item, index) {
  console.log( item + ' имеет позицию ' + index );
});


// объект с 3 автомобилями
const cars = {
  'Audi': 2015,
  'BMW': 2018,
  'Ford': 2010
};

// пройдем по объекту, выведем каждый элемент
for (let key in cars) {
  console.log( key + ' имеет позицию ' + cars[key] );
}

</script>