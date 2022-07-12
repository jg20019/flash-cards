<script>
import Card from './Card.svelte'

let cards = [
    { front: "+",  back:"Add",       showFront:true },
    { front: "-",  back:"Subtract",  showFront:true },
    { front: "*",  back:"Multiply",  showFront:true },
    { front: "/",  back:"Divide",    showFront:true },
    { front: "%",  back:"Modulus",   showFront:true },
    { front: "++", back:"Increment", showFront:true },
    { front: "--", back:"Decrement", showFront:true },
]

let index = 0

$: card = cards[index]
$: length = cards.length

function prevCard() {
    index = Math.max(0, (index - 1))
}

function flipCard() {
    console.log('flipping card')
    cards[index].showFront = !cards[index].showFront
}

function nextCard() {
    index = (index + 1) % length
}

</script>

<main> 
<Card 
    front="{card.front}"
    back="{card.back}" 
    showFront="{card.showFront}"
/>
<div class="controls">
    <button on:click={prevCard}> Prev </button>
    <button on:click={flipCard}> Flip </button>
    <button on:click={nextCard}> Next </button>
</div>
</main>


<style>
  :root {
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen,
      Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  }

  main {
    width: max-content;
    margin: 0 auto;
  }

  .controls {
    margin-top: 10px;
    display: flex;
    justify-content: space-between;
  }

  .controls button {
    padding: 5px 10px;
    font-family: monospace;
  }
</style>
