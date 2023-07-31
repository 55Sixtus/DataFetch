

<template>
  <main>
    <h1>search movie</h1>
    <div class="input-btn">
      <input type="text" v-model="search">
      <button @click="getPosts">Fetch</button>
    </div>
    <div>
      <ul>
        <li :v-for="post in post">{{ post }}</li>
      </ul>
    </div>

  </main>

</template>

 <script>
export default{
  data(){
    return{
      post: [],
      search: ''
    }
  },
  methods: {
    getPosts(){
      fetch(`http://www.omdbapi.com/?i=tt3896198&apikey=ea8b573d`)
        .then(Response => Response.json())
        .then(data => this.post = data)
    }
  }
}

</script>
<style  scoped>
main{
  background-color: aqua;
}

</style>


