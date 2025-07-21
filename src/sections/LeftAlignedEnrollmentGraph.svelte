<script>
  import "highcharts/modules/exporting";
  import Scroller from "../lib/Scroller.svelte";
  import ArticleText from "../lib/ArticleText.svelte";
  import EnrollmentGraph from "../lib/EnrollmentGraph.svelte";
</script>

<div>
  <Scroller layout="left">
    {#snippet sticky()}
      <!-- Visualization pulled from BWDC's Education data. -->
      <EnrollmentGraph />

      <div class="BWDC-graph-link">
        <a
          href="https://public.tableau.com/views/BWDC-EducationEmployment-Grade12andUndergradEnrollmentRates/EDU07?:language=en-US&padding=0&:embed=y&:sid=&:redirect=auth&:origin=viz_share_link&:display_count=n&position=relative"
        >
        <button>🔍 Click to Interact with this BWDC graph</button>
        </a>
      </div>
    {/snippet}

    {#snippet scrolly()}
      <ArticleText>
        <strong>In fact,</strong> undergraduate enrollment rates have <u>decreased</u>
        across all races, according to the <a href="https://blackwealthdata.org/">Black Wealth Data Center (BWDC)</a>.
      </ArticleText>

      <ArticleText>
        <strong>Scroll down</strong> to view the percent decrease for each race, ordered
        from greatest to least.
      </ArticleText>

 <!-- TODO: create a new type of ArticleText? that's styled differently? -->
      <ArticleText>
        Black: ⬇️ 1.6%
      </ArticleText>

      <ArticleText>
        Asian: ⬇️ 1.5%
      </ArticleText>

      <ArticleText>
        White: ⬇️ 0.9%
      </ArticleText>

      <ArticleText>
        Hispanic: ⬇️ 0.6%
      </ArticleText>

      <ArticleText>
        Evidently, less students are pursuing higher education. 
      </ArticleText>
    {/snippet}
  </Scroller>
</div>

<style>
</style>
