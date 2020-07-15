<template>
  <div class="form-container">
    <form @submit="handleSubmit" class="form">
      <k-input v-model="email" :label="'Email'"/>
      <k-input v-model="password" type="password" :label="'Password'"/>
      <kendo-button class="k-primary">Submit</kendo-button>
    </form>
    <kendo-notification ref="popupNotification"/>
  </div>
</template>
<script>
export default {
  name: 'Form',
  data() {
    return {
      email: '',
      password: ''
    }
  },
  methods: {
    async handleSubmit(e) {
      e.preventDefault()
      let response = await fetch('https://dogz.studio/api/login', {
        method: 'POST',
        mode: 'cors', 
        headers: {
          'Content-Type': 'application/json'
        },
        body: JSON.stringify({
          email: this.email,
          password: this.password
        }) 
      }).then(res => res.json())
      this.$refs.popupNotification.kendoWidget().show(response.message)
    }
  }
  
}
</script>
<style>
  .form {
    width: 250px;
    display: flex;
    flex-direction: column;
    align-items: center;
    border-radius: 4px;
    background: #FEFEFE;
    box-shadow: 0px 0px 8px rgba(32, 37, 37, 0.15);
  }

  .form > * 
  {
    margin: 10px;
  }
</style>