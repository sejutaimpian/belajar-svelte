<script>
  import Modal from "./lib/Modal.svelte";

  let showModal = false;

  let people = [
    { name: "yoshi", beltColour: "black", age: 25, id: 1 },
    { name: "mario", beltColour: "orange", age: 45, id: 2 },
    { name: "luigi", beltColour: "brown", age: 35, id: 3 },
  ];

  const handleClick = (e, id) => {
    people = people.filter((person) => person.id != id);
    console.log(e);
  };
  let toggleModal = () => {
    showModal = !showModal;
  };
</script>

<Modal message="Hello, Ninjas!" {showModal} on:click={toggleModal} />
<main>
  <button on:click|once={toggleModal}>Open Modal</button>
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

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }
  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
