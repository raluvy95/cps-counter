<script>
  let click = 0;
  let totalclick = 0;
  let cps = 0;

  function onClick() {
    click++;
    totalclick++;
    document.getElementById("clickarea").innerText = `${cps} CPS`;
  }

  function reset() {
    click = 0
    totalclick = 0
    cps = 0
  }

  setInterval(() => {
    cps = click / 2;
    click = 0;
  }, 2 * 1000);
</script>

<main>
  <h1>CPS Counter</h1>
  <p>Show how fast you can click in 2 seconds!</p>
  <button on:click={reset}>Reset</button>
  <br>
  <p>Click: {click} | Total click: {totalclick}</p>
  <div id="clickarea" on:click={onClick} on:keypress={onClick}>
    <p>Click here to start!</p>
  </div>
  <p><a href="https://github.com/raluvy95/cps-counter">This project is open source</a></p>
</main>
