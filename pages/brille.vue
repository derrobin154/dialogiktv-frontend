<template>
    <b-container fluid class="bg-secondary text-light">
        <h1 class="display-1">Brillen <small>Kanalaktion</small></h1>

        <ul class="mb-0">
            <li v-for="(brille, index) in brillen" :key="brille" class="mb-4">
                <div align="center" class="embeddor">
                    <video autoplay loop class="embed-responsive-item">
                        <source :src="`/brillen/brille-${index+1}-${brille}.mp4`" type="video/mp4">
                    </video>

                    <div class="content text-left">
                        <h2>{{ brille }}</h2>
                        <p class="mb-0">Hier müsste jetzt Text kommen, damit das funktioniert.</p>
                    </div>
                </div>
            </li>
        </ul>
     </b-container>
</template>

<script>
export default {
    data() {
        return {
            brillen: [
                'arbeitgeber',
                'johnnydepp',
                'professor',
                'geierfogel',
                'gelblicht',
            ]
        };
    },
}
</script>

<style scoped>
ul, li {
    margin: 0;
    padding: 0;
}

li {
    list-style-type: none;
    min-height: 100vh;
}

li .embeddor {
    position: relative;
    overflow: hidden;
    background-color: black;
}

li .embeddor video {
    position: absolute;
    right: -30%;
    z-index: 1;
    top: 0;
    width: 100%;
    height: 100%;
    /*  object-fit is not supported on IE  */
    object-fit: cover;
    opacity: .05;
}

/* li .embeddor video::after {
    content: 'AAA';
    position: absolute;
    outline: 6px solid red;
    background: -moz-linear-gradient(left, rgba(0, 0, 0, 1), rgba(0, 0, 0, 1));
    background: -webkit-linear-gradient(left, rgba(0, 0, 0, 1), rgba(0, 0, 0, 1));
} */

li .embeddor .content {
    min-height: 100vh;
    display: grid;
    place-items: center;
}
</style>