<template>
    <div>
        <PageComponent title="Commission" :json="json" imageFolder="Commission"/>
    </div>
</template>
<script>
import PageComponent from '@/components/PageComponent.vue'
import json from '@/assets/CommissionWorks.json'
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