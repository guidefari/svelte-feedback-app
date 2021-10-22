<script>
import FeedbackForm from './components/FeedbackForm.svelte';

	import FeedbackList from './components/FeedbackList.svelte'
import FeedbackStats from './components/FeedbackStats.svelte';
	
  let feedback = [
	  {
		  id: 1,
		  rating: 9,
		  text: 'girl end spring excitement aware wonderful atmosphere language caught oil book goes donkey nature already dinner maybe shop tool spider which such sign strength',
	  },
	  {
		  id: 3,
		  rating: 1,
		  text: 'character left apple ball thus anywhere massage would hang location put toy torn bridge excited second diagram skill numeral operation without silence freedom sharp',
	  },
	  {
		  id: 2,
		  rating: 4,
		  text: 'student total let laugh tongue story pet led column imagine society temperature friendly teacher bright hardly north beat figure last mouse interest congress slept',
	  },
  ]

  $: count = feedback.length
  $: average = feedback.reduce((a, {rating}) => a + rating, 0) / feedback.length

  const deleteFeedback = e => {
	  const itemId = e.detail;
	  feedback = feedback.filter(item => item.id != itemId)
  }
</script>

<main class="container">
	<FeedbackForm />
	<FeedbackStats {count} {average}/>
	<FeedbackList {feedback} on:delete-feedback={deleteFeedback}/>
</main>

<style>

</style>