<script>
  import PollDetails from "./PollDetails.svelte";
  import PollStore from "../stores/PollStore";
  import { fade, slide, scale } from "svelte/transition";
  import { flip } from "svelte/animate";
  // import { onDestroy, onMount } from "svelte";
  // export let polls = [];

  // const unsub = PollStore.subscribe((data) => {
  //   polls = data;
  // });

  // // onMount(() => {});
  // onDestroy(() => {
  //   unsub();
  // });
</script>

<div class="poll-list">
  <!-- use$PollStore to automatically subscribe and unsubscribe on mount and destroy -->
  {#each $PollStore as poll (poll.id)}
    <div in:fade out:scale|local animate:flip={{ duration: 500 }}>
      <PollDetails {poll} />
    </div>
  {/each}
</div>

<style>
  .poll-list {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 20px;
  }
</style>
