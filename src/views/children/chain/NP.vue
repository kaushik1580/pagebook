<template>
  <div>
    <!---------------------------------------------------- PROFILE USER ID --------------------------------------------------------------------->
    <NP1/>
<!---------------------------------------------------- PROFILE POST CARD --------------------------------------------------------------------->    
  <DisplayPost2/>
  <!-- <Comments/> -->
  </div>
</template>
<script>
// import Vue from 'vue'
// import axios from 'axios'
// import VueAxios from 'vue-axios'
// Vue.use(VueAxios, axios);
// import jwtdecode from 'jwt-decode'

import NP1 from '../../../components/NP1.vue'
import DisplayPost2 from '../../../components/DisplayPost2.vue'
// import Comments from '../../../components/Comments.vue'
export default {
  name: 'Profile',
  components: {
    NP1,
    DisplayPost2,
    // Comments
  },
  // data () {
  //   return{
  //   userId: jwtdecode(localStorage.getItem("token")).userId,
  //   userData: undefined,
  //   posts: {
  //     "userId" : this.userId,
  //     "postText" : "",
  //     "postUrl" : "",
  //     "postType" : 1,
  //     "postCategory" : "General",
  //     "timestamp" : 1234567891,
  //     "sharedPostId" : null
  // },
  // displayPosts: undefined,
  // links: {
  //   'hearts': '/hearts',
  //   'likes': '/likes',
  //   'dislikes': '/dislikes',
  //   'angry': '/angry'
  // },
  // curr_reaction: 0,
  // react_data: {
  //   "postId" : null,
  //   "reactionType" : null,
  //   "userId" : this.userId
  // },
  // reaction_data: {
  //   1: "likes",
  //   2: "dislikes",
  //   3: "angry",
  //   4: "hearts"
  // },
  //   loading: false,
  //   selection: 1,
  //   }
  // },
  // mounted() {
  //   // const uid = this.userId
  //   // Vue.axios.get(`http://10.177.1.179:7081/pb/user/myProfile/${uid}`)
  //   //   .then((resp) => {
  //   //     this.userData = resp.data
  //   //     console.log(resp.data)
  //   //   })
  //   // Vue.axios.get(`http://10.177.1.69:8081/pb/post/getUserPosts/${uid}`)
  //   //   .then((resp) => {
  //   //     this.displayPosts = resp.data
  //   //     console.log(resp.data)
  //   //   })
  //   // Vue.axios.get(`http://10.177.1.69:8081/pb/story/getFriendsStories/${uid}`)
  //   //   .then((resp) => {
  //   //     this.stories = resp.data
  //   //     console.log("LOLLLLL");
  //   //     console.log(resp.data)
  //   //   })
  // },
  // methods: {
  //   reserve () {
  //     this.loading = true

  //     setTimeout(() => (this.loading = false), 2000)
  //   },
  //   func: function(val, index){
  //   this.react_data.userId = this.displayPosts[index].postDTO.userDTO.userId
  //   this.react_data.postId = this.displayPosts[index].postDTO.postId
  //   this.react_data.reactionType = val
  //   console.log(this.react_data)
  //   this.axios.post(`http://10.177.1.69:8081/pb/reaction/updateReaction`, this.react_data)
  //     .then((resp) => {
  //       console.log(resp)
  //     })
  //   // console.log(this.curr_reaction !== val )
  //   // console.log(this.displayPosts.)
  //   if(this.curr_reaction !== val){
  //     if(this.curr_reaction !== 0){
  //       this.displayPosts[index].reactionsDTOS[this.curr_reaction-1].count = this.displayPosts[index].reactionsDTOS[this.curr_reaction-1].count-1
  //     }
  //         this.displayPosts[index].reactionsDTOS[val-1].count = this.displayPosts[index].reactionsDTOS[val-1].count+1
  //           // console.log(this.displayPosts[index].reactionsDTOS[this.curr_reaction-1].count)
  //          this.curr_reaction = val
  //     }
  //     else{
  //       this.displayPosts[index].reactionsDTOS[val-1].count = this.displayPosts[index].reactionsDTOS[val-1].count-1
  //       this.curr_reaction = 0
  //     }
  //   },
  //   postData (e) {
  //     this.posts.timestamp = Date.now()
  //     console.log(this.posts.timestamp)
  //     this.axios.post('http://10.177.1.69:8081/pb/post/addPost', this.posts)
  //       .then((resp) => {
  //         console.log(resp.data)
  //         // if (resp.data) {
  //         //   this.$router.push('/home')
  //         // }
  //       })
  //       .catch(error => alert(error))
  //     e.preventDefault()
  //   }
  // }
}
</script>
<style scoped>
.mx-auto{
  width: 60%;
  margin-top: 50px;
  height: 50%;
}
.pimg{
  height: 20px;
  width: 30px;
}
</style>