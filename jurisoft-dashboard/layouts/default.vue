<template>
  <div class="total">
    <div class="sidebar">
      <LayoutMenuLateral @change-content="changeContent" @estado-menu="estadoMenu" :user="user" />
    </div>
    <main>
      <section>
        <LayoutHeader :user="user" :estadomenu="estadomenu"/>
      </section>
      <section class="content">
        <!-- <UiFeedbackDiario v-if="content === 'Dashboard'" /> -->
        <div class="parent" v-if="content === 'Dashboard'">
          <div class="grid-area-1">
            <UiTimeTracker />
          </div>
          <div class="grid-area-2">
            <UiHorasDiarias />
          </div>
          <div class="grid-area-3">
            <UiCursosProgresso />
          </div>
          <div class="grid-area-4">
            <UiColaboladoresDestaque />
          </div>
          <div class="grid-area-5">
            <UiCursosAndamento />
          </div>
          <div class="grid-area-6">
            <UiFeedbackDiario />
          </div>
        </div>
        <p v-if="content === 'Calendário'">Calendário</p>
        <p v-if="content === 'Descanso'">Descanso</p>
        <p v-if="content === 'Projetos'">Projetos</p>
        <p v-if="content === 'Times'">Times</p>
        <p v-if="content === 'Integrações'">Integrações</p>
        <p v-if="content === 'Benefícios'">Benefícios</p>
        <p v-if="content === 'Documentos'">Documentos</p>
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
      estadomenu: true,
    };
  },
  methods: {
    changeContent(content) {
      this.content = content;
    },
    estadoMenu(menu) {
      this.estadomenu = menu;
      // console.log(this.estadomenu);
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
  padding: 0 32px;
}

.parent {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: repeat(4, 1fr);
  grid-column-gap: 0px;
  grid-row-gap: 0px;
  grid-gap: 12px;
}

.grid-area-1 { grid-area: 1 / 1 / 3 / 2; }
.grid-area-2 { grid-area: 1 / 2 / 2 / 3; }
.grid-area-3 { grid-area: 2 / 2 / 3 / 3; }
.grid-area-4 { grid-area: 1 / 3 / 3 / 4; }
.grid-area-5 { grid-area: 3 / 1 / 5 / 3; }
.grid-area-6 { grid-area: 3 / 3 / 5 / 4; }

</style>