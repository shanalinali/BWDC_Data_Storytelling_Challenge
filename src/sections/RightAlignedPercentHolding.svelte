<script>
  import "highcharts/modules/exporting";
  import Scroller from "../lib/Scroller.svelte";
  import ArticleText from "../lib/ArticleText.svelte";
  import PercentHoldingGraph from "../lib/PercentHoldingGraph.svelte";
</script>

<div>
  <Scroller layout="right">
    {#snippet sticky()}
      <!-- Visualization pulled from BWDC's Education data. -->
      <PercentHoldingGraph />

      <!-- make cute !!!! -->
      <div class="BWDC-graph-link">
        <a
          href="https://public.tableau.com/shared/8WFKXMT8Y?:display_count=n&:origin=viz_share_link&:embed=y"
        >
          <button>🔍 View this BWDC graph in another tab</button>
        </a>
      </div>
    {/snippet}

    {#snippet scrolly()}
      <ArticleText>
        gotta edit this :D
      </ArticleText>

      <ArticleText>
        hihi edit me!
      </ArticleText>
    {/snippet}
  </Scroller>
</div>

<style>
</style>
