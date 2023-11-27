<script>
export default {
    props: {
        character: Object,
    },
}

</script>

<template>
    <div class="card text-bg-warning">
        <img :src="character.card_images[0].image_url" alt="">
        <h3>{{ character.name }}</h3>
    </div>
    
</template>

<script>

</script>