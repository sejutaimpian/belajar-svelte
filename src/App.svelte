<script>
  let firstName = "Udin";
  let lastName = "Saepudin";
  let beltColor = "black";

  $: fullName = `${firstName} ${lastName}`;

  const changeColor = () => {
    beltColor = "orange";
  };
  const handleInput = (e) => {
    beltColor = e.target.value;
  };
</script>

<main>
  <!-- <p>{firstName} {lastName} - {beltColor} Color</p> -->
  <p>{fullName} - {beltColor} Color</p>
  <input type="text" bind:value={firstName} />
  <input type="text" bind:value={lastName} />
  <input type="text" bind:value={beltColor} />
</main>
