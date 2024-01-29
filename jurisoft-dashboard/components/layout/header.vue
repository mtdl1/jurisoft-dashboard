<template>
  <div>
    <header>
      <div class="user">
        <div class="avatar">
          <img src="@/assets/img/sophia-williams.png" alt="">
        </div>
        <div class="texto">
          <p class="name">{{ user.name }}</p>
          <p class="mensagem">Bem-vinda de volta 👋🏻</p>
        </div>
      </div>
      <div class="utilidades">
        <div class="icons">
          <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 20 20" fill="none">
            <path d="M9.25 2.5C12.976 2.5 16 5.524 16 9.25C16 12.976 12.976 16 9.25 16C5.524 16 2.5 12.976 2.5 9.25C2.5 5.524 5.524 2.5 9.25 2.5ZM9.25 14.5C12.1502 14.5 14.5 12.1502 14.5 9.25C14.5 6.349 12.1502 4 9.25 4C6.349 4 4 6.349 4 9.25C4 12.1502 6.349 14.5 9.25 14.5ZM15.6137 14.5532L17.7355 16.6742L16.6742 17.7355L14.5532 15.6137L15.6137 14.5532Z" fill="#525866"/>
          </svg>
          <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 20 20" fill="none">
            <path d="M16 13.75H17.5V15.25H2.5V13.75H4V8.5C4 6.9087 4.63214 5.38258 5.75736 4.25736C6.88258 3.13214 8.4087 2.5 10 2.5C11.5913 2.5 13.1174 3.13214 14.2426 4.25736C15.3679 5.38258 16 6.9087 16 8.5V13.75ZM14.5 13.75V8.5C14.5 7.30653 14.0259 6.16193 13.182 5.31802C12.3381 4.47411 11.1935 4 10 4C8.80653 4 7.66193 4.47411 6.81802 5.31802C5.97411 6.16193 5.5 7.30653 5.5 8.5V13.75H14.5ZM7.75 16.75H12.25V18.25H7.75V16.75Z" fill="#525866"/>
          </svg>
        </div>
        <transition name="slide">
        <div class="botoes" v-if="menu">
          <button class="btn soft"> 
            <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 20 20" fill="none">
              <path d="M7.75 1.75V3.25H12.25V1.75H13.75V3.25H16.75C16.9489 3.25 17.1397 3.32902 17.2803 3.46967C17.421 3.61032 17.5 3.80109 17.5 4V16C17.5 16.1989 17.421 16.3897 17.2803 16.5303C17.1397 16.671 16.9489 16.75 16.75 16.75H3.25C3.05109 16.75 2.86032 16.671 2.71967 16.5303C2.57902 16.3897 2.5 16.1989 2.5 16V4C2.5 3.80109 2.57902 3.61032 2.71967 3.46967C2.86032 3.32902 3.05109 3.25 3.25 3.25H6.25V1.75H7.75ZM16 8.5H4V15.25H16V8.5ZM12.277 9.352L13.3375 10.4125L9.625 14.125L6.973 11.473L8.035 10.4125L9.62575 12.004L12.2778 9.352H12.277ZM6.25 4.75H4V7H16V4.75H13.75V5.5H12.25V4.75H7.75V5.5H6.25V4.75Z" fill="#525866"/>
            </svg> 
            Calendário
          </button>
          <button class="btn secondary">
            <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 20 20" fill="none">
              <path d="M9.25 9.25V4.75H10.75V9.25H15.25V10.75H10.75V15.25H9.25V10.75H4.75V9.25H9.25Z" fill="white"/>
            </svg>
            Nova solicitação
          </button>
        </div>
        </transition>
      </div>
    </header>
    <!-- <p>{{ menu }}</p> -->
  </div>
</template>

<script>
export default {
  data() {
    return {
      menu: true,
    }
  },
  props: {
    user: {
      type: Object,
      required: true,
    },
    estadomenu: {
      type: Boolean,
      required: true,
    },
  },
  watch: {
    estadomenu: function (val) {
      this.menu = val;
    }
  },
}
</script>

<style scoped lang="scss">
@import "@/assets/scss/main.scss";
header {
  width: 100%;
  padding: 24px 32px;
  display: flex;
  .user{
    display: flex;
    align-items: center;
    gap: 14px;
    flex-grow: 1;
    .texto{
      .name{
        color: $primary;
        font-size: 18px;
        font-style: normal;
        font-weight: 500;
        line-height: 24px; /* 133.333% */
        letter-spacing: -0.27px;
      }
      .mensagem{
        color: $soft;
        font-size: 14px;
        font-style: normal;
        font-weight: 400;
        line-height: 20px; /* 142.857% */
        letter-spacing: -0.084px;
      }
    }
  }
  .utilidades{
    display: flex;
    align-items: center;
    gap: 16px;
    .icons{
      display: flex;
      align-items: center;
      gap: 16px;
      svg{
        cursor: pointer;
      }
    }
    .botoes{
      display: flex;
      align-items: center;
      gap: 16px;
    }
  }
}

.slide-enter-active, .slide-leave-active {
  transition: transform 0.5s;
}

.slide-enter, .slide-leave-to {
  transform: translatey(-250%);
}
</style>
