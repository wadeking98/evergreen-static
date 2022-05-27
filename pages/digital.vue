<template>
    <div>
        <PageComponent title="Digital Art" :json="json" imageFolder="Digital Art"/>
    </div>
</template>
<script>
import PageComponent from '@/components/PageComponent.vue'
import json from '@/assets/DigitalWorks.json'
export default {
    name: 'DigitalPage',
    components: {
        PageComponent
    },
    data(){
        return{
            json:json
        }
    }
}
</script>