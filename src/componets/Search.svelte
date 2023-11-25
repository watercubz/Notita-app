<script>
</script>

<div class="Search">
  <input type="text" placeholder="Search..." on:input />
</div>

<style>
  input {
    display: block;
    width: 500px;
    padding: 10px;
    padding-left: 2.5rem;
    font-size: 0.875rem;
    color: #333;
    border: 1px solid #ccc;
    border-radius: 0.375rem;
    background-color: #f2eee2;
    outline: none;
    transition:
      border-color 0.15s ease-in-out,
      box-shadow 0.15s ease-in-out;
  }

  @media (max-width: 600px) {
    input {
      width: 100%;
      max-width: none;
    }
  }
</style>
