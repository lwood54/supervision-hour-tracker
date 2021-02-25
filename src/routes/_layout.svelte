<script lang="ts">
  import Nav from '../components/Nav.svelte';
  import { MaterialApp } from 'svelte-materialify';
  import { Button } from 'svelte-materialify';

  let theme: 'light' | 'dark' = 'light';
  let isClicked = false;

  export let segment: string;
  const handleClick = () => {
    isClicked = !isClicked;
  };
</script>

<MaterialApp {theme}>
  <Nav {segment} />
  <slot />
  <Button on:click={handleClick}>Click Me</Button>
  {#if isClicked}
    <h1>First Click</h1>
  {/if}
</MaterialApp>

<style>
</style>
