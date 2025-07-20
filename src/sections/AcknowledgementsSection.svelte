<script>
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";
</script>

<div>
    <Scroller layout="left">
        {#snippet scrolly()}
            <ArticleText>
                <strong>
                    BWDC credit here lolz KWK Challenge credit here lolz
                </strong>
            </ArticleText>

            <ArticleText>Little self plug perchance?</ArticleText>
        {/snippet}

        {#snippet sticky()}
        <!-- TODO: add an image of myself lolol -->
            <img class="duck-img" src="duck.png" alt="KWK rubber duck!" />
        {/snippet}

        
    </Scroller>
</div>

<style>
    .duck-img {
        width: 25%;
        margin: 0px auto;
    }
</style>
