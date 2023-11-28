<script>
export default {
    props: {
        character: Object,
    },
}

</script>

<template>
    <div class="card text-bg-warning h-100">
        <img :src="character.card_images[0].image_url_small" alt="">
        <h3>{{ character.name }}</h3>
        <p>{{character.archetype}}</p>
    </div>
    
</template>

<script>

</script>