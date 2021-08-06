<template>
<div class="col-12 col-sm-12 col-md-6 col-lg-4">
    <div class="card border-light  mt-3">
    <img :src="anime.image_url" class="img-fluid mt-3" alt="...">
    <div class="card-body">
        <h5 class="card-title text-center">{{anime.title}}</h5>
        <p class="card-text">{{anime.synopsis}}</p>
        <p>
            Tipo : <span class="muted">{{anime.type}} </span>
            &nbsp;&nbsp;Score: <span class="muted">{{anime.score}}</span>
            &nbsp;&nbsp;Episodes: <span class="muted">{{anime.episodes}}</span>
            Rated: <span class="muted">{{anime.rated}}</span>
            &nbsp;&nbsp;End date: <span class="muted">{{FechaNormal}}</span>
        </p>
        <a :href="anime.url" class="btn btn-dark" target="_blank">Go to myanimelist</a>
    </div>
    </div>
</div>
</template>

<script>
export default{
    name : 'CardComponent',
    props:['anime'],
    computed: {
        FechaNormal(){
            let b = new Date(this.anime.end_date);
            b = b.toLocaleDateString();
            return b;
        }
    }
};
</script>
