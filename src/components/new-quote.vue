<template>
    <form @submit.prevent="onSubmited">

        <div class="form-group">
            <label for="content">Content</label>
            <input type="text" name="content" id="content" class="form-control" v-model="quoteContent">
        </div>

        <button class="btn btn-primary">Submit</button>
    </form>
</template>
<script>
    import axios from 'axios';

    export default{
        data(){
            return {

                quoteContent: ''
            }
        },
        methods: {

            onSubmited(){

                axios.post('http://127.0.0.1:8000/api/quote/',
                        {content: this.quoteContent})
                        .then(function (response) {

                            console.log(response);

                        }).catch(function (error) {

                    console.log(error);

                });
            }
        }
    }
</script>