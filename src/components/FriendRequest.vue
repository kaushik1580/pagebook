<template>
    <div style="margin-right:200px">
        <v-card  class="frnd" elevation="100" justify="center" outlined max-width="8000" v-for="request in requests" :key="request.requestId">
        <v-row justify="center">
        <v-avatar @click="toPost(post.postDTO.postId)" size= 100>
            <img :src="request.profileImage" alt="John" class="img">
        </v-avatar>
        </v-row>
        <v-card-title @click="toProfile(request.userId)" class="ma-4">
            {{request.userName}}
            </v-card-title>
        <v-btn class="ma-4" color="#f95e49" dark @click="func(1, request)">
            Accept
            <v-icon dark right> mdi-checkbox-marked-circle</v-icon>
        </v-btn>
        <v-btn class="ma-3" color="red" dark @click="func(3, request)">
            Decline
            <v-icon dark right>
            mdi-cancel
            </v-icon>
        </v-btn>
        </v-card>
    </div>
</template>

<script>
import Vue from 'vue'
import axios from 'axios'
import VueAxios from 'vue-axios'
import jwtdecode from 'jwt-decode'
Vue.use(VueAxios, axios);
export default {
    name: "FriendRequest",
    data(){
        return{
            uid: jwtdecode(localStorage.getItem("token")).userId,
            requests: undefined,
            request_resp: {
                "requestId": null,
                "senderId": null,
                "receiverId": null,
                "status": null
            }
        }
    },
    mounted() {
        const uid = this.uid
        Vue.axios.get(`http://10.177.1.179:7081/pb/user/getFriendRequests/${uid}`)
        .then((resp) => {
            console.log(uid)
            console.log(resp.data)
            this.requests = resp.data
        })
    },
    methods: {
    toProfile(id){
        console.log(id)
            this.$store.state.friendId = id
            console.log(id)
            this.$router.push(this.$router.push({path: `/np/`}))
        },
        func: function(val, request){
            this.request_resp.requestId = request.requestId
            this.request_resp.senderId = request.userId
            this.request_resp.receiverId = this.uid
            this.request_resp.status = val
            console.log(this.request_resp)
            Vue.axios.post('http://10.177.1.179:7081/pb/user/updateFriendRequest', this.request_resp)
            .then((resp) => {
                console.log(resp)
            })
        }
    }
}
</script>