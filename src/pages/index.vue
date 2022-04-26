<script setup lang="ts">
const name = $ref('')

const router = useRouter()
const go = () => {
  if (name)
    router.push(`/to/${encodeURIComponent(name)}`)
}
</script>

<template>
  <div>
    <p>Happy Birthday</p>
    <p mb-2>
      <em text-sm op75>Surprise your friend.</em>
    </p>

    <input
      id="input"
      v-model="name"
      placeholder="Who's birthday is it?"
      type="text"
      autocomplete="false"
      p="x-4 y-2"
      w="250px"
      text="center"
      bg="transparent"
      border="~ rounded gray-200 dark:gray-700"
      outline="none active:none"
      @keydown.enter="go"
    >

    <div>
      <button
        class="m-3 text-sm btn"
        :disabled="!name"
        @click="go"
      >
        Go
      </button>
    </div>
  </div>
</template>
