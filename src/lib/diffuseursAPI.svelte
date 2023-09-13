<script lang="ts">
  import { onMount } from "svelte";

  let cities: never[];
  onMount(async () => {
    const response = await fetch(
      "https://geo.api.gouv.fr/departements/29/communes?limit=10"
    );
    cities = await response.json();
  });

  //osInfos();
</script>

<div>
  API Geo gouv
  <ul>
    {#if cities}
      {#each cities as city}
        <li>{city.nom}</li>
      {/each}
    {:else}
      <li>Loading...</li>
    {/if}
  </ul>
</div>
