<script>
  import {onDestroy, onMount} from 'svelte';
  import DataCollection from './GrafanaDashboard.svelte';
  import GrafanaDashboard from "./GrafanaDashboard.svelte";
  import Section from './Section.svelte';

  onMount(() => {
    const sections = document.querySelectorAll('section');

    /*sections.forEach(section => {
      section.addEventListener('click', () => {
        //section.scrollIntoView({ behavior: 'smooth' });
      });
    });*/
  });


</script>

<header class="global-header">
  <h1 style="margin-right: 5px;">Serfana</h1>
  <img class="img" src="namecheap.svg" alt="Description of the image">
  <a href="#section2" class="navbaritems">The Problem</a>
  <a href="#section3" class="navbaritems">Our Dashboards</a>
  <a href="#section4" class="navbaritems">The Architecture</a>
  <a href="#section5" class="navbaritems">Learning</a>

</header>

<main class ="mainbody">

  <Section id="section2" title="The Problem">

  </Section>
  <Section id="section3" title="Our Dashboards">
  </Section>
  <Section id="section4" title="The Architecture">

  </Section>
  <Section id="section5" title="Learning">

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

  .navbaritems {
    margin-right: 5px;
    text-decoration: none; /* Remove underline */
    color: black; /* Inherit color from parent */
  }
  .global-header {
    position: fixed;
    display: flex;
    height: 70px;
    align-items: center; /* Center vertically */
    margin-left: 30px;
  }

  .mainbody {
     margin-top: 100px;
     overflow-y: auto;
     scroll-snap-type: y mandatory;
     height: calc(100vh - 100px); /* Set height to fill the remaining viewport space after considering the fixed header */
  }

  .img {
    width: 60px;
    height: 60px;
    margin-right: 10px;
  }




</style>
