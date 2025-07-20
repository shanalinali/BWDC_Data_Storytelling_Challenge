<script>
  import * as Highcharts from "highcharts";
  import "highcharts/modules/exporting";
  import { Chart } from "@highcharts/svelte";
  import Scroller from "../lib/Scroller.svelte";
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
        elem.style.backgroundColor = "#e3ff00";
      } else if (entry.intersectionRatio < 0.9) {
        // "inactive" state
        // to do BLUR !!!!!
        elem.style.backgroundColor = "#888888";
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
      <!-- using the Svelte JS typewriting transition here would be goated -->
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
        Our 30-minute carpool drive to work almost always circles back to the topic
        of me trading stocks soon.
      </ArticleText>

      <ArticleText>
        <strong>I know the merit</strong> behind understanding today's market
        trends, of course.
        <br /><br />
        However, my Computer Science undergraduate degree will hold value to me too,
        once I achieve it.
        <br /><br />
        Why would my education's value <i>diminish</i> in the context of wealth?
      </ArticleText>

      <ArticleText>
        <strong>It's a common question</strong> for current college students,
        like myself.
        <br /><br />
        Shockingly, the value of education today <i>is</i> getting murkier.
      </ArticleText>

      <ArticleText>
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
      </ArticleText>
    {/snippet}
  </Scroller>
</div>

<style>
  /* TODO: Delete this if unneeded! */
  /* p {
    font-size: 1rem;
    color: #f6e8ea;
    text-shadow: 1px 1px 0 #36242b;
    margin-top: 1rem;
    font-family: Georgia;
  } */
</style>
