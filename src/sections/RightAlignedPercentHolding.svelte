<script>
  import Scroller from "../lib/Scroller.svelte";
  import ArticleText from "../lib/ArticleText.svelte";
  import ObservedArticleText from "../lib/ObservedArticleText.svelte";
  import PercentHoldingsGraph from "../lib/PercentHoldingsGraph.svelte";
  import { fade } from "svelte/transition";

  // Boolean to determine if the BWDC graph has static vs. interactive display
  let showEmbed = false;

  // 0 will show the percent stock holdings and education loans for White households
  // 1 will show the percent stock holdings and education loans for Black households
  let showBlackHouseholds = 0;

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

  // Switch to image of percent stock holdings and education loans for Black households
  const showBlackHouseholdsCallback = (entries) => {
    entries.forEach((entry) => {
      if (entry.isIntersecting && entry.intersectionRatio >= 0.9) {
        showBlackHouseholds = 1;
      }
    });
  };

  // Switch to image of percent stock holdings and education loans for White households
  const showWhiteHouseholdsCallback = (entries) => {
    entries.forEach((entry) => {
      if (entry.isIntersecting && entry.intersectionRatio >= 0.9) {
        showBlackHouseholds = 0;
      }
    });
  };
</script>

<div>
  <Scroller layout="right">
    {#snippet sticky()}
      <!-- Visualization pulled from BWDC's Assests & Debts data. -->
      <!-- Conditonal to toggle between the static vs. interactive graph data + Conditional to fade between different Household images were debugged using ChatGPT -->
      {#if !showEmbed}
        <!-- Show static image -->
        {#if showBlackHouseholds === 0}
          <!-- Show static image of White Household percentages -->
          <img
            src="WhiteHouseholdHoldings.png"
            alt="Percentage of White households holding stock assets and education loans from 2007 - 2022 from the Black Wealth Data Center."
            in:fade={{ duration: 500 }}
          />

          <div class="BWDC-graph-link">
            <button on:click={() => (showEmbed = true)}>
              🔍 <u>Click to Interact with this BWDC graph</u>
            </button>
          </div>
        {:else}
          <!-- Show static image of Black Household percentages -->
          <img
            src="BlackHouseholdHoldings.png"
            alt="Percentage of Black households holding stock assets and education loans from 2007 - 2022 from the Black Wealth Data Center."
            in:fade={{ duration: 500 }}
          />

          <div class="BWDC-graph-link">
            <button on:click={() => (showEmbed = true)}>
              🔍 <u>Click to Interact with this BWDC graph</u>
            </button>
          </div>
        {/if}
      {:else}
        <!-- Show embedded, interactive graph -->
        <PercentHoldingsGraph />

        <div class="BWDC-graph-link">
          <button on:click={() => (showEmbed = false)}>
            🔍 <u>Click to Return to Image</u>
          </button>
        </div>
      {/if}
    {/snippet}

    {#snippet scrolly()}
      <ObservedArticleText callback={showWhiteHouseholdsCallback} {options}>
        <strong>Wealthier households</strong> have a stronger capability to take
        on financial risks.
      </ObservedArticleText>

      <ArticleText>
        <strong>From 2019 to 2022,</strong> the percent of White and Other race
        households with stock holdings <u>grew</u>.

        <br /><br /> At the same time, the percentage of these households with
        education loans <u>fell</u>. <br /><br />
        <ObservedArticleText {callback} {options}>
          <strong>Negative correlation</strong>—meaning that stock assets
          increased while education debts decreased for these households.
        </ObservedArticleText>

        <h5>
          <i
            >NOTE: Only White households are pictured because both filters
            cannot be displayed at once. Click the interactive button underneath
            the graph to observe this trend for Other race households as well!</i
          >
        </h5>
        <br /><br />
      </ArticleText>

      <ObservedArticleText callback={showBlackHouseholdsCallback} {options}>
        <strong>Again, this trend is different</strong> for Black and Hispanic households.
      </ObservedArticleText>

      <ArticleText>
        <strong>From 2019 to 2022,</strong> the percentage of Black and Hispanic
        households with stock holdings increased, but
        <u>so did the percentage of these households with education loans</u>.

        <ObservedArticleText {callback} {options}>
          <strong>Positive correlation</strong>—stock assests and education
          debts both increased.
        </ObservedArticleText>

        <br /><br />
        <h5>
          <i
            >NOTE: Only Black households are pictured because both filters
            cannot be displayed at once. Click the interactive button underneath
            the graph to observe this trend for Hispanic households as well!</i
          >
        </h5>
      </ArticleText>

      <ArticleText>
        Education loans are typically fixed and accrue interest—a consistent
        detractor of wealth—while stocks are an unpredictable source of wealth.
        <br /><br />Black and Hispanic households are then at a
        <u>higher financial risk</u>
        when they decide to pursue higher education.
        <br /><br />They do not have the generational wealth or median net
        worth, as established by previous visualizations, to easily make that
        decision.
      </ArticleText>

      <ArticleText>
        <strong>So many factors</strong> play into whether students, workers, or
        households are likely to take out loans to further their education.
        <br /><br />And when the job market does not readily guarentee a job
        after graduation, the risk in taking on debt for education increases.
        <br /><br />Instead of improving one's chances at wealth, education
        could hurt it.
      </ArticleText>
    {/snippet}
  </Scroller>
</div>

<style>
  /* Styling the different states of the button */
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
    padding: 10px;
  }
</style>
