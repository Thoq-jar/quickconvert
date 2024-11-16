<script lang="ts">
  import {page} from '$app/stores';
  import {get} from 'svelte/store';
  import type {Page} from '@sveltejs/kit';

  const code: number = (get(page) as Page).status;
  const catUrl: string = `https://http.cat/${code}`;
</script>

<div class="center native">
    <img src={catUrl} alt="Status code cat"/>
</div>

<style lang="css">
  .center {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
  }
</style>