<template>
  <div class="lg:w-1/5 border-r border-lighter lpx-2 lg:px-6 py-2 flex flex-col justify-between">
      <div>
        <button class="h-14 w-14 hover:bg-lightblue text-3xl rounded-full text-blue">
          <font-awesome-icon :icon="['fab', 'twitter']" class="icon alt" />
        </button>
      <div>
        <button 
          v-for="tab in tabs" 
          :key="tab.id"
          @click="id = tab.id"
          :class="`focus:outline-none hover:text-blue flex items-center py-2 px-4 hover:bg-lightblue rounded-full mr-auto mb-3 ${ id === tab.id?'text-blue': ''}`">
          <font-awesome-icon :icon="tab.icon" class="text-2xl mr-4 text-left" />
          <p class="text-lg font-semibold text-left hidden lg:block">{{ tab.title }}</p>
        </button>
        </div>
        <button class="text-white bg-blue rounded-full font-semibold focus:outline-none w-12 h-12 lg:h-auto lg:w-full m-1 p-3 hover:bg-darkblue">
          <p class="hidden lg:block">Tweet</p>
          <font-awesome-icon icon="fas fa-plus" class="lg:hidden" />
        </button>
      </div>
      <div class="lg:w-full relative">
        <button @click="dropdown = true" class="flex item-center w-full hover:bg-lightblue rounded-full p-2 focus:outline-none">
          <img src="../assets/profile.png" class="w-10 h-10 rounded-full border border-lighter"/>
          <div class="hidden lg:block ml-4">
            <p class="text-sm font-bold leading-tight">Random name</p>
            <p class="text-sm leading-tight"> @RandomTag</p>
          </div>
          <font-awesome-icon icon="fas fa-angle-down" class="ml-auto text-lg"/>
        </button>
        <div v-if="dropdown === true" class="absolute bottom-0 left-0 w-64 rounded-lg shadow-md border-lightest bg-white mb-16">
          <button @click="dropdown = false" class=" p-3 flex item-center w-full hover:bg-lightest p-2 focus:outline-none">
          <img src="../assets/profile.png" class="w-10 h-10 rounded-full border border-lighter"/>
          <div class="hidden lg:block ml-4">
            <p class="text-sm font-bold leading-tight"> Random name</p>
            <p class="text-sm leading-tight"> @RandomTag</p>
          </div>
          <font-awesome-icon icon="fas fa-check" class="ml-auto test-blue"/>
        </button>
        <button @click="dropdown = false" class="w-full text-left hover:bg-lightest border-t boreder-lighter p-3 text-sm focus:outline-none">
          Add an existing account
        </button>
         <button @click="dropdown = false" class="w-full text-left hover:bg-lightest border-t boreder-lighter p-3 text-sm focus:outline-none">
          Log out @RandomTag
        </button>
        </div>
      </div>
    </div>
</template>

<script>
export default {
    data: function() {
    return {
      tabs: [
        {icon: 'fas fa-house', title: 'Home', id:'home'},
        {icon: 'fa fa-hashtag', title: 'Explore', id:'explore'},
        {icon: 'fas fa-bell', title: 'Notifications', id:'notifications'},
        {icon: 'fas fa-envelope', title: 'Messages', id:'messages'},
        {icon: 'fas fa-bookmark', title: 'Bookmarks', id:'bookmarks'},
        {icon: 'fas fa-clipboard-list', title: 'Lists', id:'lists'},
        {icon: 'fas fa-user', title: 'Profile', id:'profile'},
        {icon: 'fas fa-ellipsis-h', title: 'More', id:'more'},
        
      ],
      id: 'home',
      dropdown: false,
    }
  }
}
</script>

<style>

</style>