<script lang="ts">
  import Greet from './lib/Greet.svelte'
  import OSinfo from './lib/OSinfo.svelte'
  import DiffuseursApi from './lib/diffuseursAPI.svelte';
</script>

<main class="container">

  <div class="row">
    <div class="col">
      <h1>Tauri, web Desktop app</h1>

      <p>un code (Rust/Javascript) = multi plateforme Windows/Linux/Mac (msi, exe, deb, dmg, ...)</p>
      <p>Il suffit de "commit" le code et la CI s'occupe de générer les binaires</p>

    </div>
  </div>
  <div class="row">
    <hr>
    <div class="col">
      <h4>Accès aux ressources du PC/mobile si besoin</h4>
      <p>fichiers, etc... Exemples :</p>
      <OSinfo/>
    </div>
    <div class="col">
      <h4>Afficher les données d'une API</h4>
      <DiffuseursApi/>
    </div>
  </div>


</main>

