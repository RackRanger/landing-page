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
  <Section id="section1" title="Serfana">

  </Section>
  <Section id="section2" title="The Problem">

  </Section>
  <Section id="section3" title="Our Dashboards">
  </Section>
  <Section id="section4" title="The Architecture">

  </Section>
  <Section id="section4" title="Learning">

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

  main {
     overflow-y: auto;
     scroll-snap-type: y mandatory;
     height: 100vh;
   }




</style>
