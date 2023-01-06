<script>
  export let path;
  const jumpToDetailPage = (e) => {
    path = 'detail';
  };
  const jumpToMap = (e) => {
    path = 'map';
    setTimeout(() => {
      window.scrollTo(0, document.body.scrollHeight);
    }, 0);
  };
</script>

<div class="content">
  <div class="logo">
    <img src="./assets/logo.png" alt="logo"/>
  </div>
  <!-- svelte-ignore a11y-click-events-have-key-events -->
  <div class="btn" on:click|preventDefault={jumpToDetailPage}>
    <img src='./assets/button1.png' alt='button1'/>
  </div>
  <!-- svelte-ignore a11y-click-events-have-key-events -->
  <div class="btn" on:click|preventDefault={jumpToMap}>
    <img src='./assets/button2.png' alt='button1'/>
  </div>
</div>

<style>
  .content{
    position: absolute;
    z-index: 2; 
    flex-direction: column;
    display: flex;
    flex-wrap: nowrap;
    align-content: center;
    justify-content: center;
    align-items: center;
    width: 100%;
    height: 100%;
    /* gap: 5%; */
  }
  .logo{
    width: 60%;
    /* max-height: 300px; */
    margin: 0 auto;
    margin-bottom: 3rem;
  }
  .logo>img{
    width: 100%;
    height: 100%;
    object-fit: contain;
    filter: drop-shadow(0 0 1.2rem rgba(0, 0, 0, 0.5));
  }
  .btn{
    width: 40%;
    max-height: 300px;
    margin: 0 auto;
    margin-bottom: 1.5rem;
  }
  .btn>img{
    width: 100%;
    object-fit: contain;
    filter: drop-shadow(0 0 1.2rem rgba(0, 0, 0, 0.5));
  }
</style>