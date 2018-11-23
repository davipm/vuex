<template>
  <div class="hello">
    <div class="left">
      <h1 class="title">
        {{ title }}
      </h1>
      <form @submit.prevent="addLink">
        <input type="text"
               class="input-form"
               placeholder="Add links"
               v-model="newLink"
        >
      </form>
      <ul class="links-list">
        <li class="links-item" v-for="(link, index) in links" :key="index">
          {{ link }}
          <button @click="removeLinks(index)" class="rm">
            Remove
          </button>
        </li>
      </ul>
    </div>
    <div class="right">
      <Stats />
    </div>
  </div>
</template>

<script>
  import Stats from './Stats.vue'
  import { mapState, mapMutations, mapActions } from 'vuex'
  export default {
    name: 'HelloWorld',
    components: {
      Stats
    },

    props: {
      msg: String
    },

    data() {
      return {
        newLink: ''
      }
    },

    methods: {
        ...mapMutations([
            'ADD_LINK'
        ]),

        ...mapActions([
            'removeLink'
        ]),

      addLink() {
        this.ADD_LINK(this.newLink);
        this.newLink = '';
      },

      removeLinks(link) {
        this.removeLink(link);
      }
    },

    computed: {
        ...mapState([
            'title',
            'links'
        ])
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>
