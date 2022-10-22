<template>
   <div class="container-fluid blue d-flex align-items-center mb-5 py-3" id="home" style="min-height: 100vh">
    <div class="container">
        <div class="row align-items-center">
            <div class="col-lg-7 text-center text-left">
                <h3 class="text-white font-weight-normal mb-3">Hello, my name</h3>
                <h1 class="display-3 text-uppercase text-primary mb-2" style="-webkit-text-stroke: 4px #ffffff">{{ data.name }}</h1>
                <div class="d-flex align-items-center justify-content-center justify-content-lg-start pt-5">
                    <a href="#" target="_blank" class="btn btn-white m-auto" download>Downlod CV</a>
                </div>
            </div>
            <div class="col-lg-5 px-8 pl-lg-0 pb-5 pb-lg-4 about-img">
                <img src="../assets/f2.jpg" alt="" class="img-fluid rounded-circle shadow-sm pt-5 m-auto" style="width: 400px">
            </div>
        </div>
    </div>
   </div>
</template>

<script>
import axios from "axios";
export default {
    name: "HeaderPage",
    data(){
        return{
            data:{}
        }
    },
    mounted(){
        axios
        .get('http://localhost:3000/user')
        .then((response) => this.setData(response.data))
        .catch((error)=> console.log("failed: ", error));
    },
    methods: {
        setData(data){
            this.data = data;
        }
    }
}
</script>