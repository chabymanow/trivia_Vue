<template>
    <div>
        <h1>Choose a category:</h1>
        <div>
            <select @change="onChange($event)" class="form-control">
                <option v-for="(value, key) in categories[0]" :key="{key}" :value="key">
                    {{value}}
                </option>
            </select>
        
            <button @click="getData()">Get question</button>
        </div>
    </div>
</template>

<script>
    export default{
        name: 'GetTrivia',
        props:{
            categories: [],
        },
        data(){
            return{
                category: "general"
            }
        },
        methods:{
            async getData(){
                if(this.category == ""){
                    this.category = "general"
                }
                console.log(this.category);
                const URL = 'https://api.api-ninjas.com/v1/trivia?category='+this.category;
                const headers = { 'X-Api-Key': 'GET_YOUR_API_KEY' };
                const res = await fetch(URL, { headers } )
                const results = await res.json()
                console.log(results)
                this.$emit('getData', results)
            },

            onChange(event) {
                this.category = event.target.value;
                
            },
        }
    }
</script>

<style scoped>
h1{
    font-size: 3rem;
}

select, button{
    font-size: 1.3rem;
    padding: .3rem 1rem;
}

</style>