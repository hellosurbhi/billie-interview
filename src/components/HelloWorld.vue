<template>
  <div class="doggie-tinder">
    <h2>Tinder yo dogs</h2>
    <div class="doggie-profiles">
      <div v-for="profile in profiles" :key="profile" class="doggie">
        <img height="400" width="400" alt="individual-dog-picture" :src="profile">
      </div>
    </div>
    <button @click="callProfile">></button>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
  },
  data: function () {
    return {
          quantity: 1,
          profiles: {},
    }
  },
  created() {
    this.callProfile()
  },
  // created() {
  //   fetch(`https://dog.ceo/api/breeds/image/random/${this.quantity}`)
  //   .then(response => response.json())
  //   .then(data => this.profiles = { ...data.message})
  //   },
methods: {
  callProfile() {
    fetch(`https://dog.ceo/api/breeds/image/random/${this.quantity}`)
    .then(response => response.json())
    .then(data => this.profiles = { ...data.message})
    },
    showNextDog() {

    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>


</style>
