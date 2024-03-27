<template>  
  <form @submit.prevent = "handleSubmit">
    <label>Title:</label>
    <input type="text" v-model="title" required>

    <label>Details:</label>
    <textarea v-model="details" cols="30" rows="10" required></textarea>

    <button>Update Project</button>
  </form>  
</template>

<script>
  export default {
    props: ['id'],
    data() {
      return {
        title: "",
        details: "",
        uri: "http://localhost:3000/projects/" + this.id,
      }
    },
    mounted() {
      fetch(this.uri)
      .then(res => res.json())
      .then(data => {
        this.title = data.title,
        this.details = data.details
      })
    },
    methods: {
      handleSubmit() {
        fetch(this.uri, {
          method: "PATCH",
          headers: {"Content-Type": "application/json"},
          body: JSON.stringify({title: this.title, details: this.details})          
        })
        .then(() => this.$router.push('/'))
        .catch(err => console.log(err))
      }
    },
  }
</script>

<style>
  form {
    background: #fff;
    padding: 20px;
    border-radius: 0.3rem;
    margin-top: 2rem;
  }
  label {
    display: block;
    color: #bbb;
    text-transform: uppercase;
    font-size: 14px;
    font-weight: bold;
    letter-spacing: 1px;
    margin: 20px 0 10px 0;
  }
  input, textarea {
    padding: 10px;
    border: none;
    border-bottom: solid 3px #ddd;
    width: 100%;
    box-sizing: border-box;
  }
  button {
    display: block;
    margin: 20px auto 0;
    background: rgba(255, 0, 0, 0.605);
    color: #fff;
    padding: 10px;
    border: none;
    border-radius: 0.3rem;
    font-size: 16px;
    cursor: pointer;
    text-transform: uppercase;
  }
</style>