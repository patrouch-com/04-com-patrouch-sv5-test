<script>
    /** @type {number} */
    let dice = $state(0);
    /** @type {Array.<number>} */
    let rolls = $state([]);

    function roll() {
        dice = Math.floor(Math.random() * Math.floor(12)) + 1;
        rolls[rolls.length] = dice;
    }
    function reset() {
        dice = 0;
        rolls = [];
    }
</script>

<section style="padding-top: 50px;">
        <button on:click={reset}> Let's restart </button>
        <button on:click={roll}> Let's roll </button>


    {#each rolls as t, index}
        <p style="text-align: center">
            Roll # {index + 1} =  {t}
        </p>
    {/each}
</section>
