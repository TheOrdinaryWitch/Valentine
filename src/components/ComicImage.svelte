<script>
    export let src;
    export let onClick;
</script>

<img src={src} alt="Comic" on:click={onClick}/>

<style>
    img{
        max-width: 100%;
        max-height: 100vh;
        display: block;
        margin: auto;
    }
</style>