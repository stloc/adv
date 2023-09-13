<script lang="ts">
  import { invoke } from "@tauri-apps/api/tauri";
  import { platform, version, type, tempdir } from "@tauri-apps/api/os";

  let name = "";
  let greetMsg = "";

  async function greet() {
    // Learn more about Tauri commands at https://tauri.app/v1/guides/features/command
    greetMsg = await invoke("greet", { name });
  }

  async function osInfos() {
    const platformName = await platform();
    const osType = await type();
    const tempdirPath = await tempdir();
    console.log(platformName, osType);
    return { platformName: platformName, osType: osType, tempdirPath: tempdirPath };
  }

  //osInfos();
</script>

<div>
  informations systeme {#await osInfos() then osInfos}
    <strong>{osInfos.platformName}, {osInfos.osType}, {osInfos.tempdirPath}</strong>
  {/await}
</div>
