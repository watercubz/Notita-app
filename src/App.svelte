<script>
  import Dashboard from "./componets/Dashboard.svelte";
  import Header from "./componets/Header.svelte";

  import { v4 } from "uuid";

  import Note from "./componets/Note.svelte";

  import { darkmode } from "./store/store";

  let notes = [
    {
      id: 0,
      title: "Hi, soy watercubz",
      color: "yellow",
      text: "Bienvenido a Notita ❤️",
    },
  ];
  let copyNotes = [...notes];

  $: count = notes.length;

  function handleNew() {
    const color = generateColor();
    const id = v4();
    const note = {
      id: id,
      title: "",
      color: color,
      text: "",
    };
    notes = [note, ...notes];
    copyNotes = [...notes];
  }

  function generateColor() {
    const colors = [
      "#C0C0C0",

      "#FF0000",
      "#800000",

      "#80080",

      "#FFA500",

      "#FA8072",
      ,
    ];
    const index = Math.floor(Math.random() * colors.length);
    return colors[index];
  }

  function handleUpdate(e) {
    const note = e.detail;
    const index = notes.findIndex((n) => n.id === note.id);
    note[index] = note;
  }

  function handleColor(e) {
    const index = notes.findIndex((n) => n.id === e.detail.id);
    notes[index].color = generateColor();
    copyNotes = [...notes];
  }

  function handleRemove(e) {
    const response = notes.filter((n) => n.id !== e.detail.id);

    notes = [...response];

    copyNotes = [...notes];
  }

  function handleSearch(e) {
    const q = e.target.value;

    if (q === "") {
      copyNotes = [...notes];
      return false;
    }
    const results = notes.filter((note) => {
      const title = note.title.toLocaleLowerCase();
      const text = note.text.toLocaleUpperCase();

      return title.indexOf(q) > -1 || text.indexOf(q) > -1;
    });

    copyNotes = [...results];
  }
</script>

<main>
  <Header on:input={handleSearch} />
  <div class="count-notes">{count} notas</div>
  <Dashboard
    bind:notes={copyNotes}
    on:click={handleNew}
    on:update={handleUpdate}
    on:color={handleColor}
    on:remove={handleRemove}
  />
</main>

<style>
  :global(body) {
    margin: 0;
    padding: 0;
  }

  .count-notes {
    padding: 20px 20px 0 20px;
    text-align: right;
  }
</style>
