<template>
  <div>
    <van-cell :title="obj.title" :value="date" @click="show = true" />
    <van-calendar v-model="show" @confirm="onConfirm" />
  </div>
</template>

<script>
export default {
  props: {
    obj: {
      type: Object,
      default: () => {},
    },
  },
  data() {
    return {
      date: "",
      show: false,
    };
  },
  methods: {
    formatDate(date) {
      return `${date.getMonth() + 1}/${date.getDate()}`;
    },
    onConfirm(date) {
      this.show = false;
      this.date = this.formatDate(date);
    },
  },
};
</script>