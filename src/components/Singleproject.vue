<template>
  <q-card flat bordered class="my-card q-mx-auto" :class="{complete : project.complete}">
    <q-card-section>
      <div class="text-h6 q-mx-auto">{{project.title}}</div>
    </q-card-section>

    <q-separator inset />

    <q-card-section>
      {{project.details}}
    </q-card-section>

    <q-card-actions align="right">
      <!-- <q-btn flat>Action 1</q-btn>
      <q-btn flat>Action 2</q-btn> -->
      <q-btn flat color="green-10" icon="done" />
      <q-btn flat color="green-10" icon="settings" />
    </q-card-actions>

  </q-card>
</template>

<script>
  export default {
    props: ["project"],
    data() {
      return {

      }
    },
  }
</script>

<style lang="css" scoped>
.my-card {
  width: 100%;
  max-width: 350px;
  border-left: 4px solid #4E6C50;
}
.my-card.complete {
  border-left: 4px solid #00ce89;
}
</style>
