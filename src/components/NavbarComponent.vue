<template>
    <nav class="navbar fixid-top shadow-sm navbar-expand-lg bg-light navbar-light py-3 py-lg-0 px-lg-5 d-flex justify-content-between">
        <router-link class="navbar-brand ml-lg-3" to="/"></router-link>
        <h4 class="m-0" style="font-size: 2.5rem;">
            <span class="text-primary">MY </span> Profile
        </h4>
        <router-link class="btn btn-outline-info" to="/contact">Contact Me</router-link>
    </nav>
</template>
<script>
export default {
    name: "NavbarComponent"
}
</script>