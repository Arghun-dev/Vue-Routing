<template>
    <div class="main-nav">
        <nav>
            <ul>
                <li><router-link to='/'>Home</router-link></li>
                <li><router-link :to="{ name: 'About' }">About</router-link></li>
            </ul>
        </nav>
    </div>
</template>

<script>
export default {
  name: 'Navbar',
  data () {
    return {

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
