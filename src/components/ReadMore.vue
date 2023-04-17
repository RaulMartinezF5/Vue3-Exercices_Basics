    <script setup>
    import { ref } from "vue";
    
    const title = ref("Exercise Read More");
    const isExpanded = ref(false);
    const buttonText = ref("Show More");
    
    function toggleExpanded() {
      isExpanded.value = !isExpanded.value;
      buttonText.value = isExpanded.value ? "Show Less" : "Show More";
    }
    </script>
<template>
  <div class="container text-center">
    <h1 class="my-3">{{ title }}</h1>
    <div>
      <p class="mb-3 d-block" :class="{ 'cut-text': !isExpanded, 'full-text': isExpanded }">
        Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dignissimos
        ipsa neque odio consectetur impedit tempore modi accusantium! Voluptatem
        molestiae nemo inventore soluta corrupti. Culpa perferendis sapiente
        deserunt aperiam maxime consectetur recusandae quasi commodi dicta
        temporibus pariatur ab repellendus dignissimos natus aliquam odit ullam,
        quaerat autem non hic, quidem dolore laboriosam.
      </p>
      <button class="btn btn-primary" @click="toggleExpanded">{{ buttonText }}</button>
    </div>
    <hr class="mb-4" />
  </div>
</template>


<style lang="css">
.full-text {
  overflow: inherit;
  white-space: break-spaces;
}

.full-text + button {
  display: none;
}
</style>
