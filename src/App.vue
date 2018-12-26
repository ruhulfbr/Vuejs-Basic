<template>
  <!-- <div id="app">
    <router-view/>
  </div> -->
  <div id="app">

<h1>Form input Binding</h1>
<form method="post">
    <p>Name : <input type="text" v-model.lazy="info.name"></p>
    <p>Email : <input type="text" v-model.lazy="info.email"></p>
    <p>Phone : <input type="text" v-model="info.phone"></p>

    <p>
      <label>Developer : <input type="checkbox" v-model="info.post" value="Developer"></label>
      <label>Designer : <input type="checkbox" v-model="info.post" value="Designer"></label>
      <label>Tester : <input type="checkbox" v-model="info.post" value="Tester"></label>
      <label>CEO : <input type="checkbox" v-model="info.post" value="CEO"></label>
    </p>

    <p>
      <label><input type="radio" v-model="info.gender" value="Male">Male</label>
      <label><input type="radio" v-model="info.gender" value="Female">Female</label>
      <label><input type="radio" v-model="info.gender" value="Others">Others</label>
    </p>
    <p>
      <select v-model="info.level">
        <option v-for="level in levels">{{level}}</option>
      </select>
    </p>

    <p><button type="button" v-on:click="post()">Save Student</button></p>
</form>

<ShowBlog>
  
</ShowBlog>
<!-- <h3>Output</h3>
<p>Name : {{info.name}} </p>
<p>Email : {{info.email}}</p>
<p>Phone : {{info.phone}}</p>
<p>Gender : {{ info.gender }}</p>
<p>Employee Post :
  <ul>
    <li v-for="post in info.post">{{post}}</li>
  </ul>
</p>
<p>Level : {{info.level}}</p> -->

  <!--  <hr>  <hr>   
    <keep-alive>
      <component v-bind:is="component"></component>
    </keep-alive>
    
<br>
    <button type="button" @click="component='student-form'">Student Form</button>
    <button type="button" @click="component='employee-form'">Employee Form</button>
    <student-form></student-form><br>
    <employee-form></employee-form> -->
    <!-- <n_header></n_header>
    <h2>{{ simpleMessage }}</h2>
    <button type="button" @click="updateSimpleMessage()">Update Simple message</button>
    <n_content v-bind:students="students_info"></n_content>
    <n_students v-bind:message="msg" v-bind:students="students_info" v-on:UpdateValueVariable="UpdateFun($event)">
      <h1>{{ msg2 }}</h1>
      <div slot="form-header">
          <h3>Strudent Form</h3>
      </div>
      <div slot="form-elements">
          <p>Name : <input type="text" name="name" placeholder="Student Name"></p>
          <p>Email : <input type="email" name="email" placeholder="Student Email"></p>
      </div>
      <div slot="form-button">
          <button type="button" @click="formDetails()">Submit Student</button>
      </div>
      <div slot="form-footer">
          <p>this is form Footer</p>
      </div>
    </n_students>
    <n_footer></n_footer> -->
  </div> 

</template>

<script>
  // import Header from './components/Header.vue'
  // import Content from './components/Content.vue'
  // import Footer from './components/Footer.vue'
  // import Students from './components/Students.vue'
  // import D_com_1 from './components/D_com_1.vue'
  // import D_com_2 from './components/D_com_2.vue'
  import showBlog from './components/showBlog'

export default {
  // components:{
  //   "n_header":Header,
  //   "n_content":Content,
  //   "n_students":Students,
  //   "n_footer":Footer,
  //   "student-form":D_com_1,
  //   "employee-form":D_com_2,
  // },
  components:{
    "ShowBlog":showBlog
  },
  name: 'App',
  data (){
    return{
      // msg:"Passing Data Child Component to Parent Component",
      // msg2:"passing bariable data from parent by slot",
      // simpleMessage:"This is a simple message",

      // component:"student-form",
      levels:["senior","junior","leader","motivator"],
      info:{
        name:"",
        email:"",
        phone:"",
        gender:"",
        post:[],
        level:""
        
      },

      // students_info:[
      //   {
      //     name:"Ruhul1",
      //     email:"ruhul@gmail.com-11",
      //     id:"72"
      //   },
      //   {
      //     name:"Ruhul2",
      //     email:"ruhul@gmail.com-22",
      //     id:"72"
      //   },
      //   {
      //     name:"Ruhul3",
      //     email:"ruhul@gmail.com-33",
      //     id:"72"
      //   }
      // ]
    }
  },
  // beforeCreate(){
  //   alert("Before create")
  // },
  // created(){
  //   alert("Created")
  // },
  // beforeMount(){
  //   alert("Before Mount")
  // },
  // mounted(){
  //   alert("Mounted")
  // },
  // beforeUpdate(){
  //   alert("before Update")
  // },
  // updated(){
  //   alert("Updated")
  // },


  methods:{
    post:function(){
      this.$http.post('https://jsonplaceholder.typicode.com/posts',{
        title:this.info.name,
        bosy:this.info.email + ' ' + this.info.phone + ' ' + this.info.gender,
        userId:1
      }).then(function(data){
         console.log(data);
      });
    }
    // UpdateFun(updateValue) {
    //   this.msg = updateValue
    // },
    // updateSimpleMessage(){
    //   this.simpleMessage = "Updated Simple Message"
    // }
  }
}
</script>




