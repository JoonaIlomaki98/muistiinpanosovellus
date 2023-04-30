<script>
  //Exportataan propseina.
  export let lisaa;
  let uusiNote = '';

  //Tekstikentän validointia. Jos käyttäjä yrittää lisätä uuden muistiinpanon kun ei ole syöttänyt mitään sisältöä niin annetaan virheilmoitus alert muodossa.
  function lahetaValid() {
    if (uusiNote.length < 1) {
      alert('Lisää nyt ihmeessä enemmän kuin tyhjyyden kuminaa!');
      return;
    }

    else {
  //Jos päästään validoinnista läpi niin lisätään onnistuneesti uusi käyttäjän syöttämä note. Samalla tyhjennetään kirjoitettu sisältö koska se on siirretty taulukkoon.
    lisaa(uusiNote);
    uusiNote = '';
  }
}
</script>
 <!-- Kun käyttäjä painaa lisää painiketta niin lahetaValid funktio lähtee päälle -->
<form on:submit|preventDefault={lahetaValid}>
  <label for="uusiNote">Lisää uusi muistiinpano:</label>
  <input type="text" id="uusiNote" bind:value={uusiNote}>
  <button type="submit">➕</button>
</form>