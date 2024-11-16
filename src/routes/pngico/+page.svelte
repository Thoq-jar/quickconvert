<div class="header-conversion-page native">
    <a href="/">Go Back</a>
</div>

<div class="wrapper native">
    <h1>PNG to ICO</h1>

    <div class="options">
        <input type="file"/>
    </div>

    <div class="options">
        <input id="width" type="number" placeholder="Width"/>
        <input id="height" type="number" placeholder="Height"/>
    </div>

    <button id="convert" on:click={handleConvert}>Convert</button>
</div>

<script lang="ts">import {onMount} from "svelte";

let widthInput: HTMLInputElement;
let heightInput: HTMLInputElement;

onMount(() => {
  widthInput = document.getElementById("width") as HTMLInputElement;
  heightInput = document.getElementById("height") as HTMLInputElement;

  widthInput.addEventListener('input', () => {
    if (Number(widthInput.value) > 1600) {
      widthInput.value = '1600';
    } else if (Number(widthInput.value) < 8) {
      widthInput.value = '8';
    }
  });

  heightInput.addEventListener('input', () => {
    if (Number(heightInput.value) > 1600) {
      heightInput.value = '1600';
    } else if (Number(heightInput.value) < 8) {
      heightInput.value = '8';
    }
  });
});

function handleConvert() {
  let width = widthInput ? parseInt(widthInput.value) : null;
  let height = heightInput ? parseInt(heightInput.value) : null;
}</script>