<script>
  //Tuodaan Lista ja LisaaUusi komponentit pääkomponenttiin.
  import Lista from './Lista.svelte';
  import LisaaUusi from './lisaaUusi.svelte';


  
  //Taulukko muistiinpanoille. Lisäsin myös muutaman esimerkin sisällöksi.
  let sisalto = ['Hae kaupasta maitoa', 'Käytä koiraa ulkona', 'Sovi tapaaminen ystävän kanssa klo 17', 'Toivo että Jake ei anna hylsyä'];

  //
  function lisaa(uusiNote) {
    sisalto = [...sisalto, uusiNote];
  }
  
  // Funktio poistaa muistiinpanon.
  function poistaNote(index) {
    sisalto.splice(index, 1);
    sisalto = [...sisalto];
  }
</script>
 <!-- Päänähtävyys. Löytyy otsikko, ohjeita sekä erityishuomioita. -->
<main>
<h1>Muistiinpanosovellus</h1>
<p>Ohjeet: Syötä haluamasi sisältö 'Lisää uusi muistiinpano' tekstin alapuolella olevalle kentälle ja paina plus nappia, joka lisää sisältösi kokoelmaan. Plussa tarkoittaa lisäämistä, miinus muistiinpanon vieressä tarkoittaa poistamista.</p>
<br>
<h3>HUOM! Syöttämäsi sisällön pitää sisältää vähintään yksi kirjain/merkki.</h3>
<hr>
 <!-- Lisätään Lista ja LisaaUusi komponentit tähän kohtaan. -->
<Lista sisalto={sisalto} poistaNote={poistaNote} />
<LisaaUusi lisaa={lisaa} />
</main>

 <!-- Tyylitellään tiettyjä sovelluksen elementtejä mm. otsikot, perusteksti sekä main osio. -->
<style>

  main {
    text-align: center;
    font-family: Helvetica;
  } 

  h1 { 
    text-align: center;
    color: #00276e; 
    text-transform: uppercase; 
    font-size: 3em; 
    font-weight: 100;
    font-family: Helvetica; 
  } 

  h3 {
    color: rgb(199, 0, 0);
    font-family: Helvetica;
  }
</style>