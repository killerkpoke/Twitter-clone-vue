<template>
  <div class="w-auto h-full overflow-y-scroll">
    <div class="px-5 py-3 border-b border-lighter flex items-center justify-between">
        <h1 class="text-xl font-bold">Home</h1> 
        <font-awesome-icon icon="far fa-star" class="text-blue text-xl" />
    </div>
    <div class="px-5 py-3 border-b-8 border-lighter flex">
        <div class="flex-none">
            <img src="../assets/profile.png" class="flex-none w-12 h-12 rounded-full border border-lighter" />
        </div>
        <form v-on:submit.prevent="addNewTweet" class="w-full px-4 relative">
            <textarea v-model="content.tweet" placeholder="What's up?" class="mt-3 pb-3 w-full focus:outline-none"/>
            <div class="flex items-center">
                <font-awesome-icon 
                    v-for="x in logos" 
                    :key="x.logo" 
                    :icon="x.logo" 
                    class="text-blue text-lg mr-4" />
            </div>
            <button type="submit" class="bottom-0 right-0 absolute rounded-full h-10 px-4 text-white font-semibold bg-blue hover:bg-darkblue focus:outline-none">
                Tweet
            </button>
        </form>
    </div>
    <div class="flex flex-col-reverse">
        <div v-for="follow in tweets" :key="follow.id" class="w-full p-4 border-b hover:bg-lighter flex">
            <div class="flex-none mr-4">
                <img src="../assets/profile.png" class="h-12 w-12 rounded-full flex-none"/>
            </div>
            <div class="w-full">
                <div class="flex items-center w-full">
                    <p class="font-semibold">{{ follow.name }}</p>
                    <p class="text-sm text-dark ml-2">{{ follow.handle }}</p>
                    <p class="text-sm text-dark ml-2">{{ follow.time }}</p>
                    <font-awesome-icon icon="fas fa-angle-down" class="text-dark ml-auto"/>
                </div>
                <p class="py-2">{{ follow.tweet }}</p>
                <div class="flex items-center justify-between w-full">
                    <div class="flex items-center text-sm text-dark">
                        <font-awesome-icon icon="far fa-comment" class="mr-3"/>
                        <p class="">{{ follow.comments }}</p>
                    </div>
                    <div class="flex items-center text-sm text-dark">
                        <font-awesome-icon icon="fas fa-retweet" class="mr-3"/>
                        <p class="">{{ follow.retweets }}</p>
                    </div>
                    <div class="flex items-center text-sm text-dark">
                        <font-awesome-icon icon="fas fa-heart" class="mr-3"/>
                        <p class="">{{ follow.like }}</p>
                    </div>
                    <div class="flex items-center text-sm text-dark">
                        <font-awesome-icon icon="fas fa-share-square" class="mr-3"/>
                    </div>
                </div>
            </div>
        </div>
    </div>
  </div>
</template>

<script>
export default {
    data: function(){
        return {
            logos: [
                {logo: 'far fa-image'},
                {logo: 'fas fa-film'},
                {logo: 'far fa-chart-bar'},
                {logo: 'far fa-smile'},
            ],
            tweets: [
                {id:'1', src: '', name:'Random name 1', handle:'@RandomTag_1', time:'32 min', tweet:'Get reckted', comments:'87', retweets:'123', like:'514'},
                {id:'2', src: '', name:'Random name 2', handle:'@RandomTag_2', time:'32 min', tweet:'Get lolled', comments:'634', retweets:'274', like:'457'},
                {id:'3', src: '', name:'Random name 3', handle:'@RandomTag_3', time:'32 min', tweet:'Get a kinder chocolate :3', comments:'827', retweets:'1213', like:'2543'},
            ],
            content: {
                id:'4',
                src: '', 
                name:'Kpoke', 
                handle:'@kpoke',
                time:'1 min', 
                tweet:'', 
                comments:'0',
                retweets:'0',
                like:'3'
            },
        }
    },
    methods:{
        addNewTweet() {
            if (this.content.tweet === '') return;
           
            let new_tweet = {
                src: this.content.src, 
                name: this.content.name, 
                handle: this.content.handle,
                time: this.content.time, 
                tweet: this.content.tweet, 
                comments: this.content.comments,
                retweets: this.content.retweets,
                like: this.content.like,
            };
            this.tweets.push(new_tweet);
            this.content.tweet='';
        }
    }
}
</script>

<style>

</style>