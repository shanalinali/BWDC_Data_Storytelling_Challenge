<script>
  import "highcharts/modules/exporting";
  import Scroller from "../lib/Scroller.svelte";
  import ArticleText from "../lib/ArticleText.svelte";
  import ObservedArticleText from "../lib/ObservedArticleText.svelte";
  import EnrollmentGraph from "../lib/EnrollmentGraph.svelte";

  const options = {
    threshold: [0.85, 0.95],
  };

  const callback = (entries, observer) => {
    entries.forEach((entry) => {
      const elem = entry.target;

      if (entry.intersectionRatio >= 0.9) {
        // "active" state
        elem.style.backgroundColor = "#9D6381";
      } else if (entry.intersectionRatio < 0.9) {
        // "inactive" state
        elem.style.backgroundColor = "#888888";
      }
    });
  };
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
        <button>🔍 <u>Click to Interact with this BWDC graph</u></button>
        </a>
      </div>
    {/snippet}

    {#snippet scrolly()}
      <ArticleText>
        <strong>In fact,</strong> undergraduate enrollment rates have decreased
        across <u>all</u> races, according to the <a href="https://blackwealthdata.org/">Black Wealth Data Center (BWDC)</a>.
      </ArticleText>

      <ArticleText>
        <strong>Scroll down</strong> to view the percent decrease for each race, ordered
        from greatest to least.
      </ArticleText>

      <ObservedArticleText {callback} {options}>
        Black: ⬇️ 1.6%
      </ObservedArticleText>

      <ObservedArticleText {callback} {options}>
        Asian: ⬇️ 1.5%
      </ObservedArticleText>

      <ObservedArticleText {callback} {options}>
        White: ⬇️ 0.9%
      </ObservedArticleText>

      <ObservedArticleText {callback} {options}>
        Hispanic: ⬇️ 0.6%
      </ObservedArticleText>

      <ArticleText>
        Evidently, fewer students are pursuing higher education. 
      </ArticleText>
    {/snippet}
  </Scroller>
</div>

<style>
  button {
    font-family: Verdana;
    color:#22181C;
    background-color: #8BBEB2;
    border-radius: 20px;
    padding: 10px;
  }

  button:hover{
    color: #8BBEB2;
    background-color: #513942;
  }
</style>
