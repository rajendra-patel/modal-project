<template>
    <div>
        <app-header :title="title" @onTitleChange="updateTitle($event)"></app-header>
        <router-view></router-view>
        <keep-alive>
            <component :is="component"></component>
        </keep-alive>
        <app-ninjas :ninjas="ninjas"></app-ninjas>
        <ul>
          <li v-for="(ninja, index) in ninjas" :key="index">{{ ninja.name }}</li>
        </ul>
        <app-footer :title="title"></app-footer>
    </div>
</template>

<script>
// Imports
import Header from './components/Header.vue';
import Footer from './components/Footer.vue';
import Ninjas from './components/Ninjas.vue';
import HelloWorld from './components/HelloWorld';

export default {
    components: {
        'app-header': Header,
        'app-footer': Footer,
        'app-ninjas': Ninjas,
        'app-hello': HelloWorld
    },
    data () {
        return {
          ninjas: [
              {name: 'Ryu', speciality: 'Vue Components', show: false},
              {name: 'Crystal', speciality: 'HTML Wizardry', show: false},
              {name: 'Hitoshi', speciality: 'Click Events', show: false},
              {name: 'Tango', speciality: 'Conditionals', show: false},
              {name: 'Kami', speciality: 'Webpack', show: false},
              {name: 'Yoshi', speciality: 'Data Diggin', show: false}
          ],
          title: 'Vue Wizards',
          component: 'app-hello'
        }
    },
    methods: {
        updateTitle(event) {
            this.title = event;
        }
    }
}
</script>

<style>
body{
    margin: 0;
    font-family: 'Nunito SemiBold';
}
</style>