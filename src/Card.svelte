<script>
    export let front
    export let back

    export let showFront = true

    $: cardText = showFront ? front : back

</script>

<div class="card">
    <span> { cardText } </span>
</div>

<style>
    .card {
        display: flex;
        max-width: 480px;
        min-width: 320px;
        height: 240px;
        display: flex;
        font-size: 48px;
        border: 2px solid black;
        justify-content: center;
        align-items: center;
        background-color: white;
    }
</style>
