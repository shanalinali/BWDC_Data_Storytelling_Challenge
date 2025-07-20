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
      To better understand the relationship between education and wealth, I've summarized a few shocking insights from this BWDC graph.
    </ArticleText>

      <ArticleText>
        <strong>Change the dropdown below</strong> to learn something new.
        <br /><br />
        <!-- TODO: make comparison accurate + cute-->
        <HouseholdComparison />
      </ArticleText>

      <ArticleText>
       <ArticleText>
        <strong>Certain households</strong> grow wealthier than others despite having lower education status. 
       </ArticleText>
        <ArticleText>
          <strong>Contrary to the rhetoric from before</strong>, education <u>cannot</u> serve as a 1-way ticket to wealth.
        </ArticleText>
      </ArticleText>
    {/snippet}
  </Scroller>
</div>

<style>
</style>
