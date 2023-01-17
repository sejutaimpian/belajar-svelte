<script>
  let people = [
    { name: "yoshi", beltColour: "black", age: 25, id: 1 },
    { name: "mario", beltColour: "orange", age: 45, id: 2 },
    { name: "luigi", beltColour: "brown", age: 35, id: 3 },
  ];

  let num = 5;

  const handleClick = (e, id) => {
    people = people.filter((person) => person.id != id);
    console.log(e);
  };
</script>

{#if num > 20}
  <p>Greater than 20</p>
{:else if num > 5}
  <p>Greater than 5</p>
{:else}
  <p>Not greater than 5</p>
{/if}
<main>
  {#each people as person (person.id)}
    <h4>{person.name}</h4>
    {#if person.beltColour === "black"}
      <p><strong>MASTER NINJA</strong></p>
    {/if}
    <p>{person.age} years old, {person.beltColour} belt.</p>
    <button on:click={(e) => handleClick(e, person.id)}>delete</button>
  {:else}
    <p>There are no people to show...</p>
  {/each}
</main>
