
<template>
  <!-- привязка атрибутов объекта как id / можно shorthand использовать как :-->
    <div> <h1 v-bind:id="userId">lesson14</h1>
      
      <!-- вывод текста, аргумента -->
    <p>Some text text  today is {{ date }}</p>

    <!-- перенос html тегов  и отображение, сырой html -->
<p v-html="link"></p>

<!-- javascript можно но в одну строку только  -->
<p>{{ userId === 28 ? "YES":"NO" }}</p>

<!--  привязка события нажатия. можно скоратить на @click -->
<button v-on:click="changedate">поменять дату</button>

<!-- пример инлайн функции -->
<button @click="userId ++">поменять ID</button>

<!-- использования условия if else -->
<div v-if="userId ===28"> var1 </div>
<div v-else-if="userId ===29"> var2 </div>
<div v-else> var3 </div>

<!-- v-show  отображение текста по условию. по идее при исполнении он преходит в none отображеие через css -->
<div v-show="userId===29">Lorem ipsum dolor sit amet consectetur adipisicing elit. Consequatur, suscipit corporis! 
  Provident veniam architecto hic laborum qui nulla aut voluptas nihil, consequatur voluptate magnam molestias
   distinctio sapiente cum ullam ratione?</div>

   <ul>
    <!-- использование v-for для массива для отображения в списке -->
    <li v-for="fruit in fruits">{{ fruit }} </li>
   </ul>
<hr>
   
   <ul>
    <!-- использование v-for для массива для отображения в списке c Index и отображение его -->
    <li v-for="(fruit, index) in fruits" :key="index"> {{ fruit }} {{ index }}</li>
   </ul>

</div>
</template>


<script>
export default {
  data() {
    return{
      userId:28,
      
      date:"23 October",
      
      link: "<a href='google.com' target='_blank'>google</a>",

      fruits:['apple','orange','banana','melon']

    }
  },

  methods: {
    changedate(){
      this.date = "99 october"

    }
  },


  mounted(){
  console.log(1);
}


}
</script>



<style scoped>

</style>
