
<script>
export default {
  props: {
    buttonText: {
      type: Number,
    },
  },

  emit:['submit'],

  data() {
    return {
      count: 1,
    };
  },
  methods: {
    increment() {
      this.$emit('submit',this.count = this.buttonText * this.count) ;
    },
  },
};
</script>

<template>
  <div>
    <button class="text-3xl" type="button" @click="increment">滑起來寶貝</button>
  </div> 
</template>
