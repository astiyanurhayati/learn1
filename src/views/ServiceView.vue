<template>
    <div class="container-fluid pt-5" id="service" >
        <div class="container">
            <div class="service-h4 position-relative d-flex align-items-center justify-content-center">
                <h1 class="mb-5 text-uppercase text-primary">My SErvice</h1>
            </div>
            <div class="d-flex justify-content-center pb-3">
                <div class="service-box w-25 text-center mb-5" v-for="(service, index) in services" :key="index">
                    <div class="d-flex align-items-center justify-content-center mb-4">
                        <div class="fa fa-2x fa-laptop-code service-icon blue text-white m-2 p-">
                            <h4 class="font-weight-bold m-0 text-capitalize">{{ service.name }}</h4>
                            <p>{{ service.desc  }}</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
import axios from "axios"
export default{
    name: "ServicePage",
    date(){
        return {
            services: []
        }
    },
    mounted(){
        axios
            .get("http://localhost:3000/services")
           .then((response)=> this.setData(response.data))
           .catch((error)=> console.log("failed: ", error));
    }
}
</script>