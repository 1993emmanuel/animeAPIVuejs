<template>
<div class="col-12 col-sm-12 col-md-6 col-lg-4">
    <div class="card border-success mt-4">
    <img :src="manga.image_url" class="card-img-top img-fluid" :alt="manga.title+' Poster'">
    <div class="card-body">
        <h5 class="card-title">
            {{manga.title}}
        </h5>
        <p class="card-text text-center">{{manga.synopsis}}</p>
        <p>
            Chapters :<span>{{manga.chapters}}</span>
            &nbsp;&nbsp;Score :<span>{{manga.score}}</span>
            &nbsp;&nbsp;Type :<span>{{manga.type}}</span>
        </p>
        <a :href="manga.url" class="btn btn-dark">Go to myanimelist</a>
    </div>
    </div>
</div>
</template>


<script>
export default{
    name : 'CardMangaComponent',
    props:['manga'],
};
</script>
