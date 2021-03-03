<template>
  <div>
    <div class="w-56">
      <div class=" bg-black h-full flex-none"> <!-- sidenav -->
        <div class="p-3">
          <img src="/img/logo_white.png" alt="spotify-logo" class="h-10 mb-4">
          <div class="mb-5">
            <button v-for="page in pages" v-bind:key="page.name" @click="setID = page.id"
                :class="`w-full focus:outline-none text-sm font-semibold rounded px-3 py-2 flex items-center
                      justify-start ${setID === page.id ? 'bg-light text-white' : 'text-lightest'}`">
                <i class="material-icons mr-3"> {{page.icon}} </i>
                <p>{{page.name}}</p>
            </button>
          </div>
          <div class="mx-3">
            <h1 class="text-xs font-semibold text-lightest tracking-widest uppercase mb-4">playlists</h1>
            <button class="flex items-center justify-start opacity-75 hover:opacity-100 mb-4">
              <img src="/img/create_playlist.png" alt="create playlist" class="h-8 w-8">
              <p class="text-sm text-white font-semibold ml-3">Create Playlist</p>
            </button>
            <button class="flex items-center justify-start opacity-75 hover:opacity-100">
              <img src="/img/liked_songs.png" alt="liked songs" class="h-8 w-8">
              <p class="text-sm text-white font-semibold ml-3">Liked Songs</p>
            </button>
            <div class="h-px w-full bg-light my-3"></div>
            <div class="mx-3">
              <div class="w-full h-48 overflow-y-scroll">
                <p v-for="album in albums" v-bind:key="album.name"
                  class="text-lightest hover:text-white text-sm font-medium py-3"> {{album.name}}</p>
              </div>
              <button class="flex items-center justify-start text-lightest hover:text-white py-2">
                <i class="material-icons mr-3 rounded-full border border-lightest">arrow_downward</i>
                <p class="text-sm font-semibold">Install App</p>
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- <div class="col-start-2 col-end-7 bg-blue"> -->
      <div class="w-full h-full relative">
        <div class="w-full sticky top-0 py-3 px-10 flex items-center justify-between">

          <div class="flex items-center">
            <button class="rounded-full bg-black w-8 h-8 text-white mr-4">
              <i class="material-icons text-3xl">keyboard_arrow_left</i>
            </button>
            <button class="rounded-full bg-black w-8 h-8 text-white">
              <i class="material-icons text-3xl">keyboard_arrow_right</i>
            </button>
          </div>

          <div>
            <!-- <button class="border-white border-opacity-100 rounded-full py-3 px-6">
              <p class="text-white uppercase">upgrade</p>
            </button> -->
            <button class="border-white border-opacity-100 rounded-full py-3 px-6 flex items-center">
              <img src="/img/myPic.jpg" alt="my profile picture" class="rounded-full h-8 w-8 mr-2">
              <p class="text-white font-semibold text-sm">indirapravianti</p>
            </button>
          </div>

        </div>
      </div>
    <!-- </div> -->
  </div>
</template>

<script>
export default {
  name: 'Sidenav',
  data: function() {
    return {
      pages: [
        {id: 'home', name:'Home', icon: 'home'},
        {id: 'search', name:'Search', icon: 'search'},
        {id: 'library', name:'Your Library', icon: 'bar_chart'}
      ],
      setID: 'home',
      albums: [
        {name: 'all time faves'},
        {name: 'rnb'},
        {name: 'what you did'},
        {name: 'old faves'},
        {name: 'a callow romantic'},
        {name: 'mixer'}
      ]
    };
  }
}
</script>
