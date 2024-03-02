<script>


</script>

<template>
  <header class="w-full h-[60px] text-white bg-slate-600 flex items-center justify-center">
    <div class="wrapper flex justify-end">
      <nav class="w-[200px] h-full flex items-center justify-center gap-5">
        <RouterLink class="text-white" to="/">Home</RouterLink>
        <RouterLink to="/cityApi">cityAPI</RouterLink>
      </nav>
    </div>
  </header>

  <RouterView />
</template>

<style scoped>

</style>
