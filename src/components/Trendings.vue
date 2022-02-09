<template>
  <div class="md:block hidden w-1/3 h-full border-l border-lighter py-2 px-6 overflow-y-scroll relative">
    <input class="rounded-full w-full p-2 bg-lighter mb-2 pl-12 text-sm" placeholder="Search Twitter" />
    <font-awesome-icon icon="fas fa-search" class="absolute text-light left-0 top-0 mt-5 ml-12 text-sm" />  
    <div class="w-full rounded-lg bg-lightest">
        <div class="flex items-center justify-between p-3"> 
            <p class="text-lg font-bold">Trend for You</p>
            <font-awesome-icon icon="fas fa-cog" class="text-blue text-lg" />
        </div>
        <button 
            v-for="trend in trendings" 
            :key="trend.top" 
            class="w-full flex justify-between hover:bg-lighter p-3 border-t border-lighter">
        <div>
            <p class="text-sm text-left leading-tight text-dark">{{ trend.top }}</p>
            <p class="font-bold text-left leading-tight">{{ trend.title }}</p>
            <p class="text-left leading-tight text-dark">{{ trend.bottom }}</p> 
        </div>
        <font-awesome-icon icon="fas fa-angle-down" class="text-lg text-dark" />
        </button>
        <button class="p-3 w-full hover:bg-lighter text-left text-blue border-t border-lighter">
            Show More
        </button>
    </div>

    <div class="w-full rounded-lg bg-lightest my-6">
        <div class="p-3"> 
            <p class="text-lg font-bold">Who Follow</p>
        </div>
        <button v-for="friend in friends" :key="friend.top" class="w-full flex hover:bg-lighter p-3 border-t border-lighter">
            <img src="../assets/profile.png" class="w-12 h-12 rounded-full border border-lighter"/>
            <div class="hidden lg:block ml-4">
                <p class="text-sm font-bold leading-tight">{{ friend.name }}</p>
                <p class="text-sm leading-tight">{{ friend.handle }}</p>
            </div>
            <button class="ml-auto text-sm text-blue py-1 px-4 rounded-full border-2 border-blue">
                Follow
            </button> 
        </button>
        
        <button class="p-3 w-full hover:bg-lighter text-left text-blue border-t border-lighter">
            Show More
        </button>
    </div>
  </div>
</template>

<script>
export default {
    data: function() {
        return {
            trendings: [
                {top: 'Trending in BP', title: 'Gigi', bottom: 'Trending with: Rip Gigi'},
                {top: 'Music', title: 'We Won', bottom: '125K Tweets'},
                {top: 'Rock', title: 'Metalica', bottom: '65k Tweets'},
                {top: 'Trending in US', title: 'Elon Musk', bottom: '40K Tweets'},
                {top: 'Trending', title: 'Basic David', bottom: '23.4k Tweets'},
            ],
            friends: [
                {src: '', name: 'qwe', handle: '@random_1'},
                {src: '', name: 'asd', handle: '@random_2'},
                {src: '', name: 'lol', handle: '@random_3'},
            ],
        }
    }
}
</script>

<style>

</style>