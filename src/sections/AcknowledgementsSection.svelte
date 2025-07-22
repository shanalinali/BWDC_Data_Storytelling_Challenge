<script>
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";
</script>

<div>
    <Scroller layout="right">
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
                Please feel free to email me <a href="mailto:shanaliislamm@gmail.com">here</a> with any questions or feedback on this piece.
            </i></strong>
        </ArticleText>

        <ArticleText>
            <strong> <i>
                Sincere gratitude to the <a href="https://blackwealthdata.org/">Black Wealth Data Center</a> for providing a plethora of data visualizations, feedback, and many learning experiences through their mission. 
                <br /><br />
                Gratitude again for the <a href="https://www.kodewithklossy.com/">Kode With Klossy</a> team for providing this opportunity, endless support, and a project to remember.
            </i></strong>
        </ArticleText>
        {/snippet}

        {#snippet sticky()}
            <!-- svelte-ignore a11y_img_redundant_alt -->
            <img class="profile-photo" src="Profile_Photo_Acknowledgements.jpg" alt="Photo of Shanali modeling for ASU's Sun Devil Campus Bookstores!" />
        {/snippet}
    </Scroller>
</div>

<style>
    .profile-photo {
        width: 60%;
        margin: 0px auto;
    }
</style>
