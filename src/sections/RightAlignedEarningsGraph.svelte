<script>
  // @ts-nocheck

  import * as Highcharts from "highcharts";
  import "highcharts/modules/exporting";
  import { Chart } from "@highcharts/svelte";
  import Scroller from "../lib/Scroller.svelte";
  import ArticleText from "../lib/ArticleText.svelte";
</script>

<div>
  <Scroller layout="right">
    {#snippet sticky()}
      <!-- Visualization pulled from BWDC's Education data. -->
      <div class="tableau-container">
        <div
          class="tableauPlaceholder"
          id="viz1752834030612"
          style="position: relative"
        >
          <noscript>
            <a href="#">
              <img
                alt="[2] Median Annual Earnings "
                src="https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;BW&#47;BWDC-EducationEmployment-MedianAnnualEarnings&#47;2MedianAnnualEarnings&#47;1_rss.png"
                style="border: none"
              />
            </a>
          </noscript>
          <!-- svelte-ignore a11y_missing_attribute -->
          <object class="tableauViz" style="display:none;">
            <param
              name="host_url"
              value="https%3A%2F%2Fpublic.tableau.com%2F"
            />
            <param name="embed_code_version" value="3" />
            <param name="site_root" value="" />
            <param
              name="name"
              value="BWDC-EducationEmployment-MedianAnnualEarnings&#47;2MedianAnnualEarnings"
            />
            <param name="tabs" value="no" />
            <param name="toolbar" value="yes" />
            <param
              name="static_image"
              value="https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;BW&#47;BWDC-EducationEmployment-MedianAnnualEarnings&#47;2MedianAnnualEarnings&#47;1.png"
            />
            <param name="animate_transition" value="yes" />
            <param name="display_static_image" value="yes" />
            <param name="display_spinner" value="yes" />
            <param name="display_overlay" value="yes" />
            <param name="display_count" value="yes" />
            <param name="language" value="en-US" />
          </object>
        </div>
      </div>

      <script type="text/javascript">
        var divElement = document.getElementById("viz1752834030612");
        var vizElement = divElement.getElementsByTagName("object")[0];
        vizElement.style.width = "800px";
        vizElement.style.height = "550px";
        var scriptElement = document.createElement("script");
        scriptElement.src =
          "https://public.tableau.com/javascripts/api/viz_v1.js";
        vizElement.parentNode.insertBefore(scriptElement, vizElement);
      </script>

<!-- make cute !!!! -->
      <div class="BWDC-graph-link">
        <a
          href="https://public.tableau.com/views/BWDC-EducationEmployment-MedianAnnualEarnings/2MedianAnnualEarnings?:language=en-US&padding=0&:embed=y&:sid=&:redirect=auth&:origin=viz_share_link&:display_count=n&position=relative"
        >
          <button>🔍 View this BWDC graph in another tab</button> 
        </a>
      </div>
    {/snippet}

    {#snippet scrolly()}
      <ArticleText>
        <strong>Not much.</strong>
      </ArticleText>

      <ArticleText>
        <strong
          >Despite obtaining the same educational level,</strong
        > races differ greatly in their financial earnings.
      </ArticleText>

      <ArticleText
        > <strong>BWDC</strong> breaks it down clearly. Let's consider the median earnings for those who reached <u>high school completion</u>.
      </ArticleText>

      <ArticleText
        > <strong>Asian workers</strong> reported the most, followed by White workers. 
        <br /><br /> 
        Both fall within the <strong>$45K - $50K</strong> range.</ArticleText
      >

      <ArticleText
        ><strong>Next</strong>, Hispanic workers earned around <strong>$41K</strong>, followed by Black workers at around <strong>$37K</strong>.</ArticleText
      >

      <ArticleText><strong>Even though</strong> both groups obtained a high school diploma, there is more than a <u>$13K difference</u> between Asian earnings (highest) and Black earnings (lowest).</ArticleText>

      <ArticleText
        > <strong>This disparity</strong> continues if we consider those who obtained a <u>Bachelor's degree</u>.</ArticleText
      >

      <ArticleText
        ><strong>Ranking the worker earnings </strong> from highest to lowest,
        <ol> 
          <li>Asian (around $81K)</li>
          <li>White (around $70K)</li>
          <li>Hispanic (around $57K)</li>
          <li>Black (around $56K)</li>
        </ol>
        <br />
        This ranking is the same as that for workers who obtained a high school diploma. 
        <br /><br />
        Except now, there is more than a <u><strong>$25K</strong> difference</u> between Asian earnings and Black earnings.
        </ArticleText
      >

      <ArticleText><strong>All races</strong> received a higher level of education, yet Black workers still earned the least in the workforce. 
      </ArticleText>

      <ArticleText>
        <strong>In fact,</strong> Black workers earn the least in <strong><u>half</u></strong> of the education levels included in this BWDC visualization (4 out of 8 education levels).
        <br /><br /> Hispanic workers earn the least in the other 4 levels.
      </ArticleText>
    {/snippet}
  </Scroller>
</div>

<style>
  /* !!! need help </3 the data viz is not scaling to its max screen width */
  .tableau-container {
    max-width: 800px;
    position: relative;
    aspect-ratio: 4/3;
    margin: 0 auto;
    width: 100%;
  }
</style>
