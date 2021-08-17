<script>
  import PollDetails from "./PollDetails.svelte";
  import PollStore from "../stores/PollStore";
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
    <div>
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
