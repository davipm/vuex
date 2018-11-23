<template>
  <div class="stats">
    <h1>A different component</h1>
    <p>There are currently {{ countLinks }} links</p>
    <button class="btn-remove" @click="removeAllLinks">
      Remove all links
    </button>
    <p>{{ msg }}</p>
  </div>
</template>

<script>
  import { mapGetters, mapActions, mapMutations } from 'vuex'
  export default {
    name: "Stats",
    data() {
      return {
        msg: ''
      }
    },

    computed: {
        ...mapGetters([
            'countLinks'
        ]),
    },

    methods: {
        ...mapMutations(['REM0VE_ALL']),
        ...mapActions(['removeAll']),

      removeAllLinks() {
        this.removeAll().then(() => {
          this.msg = 'They have been removed'
        })
      }
    }
  }
</script>

<style scoped>
  .btn-remove {
    padding: 10px;
    margin-top: 30px;
    width: 100%;
    background: none;
    border: 1px solid lightgray;
    outline: 0;
    cursor: pointer;
  }
</style>