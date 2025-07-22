<script>
  import "highcharts/modules/exporting";
  import Scroller from "../lib/Scroller.svelte";
  import ArticleText from "../lib/ArticleText.svelte";
  import ObservedArticleText from "../lib/ObservedArticleText.svelte";
  import EnrollmentGraph from "../lib/EnrollmentGraph.svelte";

  let showEmbed = false;

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
        elem.style.backgroundColor = "#363636";
      }
    });
  };
</script>

<div>
  <Scroller layout="left">
    {#snippet sticky()}
    <!-- Visualization pulled from BWDC's Education data. -->
    <!-- Conditonal to toggle between the static vs. interactive graph was debugged using ChatGPT -->
      {#if !showEmbed}
        <img
          alt="Bar graph of Grade 12 and Undergrad Enrollment Rates from the Black Wealth Data Center."
          src="Enrollment_Chart.png"
        />

        <div class="BWDC-graph-link">
          <button on:click={() => (showEmbed = true)}>
            🔍 <u>Click to Interact with this BWDC graph</u>
          </button>
        </div>
      {:else}
        <EnrollmentGraph />

        <div class="BWDC-graph-link">
          <button on:click={() => (showEmbed = false)}>
            🔍 <u>Click to Return to Image</u>
          </button>
        </div>
      {/if}
    {/snippet}

    {#snippet scrolly()}
      <ArticleText>
        <strong>In fact,</strong> undergraduate enrollment rates have fallen
        across <u>all</u> races, according to the
        <a href="https://blackwealthdata.org/"
          >Black Wealth Data Center (BWDC)</a
        >.
      </ArticleText>

      <ArticleText>
        <strong>Scroll down</strong> to view the percent decrease in enrollment rates
        for each, ordered from greatest to least.
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
    color: #22181c;
    background-color: #8bbeb2;
    border-radius: 20px;
    padding: 10px;
  }

  button:hover {
    color: #8bbeb2;
    background-color: #513942;
  }

  img {
    width: 900px;
    height: 660px;
    padding: 18px;
  }
</style>
