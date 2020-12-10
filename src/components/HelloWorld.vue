<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>
      For a guide and recipes on how to configure / customize this project,<br />
      check out the
      <a href="https://cli.vuejs.org" target="_blank" rel="noopener"
        >vue-cli documentation</a
      >.
    </p>
    <label>Username</label>
    <input type="text" v-model.lazy="userName"/>
    <h3>Essential Links</h3>

    <h3>Ecosystem</h3>

  </div>
  <div id="checkboxes">
      <p>Blog Categories:</p>
      <label>Ninjas</label>
      <input type="checkbox" value="ninjas" v-model="blog.categories" />
      <label>Wizards</label>
      <input type="checkbox" value="wizards" v-model="blog.categories" />
      <label>Mario</label>
      <input type="checkbox" value="mario" v-model="blog.categories" />
      <label>Cheese</label>
      <input type="checkbox" value="cheese" v-model="blog.categories" />
  </div>
  <div id="preview">
      <p>Username: {{ userName }}</p>
      <h3>Preview blog</h3>
      <p>Blog Categories:</p>
      <ul>
          <li v-for="(category, idx) in blog.categories" :key="idx">{{ category }}</li>
      </ul>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String
  },
  data() {
    return {
      userName: '',
      blog: {
        title: '',
        content: '',
        categories: []
      }
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
#checkboxes input{
    display: inline-block;
    margin-right: 10px;
}
#checkboxes label{
    display: inline-block;
}
</style>
