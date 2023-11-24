<script>
  import { darkmode } from "../store/store";

  function handleClick() {
    darkmode.update((darkmode) => !darkmode);
  }

  function toggle() {
    window.document.body.classList.toggle("dark-mode");
  }
</script>

<div class="Switch">
  <div class="switch-container">
    <button class="circle" on:click={toggle}></button>
  </div>
</div>

<style>
  .Switch {
    background-color: #ccc;
    width: 50px;
    height: 25px;
    border-radius: 30px;
    margin: 0 10px;
  }
  .switch-container .circle {
    cursor: pointer;
    width: 25px;
    height: 25px;
    border-radius: 50%;
    transition: all 0.2s;
    border: none;
  }
  button {
    background-color: #f76027;
    color: white;
    border: none;
    border-radius: 4px;
    padding: 0.5rem;
    text-transform: uppercase;
  }
  :global(body.dark-mode) button {
    background-color: #0084f6;
    color: white;
  }
  @media (max-width: 600px) {
    .Switch {
      width: 40px;
      height: 20px;
      margin: 0 5px;
    }

    .switch-container .circle {
      width: 20px;
      height: 20px;
    }
  }
</style>
