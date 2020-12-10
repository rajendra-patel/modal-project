<template>
    <header>
        <h1 @click="changeTitle">{{ title }}</h1>
    </header>
    <nav>
      <router-link to="/home" exact>Home</router-link> |
      <router-link to="/about" exact>About</router-link>
    </nav>
</template>
<script>
export default {
    props: {
      title: {
        type: String,
        required: true
      }
    },
    data(){
        return{

        }
    },
    methods: {
      changeTitle: function(){
        this.$emit('onTitleChange', 'Vue Ninjas');
        // this.title = 'Vue Ninjas';
      }
    }
}
</script>
<style scoped>
header{
    background: lightgreen;
    padding: 10px;
}
h1{
    color: #222;
    text-align: center;
}
</style>