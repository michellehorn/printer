<script>
export default {
  name: 'printer',
  methods: {
    async getPrinters() {
      await fetch('http://localhost:3000/printers', {
        method: 'GET',
        mode: 'no-cors',
        headers: { 'Content-Type': 'application/json' }
      })
        .then((res) => res.json())
        .catch((err) => err);
    },

    async handle() {
      const data = await this.getPrinters();
      console.log(data)
    }
  }
}
</script>

<template>
  <button @click="handle()">Click</button>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
