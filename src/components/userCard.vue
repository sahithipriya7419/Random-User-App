<template>
    <div class="card border-primary">
        <div class="card-body text-center">
            <img 
            :src="user.picture?.large" height="150" width="150" class="rounded-circle img-thumbnail border-danger zoomIn">
            <div class="card-title text-primary">
                <h3>
                    <span class="pl-2">{{user.name?.title}}</span>
                    <span class="pl-2">{{user.name?.first}}</span>
                    <span class="pl-2">{{user.name?.last}}</span>
                </h3>
                <h6>
                    <span class="fa-solid fa-envelope fa-1x text-dark"></span>
                    <span class="pl-2 text-dark">{{user.email}}</span>
                </h6>
                <h6>
                    <span class="fa-solid fa-location-dot text-black"></span>
                    <span class="pl-2 text-dark">{{user.location.city}}</span>
                    <span class="pl-2 text-dark">{{user.location.country}}</span>
                    <span class="pl-2 text-dark">{{user.location.postcode}}</span>
                </h6>
                <h6>
                    <span class="fa-solid fa-phone-flip pl-2 text-dark"></span>
                    <span class="pl-2 text-dark">{{user.phone}}</span>
                </h6>
                <p>
                    <span class="pt-3 text-secondary">Registered on {{user.registered.date}}</span>
                </p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name:"userCard",
    props:["user"]
}
</script>

<style>

</style>