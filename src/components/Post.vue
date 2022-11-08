<style>
.grid {
  display: grid;
}
</style>
<template>
  <article>
    <p>{{ post.title }} - {{ post.body }}</p>
  </article>
</template>

<script>
export default {
  props: ["post"],
};
</script>