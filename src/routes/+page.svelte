<main class="container">
  <form class="control-group">
    <h1>Checkboxes</h1>
    <label>
      <input type="checkbox" checked />
      <span class="label-text">First Checkbox</span>
    </label>
    <label>
      <input type="checkbox" />
      <span class="label-text">Second Checkbox</span>
    </label>
    <label>
      <input type="checkbox" disabled />
      <span class="label-text">Disabled</span>
    </label>
    <label>
      <input type="checkbox" disabled checked />
      <span class="label-text">Disabled & checked</span>
    </label>
  </form>
</main>

<style>
  /* Bonus 7 not done, but we understand how to do it (by hiding the original checkbox and creating "impostors" via :before & :after) */
  :global(html, body) {
    height: 100%;
    --bg-checked: #2aa1c0;
    --bg-unchecked: #e6e6e6;
  }
  :global(body) {
    background: #e6e6e6;
    font-family: 'Source Sans Pro', sans-serif;
  }

  .container {
    width: 100%;
    height: 100%;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
  }

  label {
    display: block;
    margin-bottom: 0.5rem;
  }

  input {
    -webkit-appearance: none;
    appearance: none;
    background-color: var(--bg-unchecked);
    margin: 0;
    font: inherit;
    color: currentColor;
    width: 1.15em;
    height: 1.15em;
    border: none;
    transform: translateY(-0.075em);
  }

  input:checked,
  input:checked:is(:focus, :hover, :hover:focus) {
    background-color: var(--bg-checked);
  }

  input:disabled {
    cursor: not-allowed;
    background-color: var(--bg-unchecked) !important;
  }

  input:disabled ~ .label-text {
    cursor: not-allowed;
    color: var(--bg-unchecked);
  }

  h1 {
    font-family: 'Alegreya Sans', sans-serif;
    font-weight: 300;
    font-size: 2rem;
    margin-top: 0;
    margin-bottom: 1rem;
  }

  .control-group {
    background: #fff;
    box-shadow: 0 1px 2px rgba(0, 0, 0, 0.1);
    padding: 30px;
    padding-right: 3rem;
    margin: 10px;
    padding-bottom: 3rem;
  }
</style>
