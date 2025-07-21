<script>
  import ArticleText from "../lib/ArticleText.svelte";
  import ObservedArticleText from "../lib/ObservedArticleText.svelte";

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


<div class="text-container">
  <div class="content">
    <ArticleText>
      Therefore, the mindset that a degree will grant wealth is misleading. 
      <br /><br />
      For minorities like Black and Hispanic students, higher education brings more risk, and earning enough to mitigate that risk will <i>still</i> be less than the earnings of their White counterparts or even those at a lower education level.
      
      <br /><br />
      The sooner we <i>acknowledge</i> this disparity, the sooner we can address the obstacles that <i>cause</i > it and support students disproportionately affected by the competitive job market today. 
    </ArticleText>

    <ObservedArticleText {callback} {options}>
      Sincerely, 
      <br /> A pensive undergraduate already stressing over job applications.
    </ObservedArticleText>
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
