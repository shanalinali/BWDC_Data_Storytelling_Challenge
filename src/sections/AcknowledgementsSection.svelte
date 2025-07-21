<script>
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";
</script>

<div>
    <Scroller layout="left">
        {#snippet scrolly()}
        <ArticleText>
            Thank you for reading my first Scrollytelling narrative! 
        </ArticleText>

        <ArticleText>
            <strong> <i>
                This piece was created as a submission for the 2025 Kode With Klossy Data Storytelling Challenge. 
                <br /><br />
                Sources are credited in this piece's ReadMe file (linked <a href="https://github.com/shanalinali/BWDC_Data_Storytelling_Challenge">here</a>). 
                <br /><br />
                Please feel free to email me <a href="mailto:shanaliislamm@gmail.com">here</a> with any questions/feedback on this piece.
            </i></strong>
        </ArticleText>

        <ArticleText>
            <strong> <i>
                Sincere gratitude to the Black Wealth Data Center for providing a plethora of data visualizations, feedback, and many learning experiences through their mission. 
                <br /><br />
                Gratitude again for the Kode With Klossy team for providing this opportunity, endless support, and a project to remember.
            </i></strong>
        </ArticleText>
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
