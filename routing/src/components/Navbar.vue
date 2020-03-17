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
            <h2>Navigation Controls</h2>
            <button @click='goHome()'>Go Home</button>
            <button @click="goBack()">Go Back</button>
            <button @click="goForward()">Go Forward</button>
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
    },

    goBack () {
      this.$router.go(-1)
    },

    goForward () {
      this.$router.go(1)
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

a.router-link-exact-active {
    color: purple;
}
</style>
