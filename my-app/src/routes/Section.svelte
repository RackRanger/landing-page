<!-- Section.svelte -->
<script>
    export let id;
    export let title;
</script>

<section id={id} class="section">
    <h2 >{title}</h2>
    <div>
        <!-- Content for each section -->
    </div>
</section>


<style>
    .section {
        scroll-snap-align: start;
        height: 100vh;
    }
</style>
