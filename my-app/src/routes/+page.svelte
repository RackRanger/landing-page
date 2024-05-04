<script>
  import {onDestroy, onMount} from 'svelte';
  import DataCollection from './GrafanaDashboard.svelte';
  import GrafanaDashboard from "./GrafanaDashboard.svelte";
  import Section from './Section.svelte';

  onMount(() => {
    const sections = document.querySelectorAll('section');

    sections.forEach(section => {
      section.addEventListener('click', () => {
        section.scrollIntoView({ behavior: 'smooth' });
      });
    });
  });


</script>


<main>
  <Section id="section1" title="The Problem">
     </Section>
  <Section id="section2" title="Our Dashboards">
    <GrafanaDashboard />
  </Section>
  <Section id="section3" title="architecture">
    <div class="first-page">
      <div class="firstline">
        <h1>Serfana</h1>

      </div>
      <div class="containerwhite">
        <div class="white-rounded-text-field">
          <h1 style="text-align: center;"> Team:</h1>
        </div>
        <div class="white-rounded-text-field">
          <h1 style="text-align: center;"> Our Mission:</h1>
        </div>
      </div>

    </div>
  </Section>

</main>





<style>
  :global(html),
  :global(body) {
    margin: 0;
    padding: 0;
    font-family: Arial, sans-serif;
    background: linear-gradient(to bottom right, #667eea, #764ba2); /* Gradient background */
    background-size: cover;
    background-attachment: fixed;
    color: white;
  }

  .containerwhite {
    display: flex;
    margin-bottom: 50px;
  }

  .firstline {
    display: flex;
    justify-content: center;
    align-items: center;

    padding: 10px;
    z-index: 1000;
    margin-bottom: 20px; /* Add margin to the bottom to create space */
    max-height: 100px; /* Set a maximum height for the .firstline element */
    overflow: hidden; /* Hide any content that exceeds the max-height */
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

  .first-page {
    height: 100vh; /* Set the height of the first page to viewport height */
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }
  main {
     overflow-y: auto;
     scroll-snap-type: y mandatory;
     height: 100vh;
   }




</style>
