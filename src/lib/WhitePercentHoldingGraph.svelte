<script>
  import { onMount } from "svelte";

  onMount(() => {
    var divElement = document.getElementById("viz1753070375687");
    var vizElement = divElement.getElementsByTagName("object")[0];
    vizElement.style.width = "800px";
    vizElement.style.height = "550px";
    var scriptElement = document.createElement("script");
    scriptElement.src = "https://public.tableau.com/javascripts/api/viz_v1.js";
    vizElement.parentNode.insertBefore(scriptElement, vizElement);
  });
</script>

<div class="container">
  <div
    class="tableauPlaceholder"
    id="viz1753070375687"
    style="position: relative"
  >
    <noscript>
      <!-- svelte-ignore a11y_invalid_attribute -->
      <a href="#">
        <img
          alt="ADT08 "
          src="https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;GB&#47;GB9BGN8RQ&#47;1_rss.png"
          style="border: none"
        />
      </a>
    </noscript>
    <!-- svelte-ignore a11y_missing_attribute -->
    <object class="tableauViz" style="display:none;">
      <param name="host_url" value="https%3A%2F%2Fpublic.tableau.com%2F" />
      <param name="embed_code_version" value="3" />
      <param name="path" value="shared&#47;GB9BGN8RQ" />
      <param name="toolbar" value="yes" />
      <param
        name="static_image"
        value="https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;GB&#47;GB9BGN8RQ&#47;1.png"
      />
      <param name="animate_transition" value="yes" />
      <param name="display_static_image" value="yes" />
      <param name="display_spinner" value="yes" />
      <param name="display_overlay" value="yes" />
      <param name="display_count" value="yes" />
      <param name="language" value="en-US" />
      <param name="origin" value="viz_share_link" />
      <param name="filter" value="padding=0" />
      <param name="filter" value="position=relative" />
    </object>
  </div>
</div>

<style>
</style>
