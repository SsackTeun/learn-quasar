<template>
  <q-page class="q-pa-xl">
    <q-separator class="q-my-md"/>
    <section >
      <p class="text-h6">breakpoints</p>
      <q-separator class="q-my-md"/>
      <div class="target flex flex-center">
        <span class="text-h2 text-weight-bold text-white">
         {{$q.screen.name}}
        </span>
      </div>
      <div v-if="$q.screen.gt.sm" class="target flex flex-center">
        <span class="text-h2 text-weight-bold text-white">
         {{$q.screen.name}}
        </span>
      </div>
    </section>
    <section>
      <p class="text-h6">$q.screen</p>
      <q-separator class="q-my-md"/>
      <div>
        <li v-for="(value, key) in $q.screen" :key="key">
          <span class="inline-block" style="width: 120px">{{ key }}</span> - <span>{{ isFunction (value) ? '함수' : value}}</span>
        </li>
      </div>
    </section>
  </q-page>
</template>

<script>
export default {
  mounted() {
    console.log('this.$q.screen: ', this.$q.screen)
  }
}
</script>

<script setup>
import { useQuasar } from 'quasar';
const $q = useQuasar();
console.log('setup -> $q.screen: ', $q.screen);

const isFunction = value => typeof value === 'function'
</script>

<style lang="scss" scoped>
.target {
  height: 200px;
  background-color: $dark;
}
@media (max-width: $breakpoint-xs-max) {
  .target {
    background-color: $red;
  }
}

.target {
  body.screen--sm & {
    background-color: $orange;
  }
}
</style>
