<script setup>
    import { ToRefs } from 'vue';
    import { RouterLink } from 'vue-router';

    const props = defineProps({
        imgae: String,
        title: String,
        subTitle: String
    })

    const { image, title , subTitle} = toRefs(props)
</script>

<template>
    <div>
        <RouterLink to="library">
            
        </RouterLink>
    </div>
</template>



