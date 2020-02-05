<template>
    <div>
        <div class="joke-card">
            <div class="card-block">
                <p><u>{{joke.setup}}</u></p>
                <p><em>{{joke.punchline}}</em></p>
            </div>
            <button class="btn btn-danger" @click="delJoke">Delete</button>
        </div>
        
    </div>
</template>
<script>
import {mapActions} from 'vuex'
export default {
    props : ['joke', 'index'],
    methods: mapActions([
        'delJoke'
    ]),
}
</script>