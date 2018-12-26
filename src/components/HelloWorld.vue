<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h2>{{ sayHello("Morning Students") }}</h2>
    <!-- <h3>{{ fullName }}</h3> -->
    <!-- <student></student>
    <employee></employee> -->

    
  </div>
</template>

<script>
  // import Employee from './Employee.vue'
    

export default {
  // components:{
  //   "employee":Employee
  // },
  // name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Code Museum'
    }
  },
  methods:{
    sayHello(dayTime){
      return "Good " + dayTime;
    }
  },
  // computed:{
  //   fullName(){
  //     return this.firstName + " " + this.lastName;
  //   }
  // }
}
</script>

