<script>
    import Card from './Card.svelte';
    import Profile from './Profile.svelte';
    export let posts = [];
    console.log("hola")

</script>

<style>
    .TimeLine {
      padding: 4em 0 0 0;
    }
  </style>

<div class = "TimeLine">
    <div class = "TimeLine-container">
        {#each posts as post}
         <Card {...post} />
        {:else}
         <p>Loading...</p>
       {/each}
    </div>
    <Profile />
</div>