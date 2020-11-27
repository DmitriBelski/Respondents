<template>
  <div class="wrap">
    <aside>
      <div class="logo">
        <svg xmlns="http://www.w3.org/2000/svg" height="70" viewBox="0 0 24 24" width="70"><path d="M0 0h24v24H0V0z" fill="none" />
          <path d="M11.57 13.16c-1.36.28-2.17 1.16-2.17 2.41 0 1.34 1.11 2.42 2.49 2.42 2.05 0 3.71-1.66 3.71-3.71 0-1.07-.15-2.12-.46-3.12-.79 1.07-2.2 1.72-3.57 2zM13.5.67s.74 2.65.74 4.8c0 2.06-1.35 3.73-3.41 3.73-2.07 0-3.63-1.67-3.63-3.73l.03-.36C5.21 7.51 4 10.62 4 14c0 4.42 3.58 8 8 8s8-3.58 8-8C20 8.61 17.41 3.8 13.5.67zM12 20c-3.31 0-6-2.69-6-6 0-1.53.3-3.04.86-4.43 1.01 1.01 2.41 1.63 3.97 1.63 2.66 0 4.75-1.83 5.28-4.43C17.34 8.97 18 11.44 18 14c0 3.31-2.69 6-6 6z" />
        </svg>
      </div>
      <div class="nav">
        <nuxt-link to="/polls" class="button">
          <svg xmlns="http://www.w3.org/2000/svg" enable-background="new 0 0 24 24" height="70" viewBox="0 0 24 24" width="70">
            <g>
              <rect fill="none" height="24" width="24" />
            </g>
            <g>
              <path d="M4,7h16v2H4V7z M4,13h16v-2H4V13z M4,17h7v-2H4V17z M4,21h7v-2H4V21z M15.41,18.17L14,16.75l-1.41,1.41L15.41,21L20,16.42 L18.58,15L15.41,18.17z M4,3v2h16V3H4z" />
            </g>
          </svg>
          <span>Опросы</span>
        </nuxt-link>
        <nuxt-link to="/users" class="button">
          <svg xmlns="http://www.w3.org/2000/svg" enable-background="new 0 0 24 24" height="70" viewBox="0 0 24 24" width="70">
            <g>
              <rect fill="none" height="24" width="24" />
            </g>
            <g>
              <path d="M16.67,13.13C18.04,14.06,19,15.32,19,17v3h4v-3C23,14.82,19.43,13.53,16.67,13.13z" />
              <path d="M15,12c2.21,0,4-1.79,4-4c0-2.21-1.79-4-4-4c-0.47,0-0.91,0.1-1.33,0.24C14.5,5.27,15,6.58,15,8s-0.5,2.73-1.33,3.76 C14.09,11.9,14.53,12,15,12z" />
              <path d="M9,12c2.21,0,4-1.79,4-4c0-2.21-1.79-4-4-4S5,5.79,5,8C5,10.21,6.79,12,9,12z M9,6c1.1,0,2,0.9,2,2c0,1.1-0.9,2-2,2 S7,9.1,7,8C7,6.9,7.9,6,9,6z" />
              <path d="M9,13c-2.67,0-8,1.34-8,4v3h16v-3C17,14.34,11.67,13,9,13z M15,18H3l0-0.99C3.2,16.29,6.3,15,9,15s5.8,1.29,6,2V18z" />
            </g>
          </svg>
          <span>Пользователи</span>
        </nuxt-link>
        <nuxt-link to="/blacklists" class="button">
          <svg xmlns="http://www.w3.org/2000/svg" height="70" viewBox="0 0 24 24" width="70">
            <path d="M0 0h24v24H0V0z" fill="none" />
            <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zM4 12c0-4.42 3.58-8 8-8 1.85 0 3.55.63 4.9 1.69L5.69 16.9C4.63 15.55 4 13.85 4 12zm8 8c-1.85 0-3.55-.63-4.9-1.69L18.31 7.1C19.37 8.45 20 10.15 20 12c0 4.42-3.58 8-8 8z" />
          </svg>
          <span>Черные списки</span>
        </nuxt-link>
        <nuxt-link to="/callcenter" class="button">
          <svg xmlns="http://www.w3.org/2000/svg" height="70" viewBox="0 0 24 24" width="70"><path d="M0 0h24v24H0V0z" fill="none" />
            <path d="M6.54 5c.06.89.21 1.76.45 2.59l-1.2 1.2c-.41-1.2-.67-2.47-.76-3.79h1.51m9.86 12.02c.85.24 1.72.39 2.6.45v1.49c-1.32-.09-2.59-.35-3.8-.75l1.2-1.19M7.5 3H4c-.55 0-1 .45-1 1 0 9.39 7.61 17 17 17 .55 0 1-.45 1-1v-3.49c0-.55-.45-1-1-1-1.24 0-2.45-.2-3.57-.57-.1-.04-.21-.05-.31-.05-.26 0-.51.1-.71.29l-2.2 2.2c-2.83-1.45-5.15-3.76-6.59-6.59l2.2-2.2c.28-.28.36-.67.25-1.02C8.7 6.45 8.5 5.25 8.5 4c0-.55-.45-1-1-1z" />
          </svg>
          <span>Колл-центр</span>
        </nuxt-link>
      </div>
    </aside>

    <main>
      <header>
        <div class="info">
          <input type="text" placeholder="Поиск по системе">
          <div class="user">
            <img src="../assets/foto_58363.jpg" alt="Пользователь Василий">
            <div class="userinfo">
              <div class="name">
                Alexander C.
              </div>
              <div class="status">
                Администратор
              </div>
            </div>
          </div>
        </div>
        <div class="breadcrumbs">
          <ol class="cd-breadcrumb">
            <li>
              <nuxt-link to="/" exact>
                <svg xmlns="http://www.w3.org/2000/svg" height="24" viewBox="0 0 24 16" width="24">
                  <path d="M0 0h24v24H0V0z" fill="none" />
                  <path d="M12 5.69l5 4.5V18h-2v-6H9v6H7v-7.81l5-4.5M12 3L2 12h3v8h6v-6h2v6h6v-8h3L12 3z" />
                </svg>
              </nuxt-link>
            </li>
            <li v-for="(route, index) in currentRoutes" :key="index">
              <nuxt-link :to="route.path" exact class="breadcrumbs-link">
                {{ route.name }}
              </nuxt-link>
            </li>
          </ol>
        </div>
      </header>
      <section>
        <nuxt />
      </section>
    </main>
  </div>
