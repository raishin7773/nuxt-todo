<template>
  <div>
    <div class="form">
      <form v-on:submit.prevent="add">
        <input v-model="name">
        <button>Add</button>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      name: '',
      done: false
    }
  },
  created: function () {
    this.$store.dispatch('todo/init')
  },
  methods: {
    add() {
      this.$store.dispatch('todo/add', this.name)
      this.name = ''
    }
  }
}
</script>
