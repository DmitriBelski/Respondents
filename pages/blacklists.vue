<template>
  <div class="wraper">
    <div class="menu">
      <nuxt-link to="/blacklists/block" class="menuitem">
        Заблокировать
      </nuxt-link>
      <nuxt-link to="/blacklists/unblock" class="menuitem">
        Разблокировать
      </nuxt-link>
    </div>
    <div class="content">
      <nuxt-child />
    </div>
  </div>
</template>

<style scoped>
  .wraper {
    display: flex;
    flex-direction: column;
  }

  .menu {
    display: flex;
    padding-bottom: 15px;
  }

  .menuitem {
    flex: 0 0 100px;
    border-bottom: 1px solid #ddd;
    text-decoration: none;
    color: seagreen;
    padding: 10px 20px;
    text-align: center;
  }

  .menuitem:hover {
    background-color: #ddd;
  }

  .active-link {
    border-bottom: 2px solid seagreen;
  }

  .content {
    flex: 1 0 0%;
  }

</style>
