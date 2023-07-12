<script lang="ts">
  import { invoke } from "@tauri-apps/api/tauri"

  let name = "";
  let greetMsg = ""

  async function generateValues(){
    // Learn more about Tauri commands at https://tauri.app/v1/guides/features/command
    greetMsg = await invoke("greet", { name })
  }
</script>

<div style="margin-top: 10px;">
  <div class="row">
    <form class="row" on:submit|preventDefault={generateValues}>
      <button type="submit">Generate values</button>
    </form>
    <form style="margin-left: 10px;">
      <button>Execute K-Means</button>
    </form>
  </div>
</div>