<template>
  <form class="card card-w30" v-on:submit.prevent="onSubmit">
    <div class="form-control">
      <label for="type">Тип блока</label>
      <select id="type" v-model="type">
        <option selected value="title">Заголовок</option>
        <option value="subtitle">Подзаголовок</option>
        <option value="avatar">Аватар</option>
        <option value="text">Текст</option>
      </select>
    </div>
    <div class="form-control">
      <label for="value">Значение</label>
      <textarea id="value" rows="3" v-model="value"></textarea>
    </div>
    <button class="btn primary" v-bind:disabled="isValid">Добавить</button>
  </form>
</template>

<script>
export default {
  name: "AppForm",
  emits: ["add-form-block"],
  data() {
    return {
      type: "subtitle",
      value: "",
    };
  },
  methods: {
    onSubmit() {
      this.$emit("add-form-block", {
        type: this.type,
        value: this.value,
        id: Date.now(),
      });

      this.type = "subtitle";
      this.value = "";
    },
  },
  computed: {
    isValid() {
      this.value.length < 4;
    },
  },
};
</script>

<style scoped>
</style>