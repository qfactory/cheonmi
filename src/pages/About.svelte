
<script>
import { onMount } from "svelte";
import { fade } from 'svelte/transition';

export let path;
let scrollY = 0
const jumpToHome = (e) => {
  path = "home";
};

const openExternalLink = (e) => {
  window.open("http://kko.to/tvqHMwRa82", "_blank");
};

onMount(() => {
  if (path === 'map') {
    setTimeout(() => {
      console.log('scroll');
      window.scrollTo(0, document.body.scrollHeight);
    }, 50);
  }
});
</script>


<div class='content'>
  <img src='./assets/page1.png' alt='detail-1'/>
  <img src='./assets/page2.png' alt='detail-2'/>
  <img src='./assets/page3.png' alt='detail-3'/>
  <img src='./assets/page4.png' alt='detail-4'/>
  <img src='./assets/page5.png' alt='detail-5'/>
  <img src='./assets/page6.png' alt='detail-6'/>
  <img src='./assets/map.png' alt='map' class='map'/>
  <!-- svelte-ignore a11y-click-events-have-key-events -->
  <div class="ext_link" on:click|preventDefault={openExternalLink}>
    <img src='./assets/button4.png' alt='ext_link' class='ext-link'/>
  </div>
  {#if scrollY > 700}
  <!-- svelte-ignore a11y-click-events-have-key-events -->
  <div class="home_btn" on:click|preventDefault={jumpToHome} transition:fade>
    <img src='./assets/button3.png' alt='home_btn'/>
  </div>
  {/if}
</div>
<svelte:window bind:scrollY={scrollY} />

<style>
  .home_btn{
    position:fixed;
    bottom: 5%;
    width: 100%;
  }
  .home_btn>img{
    width: 15%;
    max-width: 80px;
    margin:0 auto;
    height: auto;
    object-fit: contain;
    filter: drop-shadow(0 0 0.5rem rgba(0, 0, 0, 0.3));
  }

  .ext_link{
    width: 100%;
    padding-bottom: 180px;
  }
  .ext_link>img{
    width: 50%;
    margin:0 auto;
    height: auto;
    object-fit: contain;
    filter: drop-shadow(0 0 0.5rem rgba(0, 0, 0, 0.3));
  }
  .map{
    width: 90% !important;
    margin: 0 auto;
    margin-bottom: 1rem;
  }

  .content{
    position: absolute;
    z-index: 2; 
    flex-direction: column;
    display: flex;
    flex-wrap: nowrap;
    align-content: center;
    justify-content: flex-start;
    align-items: center;
    width: 100%;
    height: 100%;
    gap: 5%;
  }
  .content>img{
    width: 100%;
    height: auto;
  }
</style>