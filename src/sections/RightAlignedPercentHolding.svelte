<script>
  import "highcharts/modules/exporting";
  import Scroller from "../lib/Scroller.svelte";
  import ArticleText from "../lib/ArticleText.svelte";
  import WhitePercentHoldingGraph from "../lib/WhitePercentHoldingGraph.svelte";
</script>

<div>
  <Scroller layout="right">
    {#snippet sticky()}
      <!-- Visualization pulled from BWDC's Education data. -->
      <WhitePercentHoldingGraph />

      <!-- make cute !!!! -->
      <div class="BWDC-graph-link">
        <a
          href="https://public.tableau.com/shared/FYYG5K5ZH?:display_count=n&:origin=viz_share_link"
        >
          <button>🔍 Click to Interact with this BWDC graph</button>
        </a>
      </div>
    {/snippet}

    {#snippet scrolly()}
      <ArticleText>
        <strong>Wealthier households</strong> have a stronger capability to take on financial risks.
      </ArticleText>

      <ArticleText>
        <strong>From 2019 to 2022,</strong> the percent of White and Other race households with stock holdings <u>grew</u>.
        <br /><br /> At the same time, the percentage of these households with education loans <u>fell</u>. 
      </ArticleText>

      <ArticleText>
        <strong>Negative correlation</strong>—meaning that stock assets increased while education debts decreased for these households.
      </ArticleText>

      <ArticleText>
        <strong>Again, this trend is different</strong> for Black and Hispanic households.
      </ArticleText>

      <ArticleText>
       <strong>From 2019 to 2022,</strong> the percentage of Black and Hispanic households with stock holdings increased, but <u>so did the percentage of these households with education loans</u>.
       <br /><br /><strong>Positive correlation</strong>—stock assests and education debts both increased. 
      </ArticleText>

      <ArticleText>
        Education loans are typically fixed and accrue interest—a consistent detractor of wealth—while stocks are an unpredictable source of wealth.
        <br /><br />Black and Hispanic households are then at a <u>higher financial risk</u> when they decide to pursue higher education.
        <br /><br />They do not have the generational wealth or median net worth, as established by previous visualizations, to easily make that decision.
      </ArticleText>

      <ArticleText>
        <strong>So many factors</strong> play into whether students, workers, or households are likely to take out loans to further their education. 
        <br /><br />And when the job market does not readily guarentee a job after graduation, the risk in taking on debt for education increases. 
        <br /><br />Instead of improving one's chances at wealth, education could hurt it. 
      </ArticleText>
    {/snippet}
  </Scroller>
</div>

<style>
</style>
