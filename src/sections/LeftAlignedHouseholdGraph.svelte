<script>
  import Scroller from "../lib/Scroller.svelte";
  import ArticleText from "../lib/ArticleText.svelte";
  import HouseholdGraph from "../lib/HouseholdGraph.svelte";
  import HouseholdComparison from "../lib/HouseholdComparison.svelte";

  let showEmbed = false;
</script>

<div>
  <Scroller layout="left">
    {#snippet sticky()}
      <!-- Visualization pulled from BWDC's Education data. -->
      <!-- Conditonal to toggle between the static vs. interactive graph was debugged using ChatGPT -->
      {#if !showEmbed}
        <img
          alt="Line graph of Total Median Net Worth for Households, by Race/Ethnicity from the Black Wealth Data Center."
          src="Household_NetWorth.png"
        />

        <div class="BWDC-graph-link">
          <button on:click={() => (showEmbed = true)}>
            🔍 <u>Click to Interact with this BWDC graph</u>
          </button>
        </div>
      {:else}
        <HouseholdGraph />

        <div class="BWDC-graph-link">
          <button on:click={() => (showEmbed = false)}>
            🔍 <u>Click to Return to Image</u>
          </button>
        </div>
      {/if}
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
        <strong>Education alone</strong>
        <u>does not</u> serve as a 1-way ticket to wealth, especially for minorities.
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
