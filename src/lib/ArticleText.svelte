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
    padding: 20px;
    font-size: 1.2rem;
    color: #f6e8ea;
    text-shadow: 1px 1px 0 #60595c;
    margin-top: 1rem;
    /* Font inspired by this The Pudding website: https://pudding.cool/2025/04/music-dna/ */
    font-family: var(--font-body, serif);
    transition: transform 0.5s ease; 
  }

  .article-text:hover{
    transform: scale(1.07);
  }
</style>
