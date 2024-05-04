<!-- Section.svelte -->
<script>
    import GrafanaDashboard from "./GrafanaDashboard.svelte";

    export let id;
    export let title;
    function isIntropage() {
        return id === "section1" ;

    }
    function isProblemPage() {
        return id === "section2" ;
    }
    function isDashboard() {
        return id === "section3";
    }
    function isArchitecturePage() {
        return id === "section4" ;
    }
</script>

<section id={id} class="section">
    {#if isDashboard()}
        <h2 class="header">{title}</h2>
        <GrafanaDashboard />
    {:else if isProblemPage()}
        <h2 class="header">{title}</h2>
        <div class="problemStatement">
            Server observability is missing a key component like in we need

        </div>
    {:else if isArchitecturePage()}
        <div >
            <h2 class="header">{title}</h2>

            <div class="containerwhite">
                <div class="white-rounded-text-field">
                    <h1 style="text-align: center;"> The Team</h1>
                </div>
                <div class="white-rounded-text-field">
                    <h1 style="text-align: center;"> Our Infrastructure</h1>
                </div>
            </div>

        </div>
    {:else if isIntropage()}
        <div class="first-page">
            <h1 style="margin: 0px; ">{title}</h1>

            <div class="images">
                <img class="img" src="grafana.svg" alt="Description of the image">
                <img class="x-image" src="x-letter.svg" alt="Description of the image">
                <img class="img" src="namecheap.svg" alt="Description of the image">
            </div>

        </div>

    {/if}

</section>


<style>
    .x-image {
        width: 40px;
        height: 40px;
        margin-right: 10px;
    }
    .img {
        width: 60px;
        height: 60px;
        margin-right: 10px;
    }
    .images {
        display: flex;
        justify-content: center; /* Center horizontally */
        align-items: center; /* Center vertically */
    }
    .first-page {
        text-align: center; /* Center the text horizontally */
        font-size: 70px; /* Set the font size to 36 pixels or adjust as needed */
        justify-content: center; /* Center horizontally */
        height: 100vh; /* Set height to 100% of viewport height */
        align-items: center;
        display: grid;


    }
    .header {
        padding: 30px;
        font-size: 50px;
        margin:0px;
    }
    .section {
        scroll-snap-align: start;
        height: 100vh;
    }
    .white-rounded-text-field {
        width: 45%; /* Adjust width as needed */
        max-width: 45%; /* Set a maximum width if necessary */
        padding: 20px;
        background-color: #f5f5f5; /* Light gray color */
        border-radius: 10px;
        margin-right: 20px; /* Add spacing between the boxes */
        color: black;
    }

    .white-rounded-text-field:last-child {
        margin-right: 0; /* Remove right margin from the last box to prevent extra spacing */
    }
    .containerwhite {
        display: flex;
        justify-content: center;
    }
    .problemStatement {
        color: black;

    }



</style>
