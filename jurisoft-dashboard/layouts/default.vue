<template>
  <div class="total">
    <div class="sidebar">
      <LayoutMenuLateral @change-content="changeContent" :user="user" />
    </div>
    <main>
      <section>
        <LayoutHeader :user="user" />
      </section>
      <section class="content">
        <!-- <UiFeedbackDiario v-if="content === 'Dashboard'" /> -->
        <UiTimeTracker v-if="content === 'Dashboard'" />
        <p v-if="content === 'Calendário'">Calendário</p>
        <p v-if="content === 'Descanso'">Descanso</p>
        <p v-if="content === 'Agenda'">Agenda</p>
        <p v-if="content === 'Financeiro'">Financeiro</p>
      </section>
    </main>
  </div>
</template>

<script>
export default {
  data() {
    return {
      content: "Dashboard",
      user: {
        name: "Sophia Williams",
        email: "sophia@jurisoft.com"
      },
    };
  },
  methods: {
    changeContent(content) {
      this.content = content;
    },
  },
};
</script>

<style scoped>
.total {
  display: flex;
}
.sidebar {
  width: fit-content;
}
main {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  flex-wrap: wrap;
  flex-grow: 1;
  justify-content: baseline;
}
section{
  width: 100%;
}

.content {
  padding: 32px;
}
</style>