</template>

<script>
export default {
  data () {
    return {
      paths: {
        polls: 'Опросы',
        parameters: 'Параметры',
        questions: 'Вопросы',
        logic: 'Логика',
        conditions: 'Условия',
        respondents: 'Респонденты',
        users: 'Пользователи',
        profile: 'Профиль',
        history: 'История',
        blacklists: 'Черные списки',
        block: 'Заблокировать',
        unblock: 'Разблокировать',
        callcenter: 'Колл-центр'
      },
      currentRouteArr: [],
      currentRoutes: []
    }
  },
  computed: {
    currentRouteName () {
      return this.$route.name
    }
  },
  watch: {
    currentRouteName () {
      this.currentRoutes.length = 0
      this.currentRouteArr = this.currentRouteName.split('-')
      let routesum = ''
      for (let i = 0; i < this.currentRouteArr.length; i++) {
        routesum += '/' + this.currentRouteArr[i]
        this.currentRoutes.push({ path: routesum, name: this.paths[this.currentRouteArr[i]] })
      }
    }
  }
}
</script>

<style>
html {
  font-family:
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  font-size: 12px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
  flex: 0 0 0;
  flex-flow: row nowrap;
}

html, body, .wrap {
  min-height: 100vh;
  height: 100%;
}
</style>

<style scoped>
.breadcrumbs-link {
  text-decoration: none;
  color: black;
}
.breadcrumbs .active-link {
  background-color: transparent;
}

.cd-breadcrumb {
  list-style-type: none;
  display: flex;
  align-items: center;
  padding-left: 0;
}

.cd-breadcrumb li{
  flex: 0 0 auto;
}

.cd-breadcrumb li:first-of-type:after {
  margin-bottom: 7px;
}

.cd-breadcrumb li:after{
  display: inline-block;
  width: 10px;
  content: '';
  height: 16px;
  width: 16px;
  background: url(../assets/cd-custom-separator.svg) no-repeat center center;
  vertical-align: middle;
}

.cd-breadcrumb li:last-of-type:after{
  display: none;
}

.wrap {
  display: flex;
  background-color: #eee;
}

aside {
  display: flex;
  flex-direction: column;
  flex: 0 0 140px;
  border-right: 1px solid #ddd;
}

.logo {
  flex: 0 0 auto;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 20px 0 30px 0;
}

.logo svg {
  fill: red;
  flex: 0 0 70px;
}

.nav {
  flex: 1 0 0%;
  display: flex;
  flex-direction: column;
}

.button {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  border: 3px solid #eee;
  border-radius: 5px;
  margin: 0 7px 7px 7px;
  padding: 5px;
  text-decoration: none;
  color: black;
}

.button svg {
  fill: black;
  flex: 0 0 40px;
}

.button span {
  text-align: center;
  font-weight: bold;
  margin: 0 5px 5px 5px;
}

.button:hover {
  fill: #92D050;
  border: 3px solid #92D050;
  background-color: #eee;
}

.button:hover svg {
  fill: #92D050;
}

.button:hover span {
  color: #92D050;
}

.active-link {
  background-color: #ddd;
}

main {
  margin: 0 20px;
  flex: 1 0 0%;
  display: flex;
  flex-direction: column;
}

header {
  margin-bottom: 10px;
  flex: 0 0 auto;
}

section {
  flex: 1 0 0;
}

.info {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px 0 10px;
}

.info input {
  padding-left: 10px;
  margin-right: 50px;
  height: 30px;
  color: #aaa;
  outline: none;
  border-radius: 3px;
  border: 1px solid #ddd;
  font-size: 1.4rem;
  background: url('../assets/search.svg') no-repeat white;
  background-position: right 10px center;
  background-size: 20px 20px;
  font-size: 11px;
  flex: 1 0 0;
}

.user {
  padding-right: 15px;
  display: flex;
  justify-content: center;
  align-items: center;
  flex: 0 0 auto;
}

.user img{
  margin-right: 15px;
  max-width: 40px;
  max-height: 40px;
  height: 40px;
  width: 40px;
  border-radius: 50%;
  object-fit: cover;
  flex: 0 0 auto;
}

.userinfo {
  flex: 1 1 0%;
}

.name {
  font-weight: bold;
}

.status {
  font-size: 10px;
}

</style>
