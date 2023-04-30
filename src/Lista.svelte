<script>
  //Exportataan propseina.
  export let sisalto;
  export let poistaNote;
</script>
<main>
<h3>Muistiinpanot:</h3>
 <!-- Näytetään each metodin avulla kaikki sisältö taulukosta. -->
  {#each sisalto as sisaltoo, i}
      {sisaltoo}
  <!-- Painike, joka suorittaa poistaNote funktion, eli poistaa halutun muistiinpanon. Ilmenee jokaisen muistiinpanon vieressä koska tämä lohko sijaitsee each sisällä -->
      <button on:click={() => poistaNote(i)}>➖</button>
      <br>
  {/each}
</main>
