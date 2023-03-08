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

<script setup>
import { ref, watch } from 'vue'
import { useRoute } from 'vue-router'

const chats = ref()
const route = useRoute()

watch(
  () => route.params,
  (value) => {
    console.log('update params', value)
    chats.value = [
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
  {
    inmediate: true
  }
)
</script>
