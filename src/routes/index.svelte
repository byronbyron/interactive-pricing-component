<script>
  let output = '100K';
  let fillLower = '50%';

  // 10K pageviews / $8 per month
  // 50K pageviews / $12 per month
  // 100K pageviews / $16 per month
  // 500k pageviews / $24 per month
  // 1M pageviews / $36 per month

  const handleInput = (e) => {
    let values = ['10K', '50K', '100K', '500K', '1M'];
    output = values[e.target.value];
    fillLower = (e.target.value / e.target.max) * 100 + '%';
  }
</script>

<form>
  <div class="form-main">
    <p class="page-views">
      <output>{output}</output> Pageviews
    </p>

    <div class="form-range" style="--range: {fillLower}">
      <input id="rangeInput" type="range" min="0" value="2" max="4" step="1" on:input={handleInput}>
    </div>

    <p>$<span>16</span> /month</p>

    <div>
      <span>Monthly Billing</span>

      <!-- Rounded switch -->
      <label class="switch">
        <input type="checkbox">
        <span class="slider round"></span>
      </label>

      <span>Yearly Billing</span>

      <span>25% discount</span>
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
    margin-bottom: 2rem;
  }

  .form-main {
    padding: 2rem 1.5rem;
  }

  .form-footer {
    margin-top: auto;
    padding: 1.5rem 1.5rem 2rem;
    border-top: 1px solid var(--light-grayish-blue);
  }

  .page-views {
    font-weight: 800;
    text-transform: uppercase;
    letter-spacing: 0.1em;
    margin-bottom: 1.375rem;
  }
</style>
