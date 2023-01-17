<script>
  let people = [
    { name: "yoshi", beltColour: "black", age: 25, id: 1 },
    { name: "mario", beltColour: "orange", age: 45, id: 2 },
    { name: "luigi", beltColour: "brown", age: 35, id: 3 },
  ];
</script>

<main>
  {#each people as person (person.id)}
    <h4>{person.name}</h4>
    <p>{person.age} years old, {person.beltColour} belt.</p>
  {:else}
    <p>There are no people to show...</p>
  {/each}
</main>
