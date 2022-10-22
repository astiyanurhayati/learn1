<template>

 <div class="container-fluid py-5" id="about">
    <div class="container">
        <div class="row align-items-center">
            <div class="col-lg-5 pb-4 pb-lg-0">
                <img src="../assets/ft1.png" alt="" class="img-fluid rounded" >
            </div>
            <div class="col-lg-7">
                <h1 class="text-uppercase text-primary mb-4">About Me</h1>
                <h3 class="mb-4">UI/UX Designer & Web Developer</h3>
                <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Repellat ipsa sit, porro obcaecati iure provident accusamus nesciunt! Quisquam nihil cupiditate cumque iure unde autem soluta, iste, officia tenetur aliquid, adipisci earum? Beatae assumenda distinctio natus quod accusamus iusto consectetur nobis?</p>
            </div>
            <div class="row mb-3">
                <div class="col-sm-6 py-2"><h6>Name: <span class="text-secondery text-capitalize">{{ user.phone }}</span></h6></div>
                <div class="col-sm-6 py-2"><h6>Phone: <span class="text-secondery text-capitalize">{{ user.name }}</span></h6></div>
                <div class="col-sm-6 py-2"><h6>Birthday: <span class="text-secondery text-capitalize">{{ user.birthday }}</span></h6></div>
                <div class="col-sm-6 py-2"><h6>Email: <span class="text-secondery text-capitalize">{{ user.email }}</span></h6></div>
                <div class="col-sm-6 py-2"><h6>Address: <span class="text-secondery text-capitalize">{{ user.address }}</span></h6></div>
            </div>
            <div class="col-sm-6 py-2">
                <h6>Freelance:</h6>
                <span class="text-secondery" v-if="user.freelance">Available</span>
                <span class="text-secondery" v-else>not Available</span>
            </div>
        </div>
    </div>
 </div>
</template>

<script>
import axios from 'axios'
export default {
    name: "AboutView",
    data(){
        return{
            user:{}
        }
    },
    mounted(){
        axios
        .get("http://localhost:3000/user")
        .then((response) => this.setData(response.data))
        .catch((error) => console.log("failed: ", error));
    },
    methods: {
        setData(data){
            this.user = data;
        }
    }
}
</script>