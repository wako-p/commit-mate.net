<script setup lang="ts">
import type { TeamMember } from '@/types'

type Props = {
  member: TeamMember
}
const props = defineProps<Props>()

</script>

<template>

  <a
    :href="`https://github.com/${props.member.id}`" target="_blank" rel="noopener noreferrer"
    class="block bg-slate-50 rounded-md px-6 py-5 drop-shadow">

    <div class="w-full flex items-center space-x-4">
      <div>
        <img class="w-12 h-12 object-cover rounded-full" :src="`https://github.com/${props.member.id}.png`" alt="">
      </div>
      <div>
        <div class="text-lg text-slate-800 font-bold" v-html="props.member.displayname"></div>
        <div class="text-sm text-slate-500" v-html="props.member.id"></div>
      </div>
    </div>

    <div class="mt-6">
      <p class="text-sm text-slate-700 leading-6" v-html="props.member.bio"></p>
    </div>

  </a>

</template>