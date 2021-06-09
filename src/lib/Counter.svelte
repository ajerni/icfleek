<script>
  import { onMount } from "svelte"
  import { counter } from "../agent"
   
  var displayWert = "...getting current state...";
  var inputValue = "";

  $: wert = inputValue; //dynamically processd value (geht auch mit ganzen code blocks etc.)

  const getWert =  async () => {
    const res = await counter.getWert();
    displayWert = res.toString();
  }

  const setWert = async () => {
    displayWert = "...saving new state...";
    const result = await counter.setWert(wert);
    displayWert = result.toString();
  }

  onMount(getWert);

</script>


<div>
<section >
  <label id="lab" for="wert">Enter new state: &nbsp;</label>
  <input bind:value={inputValue} id="wert" alt="Wert" type="text" />
  <button id="clickMeBtn2" on:click={setWert}>Change State</button>
</section>
</div>
<h4>Current state:</h4>
<section id="showwert">{displayWert}</section>


<style>

#lab{  
  color:#ee1f7a;
  font-size: calc(15px + 1vmin);
}

#wert{
  font-size: calc(10px + 2vmin);
}

button {
    font-size: calc(10px + 2vmin);
    background: linear-gradient(237.86deg, #532885 -20%, #ee1f7a 124%);
    padding: 0 2em;
    border-radius: 60px;
    font-size: 0.7em;
    line-height: 40px;
    outline: 0;
    border: 0;
    cursor: pointer;
    text-transform: uppercase;
    font-weight: 900;
    color: white;
  }

  h4 {
  color: #3face2;
  font-family: "Open Sans Condensed", sans-serif;
  font-size: 28px;
  font-weight: 700;
  line-height: 28px;
  margin: 0 0 0;
  padding: 10px 15px;
  text-align: center;
  text-transform: uppercase;

}

  section {
  display: flex;
  flex-flow: row wrap;
  max-width: 40vw;
  margin: auto;
  align-items: center;
}

#clickMeBtn2 {
  padding: 5px 20px;
  margin: 10px auto;
  float: right;
}

#showwert {
  margin: 10px auto;
  padding: 10px 60px;
  border: 1px solid #222;
}

#showwert:empty {
  display: none;
}
</style>
