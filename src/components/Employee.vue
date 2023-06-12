<script>
export default {

  // получаем данные из родительского компонента
  // получение "props" с указание типа данных
  props: {
    employee: Object,
  },

  data() {
    return {

    }
  }
}

</script>


<template>
  <div class="Employee">
    <!--выводим данные, полученные из родительского компонента-->
    <p>{{ employee.name }}</p>
    <p>{{ employee.salary }}</p>
    <p>{{ employee.age }}</p>
    <hr>
  </div>
</template>


<style scoped>
  .Employee {
    background-color: #d47576;
    height: 100px;
    width: 200px;
    margin: 40px;
  }


</style>