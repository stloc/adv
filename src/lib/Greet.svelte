<script lang="ts">
  import { invoke } from "@tauri-apps/api/tauri";
  import { platform, version, type } from "@tauri-apps/api/os";

  let name = "";
  let greetMsg = "";

  async function greet() {
    // Learn more about Tauri commands at https://tauri.app/v1/guides/features/command
    greetMsg = await invoke("greet", { name });
  }

  async function osInfos() {
    const platformName = await platform();
    const osType = await type();
    console.log(platformName, osType);
  }

  osInfos();
</script>

<div>
  <form class="row" on:submit|preventDefault={greet}>
    <input id="greet-input" placeholder="Enter a name..." bind:value={name} />
    <button type="submit">Greet</button>
  </form>
  <p>{greetMsg}</p>
</div>
