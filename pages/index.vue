<template>
  <div>
    <h2>Index page</h2>
    <no-ssr>
    <v-select v-model="selected" placeholder="Select category" :options="['News', 'Advertisement']"></v-select>
    </no-ssr>
  </div>
</template>

<script>
export default {
  data(){
    return {
      selected: ''
    }
  }
}
</script>

