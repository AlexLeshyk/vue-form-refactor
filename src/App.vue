<template>
  <div class="container column">
    <AppForm v-on:add-form-block="addFormBlock"/>
    <AppView v-bind:elements="blocks"/>
  </div>
  <div class="container">
    <p>
      <button class="btn primary">Загрузить комментарии</button>
    </p>
    <div class="card">
      <h2>Комментарии</h2>
      <ul class="list">
        <li class="list-item">
          <div>
            <p><strong>test@microsoft.com</strong></p>
            <small>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Eligendi, reiciendis.</small>
          </div>
        </li>
      </ul>
    </div>
    <div class="loader"></div>
  </div>
</template>

<script>
import AppView from "./components/AppView";
import AppForm from "./components/AppForm";
export default {
  components: {
    AppView: AppView,
    AppForm: AppForm,
  },
  data() {
    return {
      blocks: [],
    }
  },
  methods: {
    addFormBlock(element) {
      this.blocks.push(element);
    }
  }
}
</script>
