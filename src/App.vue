<template>
    <div id="app">
        <div class="container mx-auto">
            <div id="nav">
                <router-link :class="{ active: $route.name === 'Home' }" to="/"
                    >Home
                </router-link>
                <router-link
                    :class="{ active: $route.name === 'Cart' }"
                    to="/cart"
                    >Cart
                </router-link>
            </div>
            <img alt="Vue logo" src="./assets/logo.png" />

            <router-view />
        </div>
    </div>
</template>

<script setup></script>

<style lang="scss">
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;

    img {
        margin: 0 auto;
    }
}

#nav {
    padding: 30px;
    width: 100%;
    height: 30px;

    a {
        font-weight: bold;
        color: darkgray;
        text-decoration: none;
        margin: 0 5px 0 5px;
        font-size: 1.25rem;

        &.active {
            color: #2c3e50;
        }
    }
}

html,
body {
    padding: 0;
    margin: 0;
    overflow-x: hidden;
}

body {
    background-color: whitesmoke;
}
</style>
