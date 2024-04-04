<script>
export default {
  data(){
    return{
      email:'',
       isEmailValid: false,
    };
  },
  methods:{
   openEmailPrompt(){
        let email = prompt('Input your email');
        if(!email){
          this.isEmailValid = false;
          return;
        }
        email = email.trim();
        this.email = email;
        console.log(email);
        const isValid = this.checkIsEmailValid(email);
        this.isEmailValid = isValid;
    },
    checkIsEmailValid(email){
      const reg = /^[\w-.]+@([\w-]+\.)+[\w-]{2,4}$/;
     return reg.test(email);
    },
    reset(){
      this.email = '';
      this.isEmailValid = false;
    }
  }
}

</script>


<template>
  <main>
  <button @click="openEmailPrompt()" class="inputEmail">Input your email</button>
  <button @click="reset()">Reset</button>
  <h1 
  :class="isEmailValid ? 'green' : 'red'"
  v-if="email"
  >{{ email }}</h1>
<h4 v-if="email">{{ `The email is ${isEmailValid ? 'valid': 'invalid'}`}}</h4>
  </main>
</template>
<style scoped>
.red{
  border: 1px solid red;
  padding:0 10px;
  border-radius: 20px;
}

.green{
  border: 1px solid green;
  padding:0 10px;
  border-radius: 20px;
}
.inputEmail{padding:10px 10px;
  margin:15px;
  font-size:20px;  
  border-radius: 15px;
  }
</style>
