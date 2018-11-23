<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <router-view/>
  </div>
</template>

<style lang="scss">
  html,
  #app,
  .home {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    height: 100%;
    padding: 0;
    margin: 0;
  }

  body {
    background-color: #F4F4F4;
    margin: 0;
    height: 100%;
  }

  .hello {
    display: grid;
    grid-template-columns: repeat(2, 50%);
    grid-template-rows: 100%;
    grid-template-areas:
      "left right";
    height: 100%;
  }

  .left,
  .right {
    padding: 30px;
  }

  ul {
    list-style: none;
    padding: 0;

    li {
      display: block;
      padding: 20px;
      background-color: white;
      margin-bottom: 8px;
    }
  }

  .right {
    grid-area: right;
    background-color: #E9E9E9;
  }

  .input-form {
    border: none;
    padding: 20px;
    width: calc(100% - 40px);
    box-shadow: 0 5px 5px lightgray;
    margin-bottom: 50px;
    outline: none;
  }

  .rm {
    float: right;
    text-transform: uppercase;
    font-size: .8em;
    background: #f9d0e3;
    border: none;
    padding: 5px;
    color: #ff0076;
    cursor: pointer;
  }
</style>
