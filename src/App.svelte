<script>
  import logo from './assets/logo.png'
  import Counter from './lib/Counter.svelte'
</script>

<main>
  <h1>Andi Erni's Storage Test</h1>
    <img src={logo} alt="DFINITY logo" />
    <h2>This is an example of Orthogonal persistence</h2>
    <h3>No need for database anymore!!!</h3>
    <p>
      State is saved directly in WebAssembly canister on the Internet Computer's
      blockchain.
    </p>
</main>

<Counter/>

<style>
  
h1 {
  color: #3face2;
  font-family: "Open Sans Condensed", sans-serif;
  font-size: 54px;
  font-weight: 700;
  line-height: 54px;
  margin: 20 0 0 0;
  padding: 20px 30px;
  text-align: center;
  text-transform: uppercase;
}

h2 {
  color: #111;
  font-family: "Open Sans Condensed", sans-serif;
  font-size: 38px;
  font-weight: 700;
  line-height: 38px;
  margin: 0 0 24px;
  padding: 0 30px;
  text-align: center;
  text-transform: none;
}

h3 {
  color: #111;
  font-family: "Open Sans Condensed", sans-serif;
  font-size: 28px;
  font-weight: 700;
  line-height: 28px;
  margin: 0 0 24px;
  padding: 0 30px;
  text-align: center;
  text-transform: none;
}

p {
  color: #3face2;
  font-family: "Open Sans", sans-serif;
  font-size: 16px;
  line-height: 28px;
  margin: 0 0 48px;
  padding: 0 30px;
  text-align: center;
  text-transform: none;
}

img {
  max-width: 20vw;
  max-height: 10vw;
  display: block;
  margin: auto;
}

</style>
