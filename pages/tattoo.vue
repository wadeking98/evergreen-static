<template>
    <div>
        <PageComponent title="Tattoo Design" :json="json" imageFolder="Tattoo" :download="true"/>
    </div>
</template>
<script>
import PageComponent from '@/components/PageComponent.vue'
import json from '@/assets/TattooWorks.json'
export default {
    name: 'TattooPage',
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