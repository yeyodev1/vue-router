<template>
  <div>
    <aside>
      <div v-for="chat in chats" :key="chat.id">
        <router-link :to="`/chats/${chat.id}`">{{ chat.name }}</router-link>
      </div>
    </aside>
    <article>
      <router-view></router-view>
    </article>
  </div>
</template>

<script>
export default {
  data() {
    return {
      chats: []
    }
  },

  created() {
    this.$watch(
      () => this.$route.params,
      (value) => {
        console.log('update params', value)
        this.chats = [
          {
            id: 1,
            name: 'Fiorella'
          },
          {
            id: 2,
            name: 'Fiorella'
          },
          {
            id: 3,
            name: 'Fiorella'
          }
        ]
      },
      { inmediate: true }
    )
  }
}
</script>
