<script>
  import "highcharts/modules/exporting";
  import Scroller from "../lib/Scroller.svelte";
  import ArticleText from "../lib/ArticleText.svelte";
  import HouseholdGraph from "../lib/HouseholdGraph.svelte";
  import HouseholdComparison from "../lib/HouseholdComparison.svelte";
</script>

<div>
  <Scroller layout="left">
    {#snippet sticky()}
      <!-- Visualization pulled from BWDC's Assets & Debts data. -->
      <HouseholdGraph />

      <div class="BWDC-graph-link">
        <a
          href="https://public.tableau.com/views/BWDC-AssetsDebt-SCFTimeSeries/SCFTimeSeries?:language=en-US&padding=0&:embed=y&:sid=&:redirect=auth&:origin=viz_share_link&:display_count=n&position=relative"
        >
          <button>🔍 View this BWDC graph in another tab</button>
        </a>
      </div>
    {/snippet}

    {#snippet scrolly()}
      <ArticleText>
        <strong>Below</strong>, I've summarized a few shocking insights from
        this BWDC graph, based on those with the highest median net worth—White
        households.
      </ArticleText>

      <ArticleText>
        <strong>Change the dropdown to learn something new</strong>.
        <br /><br />
        <HouseholdComparison />
      </ArticleText>

      <ArticleText>
        <strong>White households</strong> with lower levels of education reflect
        more wealth than other households with higher education status.
      </ArticleText>

      <ArticleText>
        <strong>Therefore</strong>, education alone
        <u>cannot</u> serve as a 1-way ticket to wealth.
      </ArticleText>
    {/snippet}
  </Scroller>
</div>

<style>
</style>
