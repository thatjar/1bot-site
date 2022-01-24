<svelte:head>
  <title>1Bot - One bot, several uses.</title>
</svelte:head>

<div class="intro">
  <h1 class="outfit">
    <span class="grey">Meet</span> 1Bot.
  </h1>
  <i class="grey">One bot, several uses.</i>
  <a href="https://dsc.gg/1bot" id="add-1bot" class="outfit">Add 1Bot</a>
</div>

<div class="features">
  <section class="card">
    <h2 class="outfit">Free</h2>
    <p>
      1Bot is completely free to use for everyone. There are no pay-to-use
      features, or even a requirement to vote!
    </p>
  </section>

  <section class="card">
    <h2 class="outfit">Easy to use</h2>
    <p>
      If you're familiar with Discord Bots, using 1Bot is a breeze. Slash
      Commands are also fully supported!
    </p>
  </section>

  <section class="card">
    <h2 class="outfit">Multipurpose</h2>
    <p>
      1Bot is a truly multipurpose bot, with commands for Moderation, Fun, Image
      Manipulation and a lot more.
    </p>
  </section>
</div>

<style>
  .intro {
    display: flex;
    gap: 10px;
    flex-direction: column;
    align-items: center;
    text-align: center;
  }

  .intro h1 {
    font-size: 3em;
    margin: 15px auto;
  }

  .intro i {
    font-size: 1.25em;
  }

  .grey {
    color: #d1d1d1;
  }

  #add-1bot {
    color: black;
    display: block;
    width: 125px;
    margin: 20px;
    padding: 10px 0;
    text-decoration: none;
    font-size: 1.5em;
    background-image: linear-gradient(to top right, #ff6600, #ff8800);
    border-radius: 5px;

    transition: 300ms;
  }

  #add-1bot:hover {
    box-shadow: 0 2px 4px #d471008e;
    transform: translateY(-2px);
  }

  #add-1bot:active {
    transform: translateY(2px);
    box-shadow: none;
  }

  .features {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-evenly;
    align-items: center;
    margin: 40px auto;
  }

  .features .card {
    display: flex;
    flex-direction: column;
    line-height: 1.5em;
    text-align: center;
    justify-content: space-between;
    width: 220px;
    height: 190px;
    margin: 10px 5px;
    padding: 25px 30px;
    background-color: #30333d;
    border-radius: 15px;
    box-shadow: 0 6px 10px #1c1d24;
  }

  .card h2 {
    margin: 10px;
  }
</style>
