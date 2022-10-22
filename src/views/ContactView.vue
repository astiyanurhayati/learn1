<template>

    <div class="container-fluid py-5" id="contact">
        <div class="container">
            <div class="position-relative d-flex align-items-center justify-content-center">
                <h1 class="mb-5 text-uppercase text-primary">contact Me</h1>
            </div>
            <div v-if="error" class="alert alert-danger" style="margin-bottom: 35px !important" role="alert">
                Silahkan untuk mengisi keseluruhan data terlebih dahulu.
            </div>
            <div v-if="success" class="alert alert-success" style="margin-bottom: 25px !important" role="alert">
                Pesan anda telah berhasil terkirim!
            </div>
        </div>
        <div class="row justify-content-center">
            <div class="col-lg-8">
                <div class="contant-form text-center">
                    <div id="success"></div>
                    <div name="sentMessage" id="contactForm">
                        <div class="row">
                            <div class="control-group col-sm-6">
                                <input type="text" class="form-control p-4" v-model="data.name" id="name" placeholder="Your Name">
                                <p class="help-block text-denger"></p>
                            </div>
                            <div class="control-group col-sm-6">
                                <input type="email" class="form-control p-4" v-model="data.email" id="email" placeholder="Your Email">
                                <p class="help-block text-denger"></p>
                            </div>
                            <div class="control-group col-sm-6">
                                <input type="text" class="form-control p-4" v-model="data.subject" id="subject" placeholder="Subject">
                                <p class="help-block text-denger"></p>
                            </div>

                            <div class="control-group col-sm-6">
                                <input type="text" class="form-control p-4" v-model="data.message" id="message" placeholder="Message" row="5">
                                <p class="help-block text-denger"></p>
                            </div>
                        </div>
                        <a href="" class="btn btn-outline-info" @click="sendMessage" id="sendMessageButton">Send Message</a>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>

import axios from 'axios'
export default {
    name: "ContactPage",
    data(){
        return{
            data: {
                name: '',
                email: '',
                subject: '',
                message: ''

            },
            error: false,
            success: false
        }
    },
    methods:{
        sendMessage(){
            if(this.data.name && this.data.email && this.data.subject && this.data.message){
                axios
                .post("http://localhost:3000/message", this.date)
                .then(()=> this.clearForm())
                .catch((err) => console.log(err));
            }else{
                this.error = true;
            }
        },
        clearForm(){
            this.success = true;
            this.data.name = '';
            this.data.email = '';
            this.data.subject = '';
            this.data.message = '';

        }
    }
}
</script>