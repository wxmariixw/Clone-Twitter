<template>
  <div id="app">
    <!--navegação-->
    <nav class="w-full h-16 border border-gray-100 rounded shadow-md">
      <div class="flex content-center max-w-screen-lg h-16 m-auto">
        <!--botões-->
        <div class="flex justify-between inline-block w-2/5 h-16">
          <button v-for="tab in tabs" class="w-auto m-2 p-2 text-sm text-blue-400 md:text-sm font-semibold hover:bg-blue-50 hover:text-blue-700 rounded-full">
            <fa :icon="`${tab.icons}`" class="inline-block"/>
            <p class="inline-block">{{tab.title}}</p>
          </button>
        </div>
        <!--icon twitter-->
        <div class="flex justify-around inline-block w-1/5 p-3">
          <svg aria-hidden="true" focusable="false" data-prefix="fab" data-icon="twitter" class="svg-inline--fa fa-twitter text-blue-400 hover:text-blue-700 text-4xl" role="img" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512"><path fill="currentColor" d="M459.4 151.7c.325 4.548 .325 9.097 .325 13.65 0 138.7-105.6 298.6-298.6 298.6-59.45 0-114.7-17.22-161.1-47.11 8.447 .974 16.57 1.299 25.34 1.299 49.06 0 94.21-16.57 130.3-44.83-46.13-.975-84.79-31.19-98.11-72.77 6.498 .974 12.99 1.624 19.82 1.624 9.421 0 18.84-1.3 27.61-3.573-48.08-9.747-84.14-51.98-84.14-102.1v-1.299c13.97 7.797 30.21 12.67 47.43 13.32-28.26-18.84-46.78-51.01-46.78-87.39 0-19.49 5.197-37.36 14.29-52.95 51.65 63.67 129.3 105.3 216.4 109.8-1.624-7.797-2.599-15.92-2.599-24.04 0-57.83 46.78-104.9 104.9-104.9 30.21 0 57.5 12.67 76.67 33.14 23.72-4.548 46.46-13.32 66.6-25.34-7.798 24.37-24.37 44.83-46.13 57.83 21.12-2.273 41.58-8.122 60.43-16.24-14.29 20.79-32.16 39.31-52.63 54.25z"></path></svg>
        </div>
        <!--pesquisa e configurações-->
        <div class="flex justify-between inline-block w-2/5 h-16 py-5">
          <form class="inline-block border border-gray-100">
            <input class="">
          </form>
          <button v-for="bot in bott" class="w-auto m-2 p-2 text-sm text-blue-400 md:text-sm font-semibold hover:bg-blue-50 hover:text-blue-700 rounded-full">
            <fa :icon="`${bot.icone}`" class="inline-block"/>
          </button>
        </div>  
      </div>
    </nav>
  </div>
</template>

<script>
export default {
  name: 'app',
  components: {

  },
  data () {
    return {
      tabs: [
        {icons: 'house-user', title: 'Home', id: 'home'},
        {icons: 'bell', title: 'Notificações', id: 'notifications'},
        {icons: 'hashtag', title: 'Descobrir', id: 'discover'},
        {icons: 'user', title: 'Perfil', id: 'profile'}
      ],
      bott: [
        {icone: 'house-user', id: 'messages'},
        {icone: 'bell', id: 'settings'},
        {icone: 'hashtag', id: 'edit'},
      ]
    }
  }
}
</script>
