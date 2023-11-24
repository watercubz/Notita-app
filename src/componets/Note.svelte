<script>
  export let title;
  export let color;
  export let text;
  export let id;

  import { darkmode } from "../store/store";

  import { createEventDispatcher } from "svelte";

  const dispatch = createEventDispatcher();

  function handleChange() {
    dispatch("update", {
      id: id,
      title: title,
      color: color,
      text: text,
    });
  }
  function handleColor() {
    dispatch("color", {
      id: id,
    });
  }

  function handleRemove() {
    dispatch("remove", {
      id: id,
    });
  }
</script>

<div class="Note">
  <div class="Note-container" style={"background-color:" + color}>
    <div class="header">
      <div class="options">
        <button on:click={handleColor}>
          <svg
            xmlns="http://www.w3.org/2000/svg"
            height="24"
            viewBox="0 -960 960 960"
            width="24"
            ><path
              d="M480-80q-82 0-155-31.5t-127.5-86Q143-252 111.5-325T80-480q0-83 32.5-156t88-127Q256-817 330-848.5T488-880q80 0 151 27.5t124.5 76q53.5 48.5 85 115T880-518q0 115-70 176.5T640-280h-74q-9 0-12.5 5t-3.5 11q0 12 15 34.5t15 51.5q0 50-27.5 74T480-80Zm0-400Zm-220 40q26 0 43-17t17-43q0-26-17-43t-43-17q-26 0-43 17t-17 43q0 26 17 43t43 17Zm120-160q26 0 43-17t17-43q0-26-17-43t-43-17q-26 0-43 17t-17 43q0 26 17 43t43 17Zm200 0q26 0 43-17t17-43q0-26-17-43t-43-17q-26 0-43 17t-17 43q0 26 17 43t43 17Zm120 160q26 0 43-17t17-43q0-26-17-43t-43-17q-26 0-43 17t-17 43q0 26 17 43t43 17ZM480-160q9 0 14.5-5t5.5-13q0-14-15-33t-15-57q0-42 29-67t71-25h70q66 0 113-38.5T800-518q0-121-92.5-201.5T488-800q-136 0-232 93t-96 227q0 133 93.5 226.5T480-160Z"
            /></svg
          ></button
        >
        <button on:click={handleRemove}>
          <svg
            xmlns="http://www.w3.org/2000/svg"
            height="24"
            viewBox="0 -960 960 960"
            width="24"
            ><path
              d="M280-120q-33 0-56.5-23.5T200-200v-520h-40v-80h200v-40h240v40h200v80h-40v520q0 33-23.5 56.5T680-120H280Zm400-600H280v520h400v-520ZM360-280h80v-360h-80v360Zm160 0h80v-360h-80v360ZM280-720v520-520Z"
            /></svg
          ></button
        >
      </div>
    </div>
    <div class="content">
      <div class="title">
        <input
          type="text"
          placeholder="Sin texto..."
          bind:value={title}
          on:change={handleChange}
        />
      </div>
      <div class="text">
        <textarea
          cols="30"
          rows="10"
          placeholder="Escribir..."
          bind:value={text}
          on:change={handleChange}
        ></textarea>
      </div>
    </div>
  </div>
</div>

<style>
  .Note {
    /* background-color: white; */
    border-radius: 3px;
    border: solid 2px transparent;
    height: 300px;
  }
  .Note-container {
    height: 100%;
    border-radius: 10px;
  }
  .Note-container:focus-within {
    border: solid 2px #000;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
  }
  .Note .Note-container .header {
    padding: 5px;
  }
  .header .options {
    display: flex;
    justify-content: space-between;
  }

  .Note .content {
    padding: 0 20px;
  }
  .text textarea {
    width: 100%;
    border: 0;
    outline: none;
    resize: none;
    height: 250px;
  }
  .title input {
    font-size: 22px;
    font-weight: bold;
    padding: 10px 0;
    outline: none;
    border: 0;
    width: 100%;
  }
  button {
    margin: 0;
    border: none;
    background-color: transparent;
    cursor: pointer;
  }
  textarea,
  input {
    background-color: transparent;
  }
</style>
