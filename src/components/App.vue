<template>
    <div id='app'>
        <h3> Got jokes </h3>
        <button class="btn btn-primary" @click="initJokes">Add 10 Jokes</button>
        <button class="btn btn-primary" @click="addJoke">Add 1 Jokes</button>
        <br>
            <span v-for="(type,index) in types" :key="index">
                <input 
                    type="checkbox" 
                    :value="type" 
                    v-model="checkedTypes"
                    checked
                >
                <label>{{type}}</label> &nbsp;
            </span>
        <br>
        <br>
        <div class="col-md-12">
            <Joke  class="col-md-4"
                v-for="(joke, index) in $store.state.jokes"
                v-show="checkedTypes.includes(joke.type)"
                :joke="joke"
                :index="index"
                :key="index"

            />
            
        </div>
        
    </div>
</template>

<script>
import {mapActions} from 'vuex'
import Joke from './Joke.vue'

export default {
    data() {
        return {
            types : ['programming', 'general', 'knock-knock'],
            checkedTypes : ['programming', 'general', 'knock-knock']
        }
    },
    methods: mapActions([
        'initJokes',
        'addJoke'
    ]),
    components: {
        Joke
    }
}
</script>

<style>

</style>