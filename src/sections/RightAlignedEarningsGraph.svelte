<script>
  import Scroller from "../lib/Scroller.svelte";
  import ArticleText from "../lib/ArticleText.svelte";
  import ObservedArticleText from "../lib/ObservedArticleText.svelte";
  import EarningsGraph from "../lib/EarningsGraph.svelte";
  import { fade } from "svelte/transition";

  // Boolean to determine if the BWDC graph has static vs. interactive dislay
  let showEmbed = false;

  // 0 will show earnings of those who completed high school
  // 1 will show earnings of those who completed a Bachelor's degree
  let showBachelors = 0;

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

  // Switch to image of earnings of those with a Bachelor's degree
  const showBachelorsCallback = (entries) => {
    entries.forEach((entry) => {
      if (entry.isIntersecting && entry.intersectionRatio >= 0.9) {
        showBachelors = 1; 
      }
    });
  };

  // Switch to image of earnings of those with High school completion
  const showHighSchoolCallback = (entries) => {
    entries.forEach((entry) => {
      if (entry.isIntersecting && entry.intersectionRatio >= 0.9) {
        showBachelors = 0; 
      }
    });
  };
</script>

<div>
  <Scroller layout="right">
    {#snippet sticky()}
      <!-- Visualization pulled from BWDC's Education data. -->
      <!-- Conditonal to toggle between the static vs. interactive graph data + Conditional to fade between different Education Level images were debugged using ChatGPT -->
      {#if !showEmbed}
      <!-- Show static image -->
        {#if showBachelors === 0}
        <!-- Show static image at High school completion level -->
          <img
            src="Earnings_HighSchoolCompletion.png"
            alt="Line graph of Median Annual Earnings for Full-Time Workers (25-34 Years Old) with High school completion from the Black Wealth Data Center."
            in:fade={{ duration: 500 }}
          />

          <div class="BWDC-graph-link">
            <button on:click={() => (showEmbed = true)}>
              🔍 <u>Click to Interact with this BWDC graph</u>
            </button>
          </div>
        {:else}
          <!-- Show static image at Bachelor's degree level -->
          <img
            src="Earnings_BachelorsDegree.png"
            alt="Line graph of Median Annual Earnings for Full-Time Workers (25-34 Years Old) with a Bachelor's degree from the Black Wealth Data Center."
            in:fade={{ duration: 500 }}
          />

          <div class="BWDC-graph-link">
            <button on:click={() => (showEmbed = true)}>
              🔍 <u>Click to Interact with this BWDC graph</u>
            </button>
          </div>
        {/if}
      {:else}
      <!-- Show embedded interactive graph -->
        <EarningsGraph />

        <div class="BWDC-graph-link">
          <button on:click={() => (showEmbed = false)}>
            🔍 <u>Click to Return to Image</u>
          </button>
        </div>
      {/if}
    {/snippet}

    {#snippet scrolly()}
      <ObservedArticleText callback={showHighSchoolCallback} {options}>
        <strong>Not much.</strong>
      </ObservedArticleText>

      <ArticleText>
        <strong>Despite obtaining the same educational level,</strong> workers differ
        greatly in their financial earnings by race.
      </ArticleText>

      <ArticleText>
        <strong
          ><a href="https://blackwealthdata.org/"
            >The Black Wealth Data Center (BWDC)</a
          ></strong
        >
        breaks it down clearly.
        <br /><br />
        Let's consider the median earnings for those who completed
        <u>high school</u>.
      </ArticleText>

      <ObservedArticleText {callback} {options}>
        <strong>Asian workers</strong> reported the most, followed by White
        workers.
        <br /><br />
        Both earnings fall within the <strong>$45K - $50K</strong> range.
      </ObservedArticleText>

      <ObservedArticleText {callback} {options}>
        <strong>Next</strong>, Hispanic workers earned around
        <strong>$41K</strong>, followed by Black workers at around
        <strong>$37K</strong>.</ObservedArticleText
      >

      <ArticleText
        ><strong>Even though</strong> both groups obtained a high school
        diploma, there is more than a <u>$13K difference</u> between Asian worker
        earnings (highest) and Black worker earnings (lowest).</ArticleText
      >

      <ObservedArticleText callback={showBachelorsCallback} {options}>
        <strong>This disparity</strong> continues if we consider those who
        obtained a <u>Bachelor's degree</u>.</ObservedArticleText
      >

      <ObservedArticleText {callback} {options}>
        <strong>Ranking the worker earnings </strong> from highest to lowest,
        <ol>
          <li>Asian (around $81K)</li>
          <li>White (around $70K)</li>
          <li>Hispanic (around $57K)</li>
          <li>Black (around $56K)</li>
        </ol>
        <br />
        This ranking is the same as that for workers who obtained a high school diploma.
      </ObservedArticleText>

      <ArticleText>
        Except now, there is more than a <u><strong>$25K</strong> difference</u>
        between earnings on the high end of the spectrum (Asian workers at $81K)
        and the low end of the spectrum (Black workers at $56K).
      </ArticleText>

      <ArticleText
        ><strong
          >Even when all groups received the same, higher level of education</strong
        >, Black workers still earned the least in the workforce.
      </ArticleText>

      <ObservedArticleText {callback} {options}>
        <strong>In fact,</strong> Black workers earn the least in
        <strong><u>half</u></strong>
        of the education levels included in this BWDC visualization—4 out of 8 levels.
        <br /><br />
        <strong>Hispanic workers</strong> earn the least in the other 4.
      </ObservedArticleText>
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
