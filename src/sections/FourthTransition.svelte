<script>
  import ArticleText from "../lib/ArticleText.svelte";
</script>


<div class="text-container">
  <div class="content">
    <ArticleText>
      ...until you understand the trade-offs involved.
    </ArticleText>

    <ArticleText>
      Here's one last graph to put my sentiment into perspective.
    </ArticleText>
  </div>
</div>

<style>
  .text-container {
    background-color: #22181c;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding: 2rem;
    box-sizing: border-box;
  }
</style>
