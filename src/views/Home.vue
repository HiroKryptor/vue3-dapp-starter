<script setup lang="ts">
import { ref } from 'vue'
import { useEthersHooks } from 'vue-dapp'
import { Round } from 'clrfund-js'

const { onActivated } = useEthersHooks()
onActivated(async ({ signer }) => {
  const round = new Round(
    '0x61c36a8d610163660E21a8b7359e1Cac0C9133e1',
    '0x856e4424f806D16E8CBC702B3c0F2ede5468eae5',
    signer,
  )
  console.log(await round.round.nativeToken())
})

const count = ref(0)
const add = () => count.value++
</script>

<template>
  <div class="text-center">
    <p>Home: {{ count }}</p>
    <button class="btn" @click="add">Count</button>
  </div>
</template>
