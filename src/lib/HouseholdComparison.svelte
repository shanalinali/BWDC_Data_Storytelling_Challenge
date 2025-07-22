<script>
    let degree = "None";
  
    const outcomes = {
      "": "______",
      "White + No High school diploma": "(1) Black and Other race households with some College or Associate's degree\n\n(2) Black and Hispanic households with a High school diploma\n\n(3) Black, Hispanic, and Other race households with no High school diploma",
      "White + High school diploma": "(1) Black households with a Bachelor's degree\n\n(2) Black, Hispanic, and Other race households with some College or Associate's degree\n\n(3) Black, Hispanic, and Other race households with a High school diploma",
      "White + Some college or Associate degree": "(1) Black households with a Bachelor's degree\n\n(2) Black, Hispanic, and Other race households with some College or Associate's degree",
      "White + Bachelor's Degree or higher": "(1) Black, Hispanic, and Other race households with a Bachelor's degree"
    };

    const medianNetWorth = {
        "":"______",
        "White + No High school diploma": "$73K",
        "White + High school diploma": "$153K",
        "White + Some college or Associate degree": "$199K",
        "White + Bachelor's Degree or higher":"$579K"
    };
  </script>
 
<div class="container">
    <!-- svelte-ignore a11y_label_has_associated_control -->
    <label>Household + Highest Education Level:</label>
    <select bind:value={degree}>
    <option></option>
    <option>White + No High school diploma</option>
    <option>White + High school diploma</option>
    <option>White + Some college or Associate degree</option>
    <option>White + Bachelor's Degree or higher</option>
  </select>
  
  <p><br><u>In 2022, their median net worth was </u><br>{medianNetWorth[degree]}<br><br> <u>This exceeded <br></u>{outcomes[degree]}</p>

</div>

<style>
.container {
  font-family:'Segoe UI';
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
  width: 100%;
}

p {
  white-space: pre-line;
}

select {
  background-color: #5A0001;
  color: #F6E8EA;
  /* Used ChatGPT to improve dropdown responsiveness/layout across devices */
  padding: 0.5rem;
  border-radius: 4px;
  border: 1px solid #5A0001;
  max-width: 100%;
  box-sizing: border-box;
  font-size: 1rem;
}

label {
  border: solid #5a0001 medium;
  padding: 5px;
}
</style>