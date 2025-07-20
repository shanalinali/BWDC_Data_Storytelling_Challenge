<script>
  let { children } = $props();
</script>

<div class="article-text">
  <p>
    {@render children()}
  </p>
</div>

<style>
  .article-text {
    margin: 50vh auto;
    width: 50%;
    background-color: #ad6a6c;
    border: solid #5a0001 3px;
    padding: 18px;
    font-size: 1.2rem;
    color: #f6e8ea;
    text-shadow: 1px 1px 0 #60595c;
    margin-top: 1rem;
    font-family: Georgia;
  }
</style>
