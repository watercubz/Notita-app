<script>
  import { darkmode } from "../store/store";

  function handleClick() {
    darkmode.update((darkmode) => !darkmode);
  }
</script>

<div class="Switch">
  <div class="switch-container">
    <button class="circle" on:click={handleClick}></button>
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
