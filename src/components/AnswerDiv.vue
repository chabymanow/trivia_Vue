<template>
    <div>
        <ShowTrivia :question=question :answer=answer />
    </div>
</template>

<script>
import ShowTrivia from '@/components/ShowTrivia.vue'

export default {
  name: 'AnswerDiv',
    props:{
        question: {type: String, default: ""},
        answer: {type: String, default: ""},
    },
    components: {
    ShowTrivia
    }
}
</script>
