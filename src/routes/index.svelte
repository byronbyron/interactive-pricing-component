<script>
  let output = '100K';
  let price = '$16.00';
  let fillLower = '50%';

  const handleInput = (e) => {
    let values = [
      ['10K', '$8.00'],
      ['50K', '$12.00'],
      ['100K', '$16.00'],
      ['500K', '$24.00'],
      ['1M', '$36.00'],
    ];
    output = values[e.target.value][0];
    price = values[e.target.value][1]
    fillLower = (e.target.value / e.target.max) * 100 + '%';
  }
</script>

<form>
  <div class="form-main">
    <p class="views">
      <output>{output}</output> Pageviews
    </p>

    <div class="form-range" style="--range: {fillLower}">
      <input id="rangeInput" type="range" min="0" value="2" max="4" step="1" on:input={handleInput}>
    </div>

    <p class="price">
      <strong><output>{price}</output></strong> / month
    </p>

    <!-- Rounded switch -->
    <div class="control">
      <label for="billing">Monthly Billing</label>

      <label class="switch">
        <input type="checkbox" id="billing">
        <span class="slider round"></span>
      </label>

      <label for="billing">
        <span>Yearly Billing</span>

        <span class="discount">
          -25% <span class="">discount</span>
        </span>
      </label>
    </div>
  </div>

  <div class="form-footer">
    <ul>
      <li>Unlimited websites</li>
      <li>100% data ownership</li>
      <li>Email reports</li>
    </ul>

    <button>Start my trial</button>
  </div>
</form>

<style>
  form {
    font-size: 0.8125rem;
    min-height: 478px;
    display: flex;
    flex-direction: column;
    text-align: center;
    background: var(--white);
    border-radius: 0.5rem;
  }

  .form-range {
    margin-bottom: 1.3rem;
  }

  .form-main {
    padding: 2rem 1.5rem 2.375rem;
  }

  .form-footer {
    padding: 1.5rem 1.5rem 2rem;
    border-top: 1px solid var(--light-grayish-blue);
  }

  .views {
    font-weight: 800;
    text-transform: uppercase;
    letter-spacing: 0.1em;
    margin-bottom: 1.375rem;
  }

  .price {
    font-size: 0.875rem;
    display: flex;
    align-items: center;
    justify-content: center;
    margin-bottom: 1.875rem;
  }

  .price strong {
    font-size: 2rem;
    letter-spacing: -0.025em;
    margin-right: 0.625rem;
    color: var(--dark-desaturated-blue);
  }

  .control {
    display: flex;
    align-items: center;
    justify-content: center;
    margin-left: -0.875rem;
  }

  label {
    font-size: 0.75rem;
    position: relative;
    display: flex;
    align-items: center;
  }

  .discount {
    font-size: 0.625rem;
    font-weight: 800;
    line-height: 1.125rem;
    display: inline-block;
    background-color: var(--light-grayish-red);
    color: var(--light-red);
    width: 2.5rem;
    height: 1.125rem;
    border-radius: 1.125rem;
    position: absolute;
    left: 100%;
    margin-left: 0.25rem;
  }

  .discount span {
    position: absolute;
    width: 1px;
    height: 1px;
    padding: 0;
    margin: -1px;
    overflow: hidden;
    clip: rect(0,0,0,0);
    white-space: nowrap;
    border: 0;
  }

  ul {
    font-size: 0.75rem;
    list-style: none;
    margin: 0 0 1.875rem;
    padding-left: 0;
  }

  li {
    margin-bottom: 0.5rem;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  li::before {
    content: '';
    display: block;
    background: url('/icon-check.svg') no-repeat top left;
    background-size: 9px 8px;
    width: 9px;
    height: 8px;
    margin-right: 0.875rem;
  }

  button {
    font-size: 0.75rem;
    font-weight: 800;
    max-width: 170px;
    width: 100%;
    height: 2.5rem;
    color: var(--pale-blue);
    border: 0;
    border-radius: 2.5rem;
    background-color: var(--dark-desaturated-blue);
    cursor: pointer;
    transition: color 0.15s;
  }

  button:hover,
  button:focus {
    color: var(--white);
  }
</style>
