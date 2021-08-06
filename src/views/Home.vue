<template>
<div class="container mt-3">
  <div class="row">
    <div class="col-12">
      <h1 class="text-center">
        The <strong>Anime</strong> Database
      </h1>
    </div>
  </div>
  <div class="row mt-3">
    <div class="col-12">
      <form @submit.prevent="handleSearch">
        <div class="col-12">
          <input 
            type="search"
            placeholder="search anime......"
            class="form-control"
            required 
            v-model="search_query" />
        </div>
      </form>
    </div>
  </div>
  <div class="row" v-if="anime_list.length > 0">
    <CardComponent v-for="anime in anime_list" :key="anime.mal_id" :anime="anime" />
  </div>
  <div class="row mt-3" v-else>
    <h1 class="text-center lead">Sorry, we have no result.....</h1>
  </div>
</div>
</template>

<script>
// @ is an alias to /src
import CardComponent from '../components/CardComponent';
import {ref} from 'vue';
export default {
  name: 'Home',
  components: {
    CardComponent,
  },
  setup(){
    const search_query = ref("");
    const anime_list = ref([]);
    const handleSearch = async()=>{
      anime_list.value = await fetch(`https://api.jikan.moe/v3/search/anime?q=${search_query.value}`).then(res=>res.json()).then(data=>data.results)
      console.log(anime_list.value);
      search_query.value = "";
    }
    return { CardComponent, search_query, anime_list, handleSearch}
  }
}
</script>
