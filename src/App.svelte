<script>
  let beltColor = "black";
  const changeColor = () => {
    beltColor = "orange";
  };
  const handleInput = (e) => {
    beltColor = e.target.value;
  };
</script>

<main>
  <p style="color: {beltColor};">{beltColor} Color</p>
  <button on:click={changeColor}>Change beltColor</button>
  <!-- <input type="text" on:input={handleInput} value={beltColor} /> -->
  <input type="text" bind:value={beltColor} />
</main>
