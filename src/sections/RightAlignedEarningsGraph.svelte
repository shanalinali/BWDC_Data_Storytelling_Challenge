<script>
  import "highcharts/modules/exporting";
  import Scroller from "../lib/Scroller.svelte";
  import ArticleText from "../lib/ArticleText.svelte";
  import EarningsGraph from "../lib/EarningsGraph.svelte";
</script>

<div>
  <Scroller layout="right">
    {#snippet sticky()}
      <!-- Visualization pulled from BWDC's Education data. -->
      <EarningsGraph />

      <!-- make cute !!!! -->
      <div class="BWDC-graph-link">
        <a
          href="https://public.tableau.com/views/BWDC-EducationEmployment-MedianAnnualEarnings/2MedianAnnualEarnings?:language=en-US&padding=0&:embed=y&:sid=&:redirect=auth&:origin=viz_share_link&:display_count=n&position=relative"
        >
          <button>🔍 Click to Interact with this BWDC graph/button>
        </a>
      </div>
    {/snippet}

    {#snippet scrolly()}
      <ArticleText>
        <strong>Not much.</strong>
      </ArticleText>

      <ArticleText>
        <strong>Despite obtaining the same educational level,</strong> races differ
        greatly in their financial earnings.
      </ArticleText>

      <ArticleText>
        <strong><a href="https://blackwealthdata.org/">The Black Wealth Data Center (BWDC)</a></strong> breaks it down clearly. 
        <br /><br />
        Let's consider the median
        earnings for those who completed <u>high school</u>.
      </ArticleText>

      <ArticleText>
        <strong>Asian workers</strong> reported the most, followed by White
        workers.
        <br /><br />
        Both earnings fall within the <strong>$45K - $50K</strong> range.</ArticleText
      >

      <ArticleText
        ><strong>Next</strong>, Hispanic workers earned around
        <strong>$41K</strong>, followed by Black workers at around
        <strong>$37K</strong>.</ArticleText
      >

      <ArticleText
        ><strong>Even though</strong> both groups obtained a high school
        diploma, there is more than a <u>$13K difference</u> between Asian worker earnings
        (highest) and Black worker earnings (lowest).</ArticleText
      >

      <ArticleText>
        <strong>This disparity</strong> continues if we consider those who
        obtained a <u>Bachelor's degree</u>.</ArticleText
      >

      <ArticleText
        ><strong>Ranking the worker earnings </strong> from highest to lowest,
        <ol>
          <li>Asian (around $81K)</li>
          <li>White (around $70K)</li>
          <li>Hispanic (around $57K)</li>
          <li>Black (around $56K)</li>
        </ol>
        <br />
        This ranking is the same as that for workers who obtained a high school diploma.
      </ArticleText>

      <ArticleText>
        Except now, there is more than a <u><strong>$25K</strong> difference</u>
        between Asian earnings and Black earnings.
      </ArticleText>

      <ArticleText
        ><strong>All races</strong> received a higher level of education, yet Black
        workers still earned the least in the workforce.
      </ArticleText>

      <ArticleText>
        <strong>In fact,</strong> Black workers earn the least in
        <strong><u>half</u></strong>
        of the education levels included in this BWDC visualization (4 out of 8
        education levels).
        <br /><br />
        <strong>Hispanic workers</strong> earn the least in the other 4.
      </ArticleText>
    {/snippet}
  </Scroller>
</div>

<style>
</style>
