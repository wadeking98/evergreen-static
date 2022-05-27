<template>
    <div>
        <PageComponent title="Murals" :json="json" imageFolder="Mural"/>
    </div>
</template>
<script>
import PageComponent from '@/components/PageComponent.vue'
import json from '@/assets/MuralWorks.json'
export default {
    name: 'MuralPage',
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