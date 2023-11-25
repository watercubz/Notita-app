<script>
  import { darkmode } from "../store/store";

  // function handleClick() {
  //   darkmode.update((darkmode) => !darkmode);
  // }

  function toggle() {
    window.document.body.classList.toggle("dark-mode");
  }
</script>

<div class="Switch">
  <div class="switch-container">
    <button class="circle" on:click={toggle}>
      <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path
          d="M3.32031 11.6835C3.32031 16.6541 7.34975 20.6835 12.3203 20.6835C16.1075 20.6835 19.3483 18.3443 20.6768 15.032C19.6402 15.4486 18.5059 15.6834 17.3203 15.6834C12.3497 15.6834 8.32031 11.654 8.32031 6.68342C8.32031 5.50338 8.55165 4.36259 8.96453 3.32996C5.65605 4.66028 3.32031 7.89912 3.32031 11.6835Z"
          stroke="#000000"
          stroke-width="2"
          stroke-linecap="round"
          stroke-linejoin="round"
        />
      </svg>
    </button>
  </div>
</div>

<style>
  /* .Switch {
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
  } */
  button {
    background-color: #f76027;
    color: white;
    border: none;
    border-radius: 4px;
    padding: 0.5rem;
    text-transform: uppercase;
    width: 30px;
    height: 30px;
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
