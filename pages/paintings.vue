<template>
    <div>
        <PageComponent title="Paintings" :json="json" imageFolder="Paintings"/>
    </div>
</template>
<script>
import PageComponent from '@/components/PageComponent.vue'
import json from '@/assets/PaintingWorks.json'
export default {
    name: 'PaintingPage',
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