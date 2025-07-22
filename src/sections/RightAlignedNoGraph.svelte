<script>
  import "highcharts/modules/exporting";
  import Scroller from "../lib/Scroller.svelte";
  import ArticleText from "../lib/ArticleText.svelte";
  import ObservedArticleText from "../lib/ObservedArticleText.svelte";

  const options = {
    threshold: [0.85, 0.95],
  };

  const callback = (entries, observer) => {
    entries.forEach((entry) => {
      const elem = entry.target;

      if (entry.intersectionRatio >= 0.90) {
        // "active" state
        elem.style.backgroundColor = "#9D6381";
      } else if (entry.intersectionRatio < 0.90) {
        // "inactive" state
        elem.style.backgroundColor = "#363636";
      }
    });
  };
</script>

<div>
  <Scroller layout="right">
    {#snippet sticky()}
      <img
        alt="Copyright-free gif of cartoon cars on a street from a bird's eye view."
        src="street_cars.gif"
      />
    {/snippet}

    {#snippet scrolly()}
      <ObservedArticleText {callback} {options}>
        <i
          >"You can't learn this now.
          <br /><br />
          If you do, you won't want to finish your studies—you'll be making enough
          money to forget about them."</i
        >
      </ObservedArticleText>

      <ArticleText>
        <strong>My father's words </strong>, spoken in Bangla, settle over me,
        and I laugh.
        <br /><br />
        Our 30-minute carpool drives to work almost always circle back to me 
        learning how to trade stocks, but "only after I graduate."
      </ArticleText>

      <ArticleText>
        <strong>I know the merit</strong> behind understanding today's market
        trends, of course.
        <br /><br />
        However, my Computer Science degree will hold value to me too,
        once I achieve it. My studies are time-consuming enough, stocks and trading aside.
        <br /><br />
        Why would the value of my education <i>diminish</i> in the context of wealth anyways?
      </ArticleText>

      <ArticleText>
        <strong>It's a common question</strong> for current college students,
        like myself.
        <br /><br />
        Truthfully, I find that the value of education today <u><i>is</i></u> getting murkier.
      </ArticleText>

      <ObservedArticleText {callback} {options}>
        <strong
          >2025 reveals a <a
            href="https://www.cnbc.com/2025/05/16/how-college-grads-can-find-a-job-in-a-tough-market.html"
            >5.8% unemployment rate</a
          ></strong
        >
        among recent college graduates. 
        <br /><br />
        Even with a degree, educated workers are
        struggling to find jobs.
        <br /><br />
      </ObservedArticleText>
    {/snippet}
  </Scroller>
</div>

<style>
</style>
