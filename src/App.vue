<script>
import axios from 'axios';
import {store} from './store';

export default{
  name: 'app',
  components:{
    
  },
  data(){
    return{
      store,
      post:[]
    }
  },
  mounted(){
    this.getPosts();
  },
  methods: {
    getPosts(){
      axios.get(`http://127.0.0.1:8000/api/posts`)
    .then(res => {
        this.post = res.data.posts;
      })
    }
  }
}
</script>

<template>
  <div id="tutto">
    <h1>Ciao Mondo</h1>
    <ul>
      <li></li>
    </ul>
  </div>
  
  
</template>

<style lang="scss">
@use './style/main.scss' as *;

#tutto{
height: 100vh;
}


</style>
