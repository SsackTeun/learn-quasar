<template>
  <q-page class="q-pa-xl">
    <section class="q-mb-xl">
      <div class="text-h4">Toolbar</div>
      <q-separator class="q-my-md"/>
      <div class="row bg-primary q-px-sm" :style="{ minHeight: '50px'}">
          <div>
            <q-btn icon="menu" flat dense round color="white"></q-btn>
            <span class="text-h6 text-weight-bold text-white">Quasar App</span>
          </div>
      </div>
    </section>
    <section class="q-mb-xl">
      <div class="text-h4">Flex row</div>
      <q-separator class="q-my-md" />
      <div class="row">
        <div class="square"></div>
        <div class="square"></div>
        <div class="square"></div>
        <div class="square"></div>
        <div class="square"></div>
      </div>
      <q-separator spaced />
      <div class="row inline reverse bg-yellow">
        <div v-for="n in 6" :key="n" class="square">{{ n }}</div>
      </div>

      <div class="row inline reverse bg-yellow no-wrap">
        <div v-for="n in 16" :key="n" class="square">{{ n }}</div>
      </div>

      <div class="text-h4">Flex col</div>
      <q-separator class="q-my-md" />
      <div class="column">
        <div class="square"></div>
        <div class="square"></div>
        <div class="square"></div>
        <div class="square"></div>
        <div class="square"></div>
      </div>
    </section>
  </q-page>
</template>

<script setup>

</script>

<style lang="scss" scoped>
.square {
  height: 80px;
  width: 80px;
  background-color: $primary;
  border: 1px solid black;
  display: inline-block;
  font-weight: 900;
  color: white;
}
</style>
