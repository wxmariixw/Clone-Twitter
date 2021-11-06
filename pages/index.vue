<template>
  <div id="app" class="w-screen bg-gray-50">
    <!--navegação-->
    <nav class="flex w-full h-16 bg-white border border-gray-100 rounded shadow-md">
      <div class="flex w-full xl:w-11/12 h-16 m-auto">
        <!--botões desktop-->
        <div class="flex justify-between inline-block w-1/3 h-16">
          <button v-for="tab in tabs" class="w-auto my-2 px-2 text-base text-blue-400 font-semibold hover:bg-blue-50 hover:text-blue-700 rounded-full">
            <fa :icon="`${tab.icons}`" class="inline-block"/>
            <p class="inline-block">{{tab.title}}</p>
          </button>
        </div>
          <!--icon twitter-->
        <div class="flex justify-around inline-block w-1/3 p-3">
          <svg aria-hidden="true" focusable="false" data-prefix="fab" data-icon="twitter" class="svg-inline--fa fa-twitter text-blue-400 hover:text-blue-700 text-4xl" role="img" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512"><path fill="currentColor" d="M459.4 151.7c.325 4.548 .325 9.097 .325 13.65 0 138.7-105.6 298.6-298.6 298.6-59.45 0-114.7-17.22-161.1-47.11 8.447 .974 16.57 1.299 25.34 1.299 49.06 0 94.21-16.57 130.3-44.83-46.13-.975-84.79-31.19-98.11-72.77 6.498 .974 12.99 1.624 19.82 1.624 9.421 0 18.84-1.3 27.61-3.573-48.08-9.747-84.14-51.98-84.14-102.1v-1.299c13.97 7.797 30.21 12.67 47.43 13.32-28.26-18.84-46.78-51.01-46.78-87.39 0-19.49 5.197-37.36 14.29-52.95 51.65 63.67 129.3 105.3 216.4 109.8-1.624-7.797-2.599-15.92-2.599-24.04 0-57.83 46.78-104.9 104.9-104.9 30.21 0 57.5 12.67 76.67 33.14 23.72-4.548 46.46-13.32 66.6-25.34-7.798 24.37-24.37 44.83-46.13 57.83 21.12-2.273 41.58-8.122 60.43-16.24-14.29 20.79-32.16 39.31-52.63 54.25z"></path></svg>
        </div>
        <!--pesquisa e configurações desktop-->
        <div class="flex inline-block w-1/3 h-16 place-content-around">
          <input type="text" id="busca" class="px-3 py-1 my-4 mx-7 border-2 border-gray-700 rounded-full bg-gray-200 bg-opacity-10 placeholder-gray-900 placeholder-opacity-25 focus:placeholder-opacity-75" placeholder="Busca">
          <button v-for="bot in bott" class=" flex my-3 mx-1 pt-1.5 text-3xl text-blue-400 hover:bg-blue-50 hover:text-blue-700 rounded-full">
            <fa :icon="`${bot.icone}`" class="inline-block mx-2 -my-0.5"/>
          </button>
        </div>  
      </div>
    </nav>
    <div class="flex content-center max-w-screen-xl justify-around m-auto my-5">
      <!--perfil-->
      <div class="flex justify-around w-1/4 h-full border-2 border-gray-300 rounded-3xl bg-white shadow-md">
        <p>a</p>
      </div>
      <!--tweets section-->
      <div class="grid grid-cols-1 divide-y divide-black divide-opacity-20 w-2/5 h-full border-2 border-gray-300 rounded-3xl bg-white shadow-md px-2">
        <!--cabeçalho-->
        <div class="flex inline-block w-full justify-start">
          <p class="flex inline-block text-xl mt-2 mb-4 ml-2 font-semibold text-gray-400">Tweets</p>
        </div>
        <!--tweet-->
        <div v-for="tweet in tweets" class="flex w-full">
          <div class="flex inline-block">
            <img :src="`${tweet.src}`" alt="icones" class="flex inline-block w-14 h-14 m-1 rounded-full"/>
          </div>
          <div class="w-4/5 m-2">
            <div class="flex h-14">
              <p class="flex place-self-center inline-block mx-2">{{tweet.name}} </p>
              <p class="flex place-self-center inline-block mx-2">{{tweet.user}} </p>
            </div>
            <div class="grid grid-rows-1 nline-block">
              <p class="">{{tweet.text}} </p>
            </div>
          </div>
        </div>
      </div>
      <!--sugestions-->
      <div class="flex justify-around w-1/4 h-full border-2 border-gray-300 rounded-3xl bg-white shadow-md">
        <p>a</p>
      </div>
    </div>
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
        {icone: 'comments', id: 'messages'},
        {icone: 'wrench', id: 'settings'},
        {icone: 'pen', id: 'edit'},
      ],
      tweets: [
        {src: 'https://pbs.twimg.com/media/EcGdw6xXsAMkqGF.jpg',user: '@blackspider', name: 'Black Spider', text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Proin sollicitudin sem purus, at blandit leo cursus tincidunt. Vestibulum vulputate nulla nisi, vel ullamcorper ex tempor sed. Integer nec quam in erat ullamcorper dictum. Morbi interdum porta ipsum, a vestibulum lacus vulputate non. Donec congue lorem non euismod lobortis. Donec et.'},
        {src: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSVPX7Fm7yD7MHd1RpTo8OMc1fEY9xP7HsgMuIvb8TX59Q8MeCyDZhgWb21zqrIAfGDheg&usqp=CAU',user: '@eletricshock', name: 'Eletric Shock', text: 'lorem ipsum'},
        {src: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQlnCXSeYCzYx2nY3dx65tLM5PISB9eO-GyZh-AKfC8m8-FfkDrpaESTi8B7ZCc7BKvlow&usqp=CAU',user: '@strogest', name: 'Strongest', text: 'lorem ipsum'},
        {src: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcT7H_WYrpsbfP-KaeG1pMHKtOe9NulDKxVLUgztsFI5QdGxGheVpywIJnzP7G4Fu2k2lrw&usqp=CAU',user: '@coldfire', name: 'Cold Fire', text: 'lorem ipsum'},
        {src: 'https://pbs.twimg.com/media/EcGdw6xXsAMkqGF.jpg',user: '@blackspider', name: 'Black Spider', text: 'lorem ipsum'},
        {src: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSVPX7Fm7yD7MHd1RpTo8OMc1fEY9xP7HsgMuIvb8TX59Q8MeCyDZhgWb21zqrIAfGDheg&usqp=CAU',user: '@eletricshock', name: 'Eletric Shock', text: 'lorem ipsum'},
        {src: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQlnCXSeYCzYx2nY3dx65tLM5PISB9eO-GyZh-AKfC8m8-FfkDrpaESTi8B7ZCc7BKvlow&usqp=CAU',user: '@strogest', name: 'Strongest', text: 'lorem ipsum'},
        {src: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcT7H_WYrpsbfP-KaeG1pMHKtOe9NulDKxVLUgztsFI5QdGxGheVpywIJnzP7G4Fu2k2lrw&usqp=CAU',user: '@coldfire', name: 'Cold Fire', text: 'lorem ipsum'},
      ]
    }
  }
}
</script>
