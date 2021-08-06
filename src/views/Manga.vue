<template>
<div class="container mt-3">
    <div class="row">
        <div class="col-12">
            <h1 class="text-center text-uppercase">Manga Section</h1>
        </div>
    </div>
    <div class="row mt-3">
        <form @submit.prevent="handleManga">
            <input type="search" class="form-control" placeholder="search manga section....." v-model="search_manga" />
        </form>
    </div>
    <div class="row mt-4">
        <!-- {{manga_list.results}} -->
        <CardMangaComponent v-for="manga in manga_list.results" :key="manga.mal_id" :manga="manga" />
    </div>
</div>
</template>



<script>
import { ref } from 'vue';
import CardMangaComponent from '../components/CardMangaComponent';
export default{
    name : 'Manga',
    components:{
        CardMangaComponent,
    },
    setup(){
        const search_manga = ref("");
        const manga_list = ref({});
        
        const handleManga = async ()=>{
            const resp = await fetch(`https://api.jikan.moe/v3/search/manga?q=${search_manga.value}`);
            manga_list.value = await resp.json();
            search_manga.value = "";
        };

        return { search_manga, manga_list, handleManga, CardMangaComponent }
    }
};
</script>
