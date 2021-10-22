<script>
    import {FeedBackStore} from '../stores'
    import {fade, scale } from 'svelte/transition'
    import FeedbackItem from "./FeedbackItem.svelte";
// import { onDestroy } from 'svelte';
//     let feedback = []

//     const unsubscribe = FeedbackStore.subscribe((data) => feedback = data)

//     onDestroy(() => {
//         unsubscribe()
//     })

</script>

{#each $FeedBackStore as fb (fb.id)}
<div in:scale out:fade>
    <FeedbackItem item={fb} />
</div>
{/each}