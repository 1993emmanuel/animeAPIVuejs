<template>
<div class="container mt-4">
    <div class="row">
        <div class="col-12"><h2 class="text-center">Character Search</h2></div>
    </div>
    <div class="row mt-2">
        <form @submit.prevent="handleCharacter">
            <input 
                type="search"
                placeholder="character search......"
                class="form-control"
                v-model="character_query"
            />
        </form>
    </div>
    <div class="row mt-2">
        <CharacterCardComponent v-for="character in character_list.results" :key="character.mal_id" :character="character" />
    </div>
</div>    
</template>

<script>
import {ref} from 'vue';
import CharacterCardComponent from '../components/CharacterCardComponent';
export default {
    name : 'Characters',
    components:{
        CharacterCardComponent
    },
    setup(){
        const character_query = ref("");
        const character_list = ref({});

        const handleCharacter = async()=>{
            const resp = await fetch(`https://api.jikan.moe/v3/search/character?q=${character_query.value}`);
            character_list.value = await resp.json();
            // console.log(character_list.value.results)
            character_query.value = "";
        };
        
        return{ character_query, character_list,  CharacterCardComponent, handleCharacter }
    }
};
</script>
