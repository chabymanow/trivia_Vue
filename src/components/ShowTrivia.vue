<template>
    <div>
        <p>{{ question }}</p>
        <button @click="show = !show" :set="show = false">Show answer</button>
        <Transition>
        <p v-if="show">{{ answer }}</p>
        </Transition>
    </div>
</template>

<script>
    export default{
        name: "ShowTrivia",
        props:{
            question: {type: String, default: ""},
            answer: {type: String, default: ""},
        },
        data() {
            return {
                show: false
            }
        }
    }
</script>

<style>
.v-enter-active,
.v-leave-active {
  transition: opacity 0.5s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}

select, button{
    font-size: 1.3rem;
    padding: .3rem 1rem;
}

p{
    font-size: 1.4rem;
    font-weight: 600;
    color: #1f1c25;
}
</style>