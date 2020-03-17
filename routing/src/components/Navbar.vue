<template>
    <div class="main-nav">
        <nav>
            <ul>
                <li><router-link to='/'>Home</router-link></li>
                <li><router-link :to="{ name: 'About' }">About</router-link></li>
            </ul>
            <ul v-for="(id, index) in userIds" :key="index">
                <li><router-link :to="{ name: ViewProfile, params: { user_id: id } }">Profile {{id}}</router-link></li>
            </ul>
            <h2>Redirect Programatically</h2>
            <button @click='goHome()'>Go Home</button>
        </nav>
    </div>
</template>

<script>
export default {
  name: 'Navbar',
  data () {
    return {
      userIds: ['1', '2', '3', '4']
    }
  },

  methods: {
    goHome () {
      this.$router.push({ name: 'Home' })
    }
  }
}
</script>

<style scoped>
ul {
    list-style-type: none;
    display: flex;
    justify-content: center;
    padding: 2rem;
}

ul li {
    margin-right: 2rem;
}

a {
    color: #42b983;
}
</style>
