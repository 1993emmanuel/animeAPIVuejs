<template>
<div class="col-12 col-sm-12 col-md-6 col-lg-4">
    <div class="card border-light  mt-3">
    <img :src="character.image_url" class="img-fluid mt-3" :Lalt="character.name+' Poster'">
    <div class="card-body">
        <h5 class="card-title text-center">{{character.name}}</h5>
        <a :href="character.url" class="btn btn-dark" target="_blank">Go to myanimelist</a>
    </div>
    </div>
</div>
</template>


<script>
export default{
    name : 'CharacterCardComponent',
    props: ['character'],
};
</script>


