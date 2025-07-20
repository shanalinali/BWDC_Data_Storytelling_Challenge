<script>
  let { title, subtitle, author } = $props();
  // import { fade } from 'svelte/transition'; get help in office hours with this transition!!
  //  or using the Svelte JS typewriting transition here would be goated
</script>

<div class="title-card">
  <div class="content">
    <h1>{title}</h1>
    <p>{subtitle}</p>
    <h3>{@html author}</h3>
  </div>
</div>

<style>
  .title-card {
    background-color: #22181c;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding: 2rem;
    box-sizing: border-box;
  }

  .content {
    max-width: 700px;
    background-color: #ad6a6c;
    padding: 2rem;
    border: 6px solid #5a0001;
    border-radius: 2rem;
    box-shadow: 16px 16px #8c1d1f;
  }

  h1 {
    font-size: 3rem;
    margin: 0;
    color: #5a0001;
    text-shadow: 1px 1px 0 #22181c;
    font-family: Times, "Times New Roman", serif;
  }

  h3 {
    margin: 0;
    color: #f6e8ea;
    text-shadow: 1px 1px 0 #36242b;
    font-family: Times, "Times New Roman", serif;
  }

  p {
    font-size: 1.3rem;
    color: #f6e8ea;
    text-shadow: 1px 1px 0 #36242b;
    margin-top: 1rem;
    font-family: monospace;
  }

  @media (max-width: 600px) {
    h1 {
      font-size: 2.2rem;
    }

    p {
      font-size: 1.1rem;
    }
  }
</style>
