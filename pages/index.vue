<template>
  <div class="container">
    <PushButton @click="toast">OPEN TOAST</PushButton>
    <PushButton @click="openModal">OPEN MODAL</PushButton>
  </div>
</template>

<script>
export default {
  methods: {
    toast() {
      this.$toast.show({
        type: 'info',
        message: 'this is the message',
      })
    },
    openModal() {
      this.$modal.show({
        type: 'danger',
        title: 'This is the title property',
        body:
          'This is the body property.  Lorem ipsum, dolor sit amet consectetur adipisicing elit. Eius aliquam laudantium explicabo pariatur iste dolorem animi vitae error totam.',
        primary: {
          label: 'Primary Action',
          theme: 'red',
          action: () => this.$toast.success('Primary Button clicked'),
        },
        secondary: {
          label: 'Secondary Button',
          theme: 'white',
          action: () => this.$toast.info('Clicked Secondary'),
        },
      })
    },
  },
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}
</style>
