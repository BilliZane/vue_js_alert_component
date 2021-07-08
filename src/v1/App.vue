<template>
  <div>

    <app-alert
      v-if="alert"
      title="Внимание!"
      text="Это действие запрещено для данной страницы."
      type="danger"
      :closable="true"
      @close="alert = false"
    ></app-alert>

    <div class="card">
      <button class="btn primary" @click="toggleAlert">
        {{ alert ? 'Скрыть сообщение' : 'Показать сообщение' }}
      </button>
    </div>

    <app-block></app-block>
  </div>
</template>

<script>

import AppAlert from "./components/AppAlert.vue";
import AppBlock from "./components/AppBlock.vue";

export default {
  data() {
    return {
      alert: false
    }
  },
  methods: {
    toggleAlert() {
      this.alert = !this.alert
    }
  },
  components: {
    AppAlert, AppBlock
  }, 
};
</script>
