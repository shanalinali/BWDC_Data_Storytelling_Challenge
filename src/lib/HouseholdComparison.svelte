<script>
    let degree = "None";
  
    const outcomes = {
      "None": "Lower job access, high financial risk",
      "High School": "Limited job security, modest earnings",
      "Bachelor's": "Higher earnings, but not guaranteed security",
      "Graduate": "More job options, but also more debt risk"
    };
  </script>
 
 <!-- TODO: Need to actually edit the content -->
<div>
    <!-- svelte-ignore a11y_label_has_associated_control -->
    <label>Household + Education Level:</label>
    <select bind:value={degree}>
    <option>None</option>
    <option>High School</option>
    <option>Bachelor's</option>
    <option>Graduate</option>
  </select>
  
  <p><br>Their net worth exceeds: <br>{outcomes[degree]}</p>

</div>

<style>
</style>