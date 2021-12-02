<svelte:head>
  <title>1Bot - One bot, several uses.</title>
</svelte:head>

<div class="large-intro">
  <div>
    <h1 class="config">Meet 1Bot.</h1>
    <i>One bot, several uses.</i>
    <a href="https://dsc.gg/1bot" id="add-1bot" class="config">Add 1Bot</a>
  </div>

  <img src="/1bot.png" alt="Logo" />
</div>

<div class="features">
  <section class="card">
    <h2 class="config">Free</h2>
    <p>
      1Bot is completely free to use for everyone. There are no pay-to-use
      features, or even a requirement to vote!
    </p>
  </section>

  <section class="card">
    <h2 class="config">Easy to use</h2>
    <p>
      If you're familiar with Discord Bots, using 1Bot is a breeze. Slash
      Commands are also fully supported!
    </p>
  </section>

  <section class="card">
    <h2 class="config">Multipurpose</h2>
    <p>
      1Bot is a truly multipurpose bot, with commands for Moderation, Fun, Image
      Manipulation and a lot more.
    </p>
  </section>
</div>

<style>
  .large-intro {
    display: flex;
    justify-content: space-evenly;
    align-items: center;
    flex-wrap: wrap-reverse;
    text-align: center;
  }

  .large-intro > * {
    margin: 0 15px;
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .large-intro img {
    width: 12vw;
    min-width: 50px;
    max-width: 10vw;
  }

  .large-intro h1 {
    font-size: 3em;
  }

  .large-intro h1:after {
    content: "";
    display: block;
    position: relative;
    top: 5px;
    height: 5px;
    background-image: linear-gradient(to bottom right, #ff8f00, #ff6000);
    border-radius: 10px;
  }

  .large-intro i {
    font-size: 1.25em;
  }

  #add-1bot {
    color: black;
    display: block;
    width: 100px;
    margin: 20px;
    padding: 10px 0;
    text-decoration: none;
    font-size: 1.25em;
    background-color: #ff8000;
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
    margin-top: 40px;
  }

  .features .card {
    display: flex;
    flex-direction: column;
    line-height: 1.5em;
    text-align: center;
    justify-content: space-between;
    width: 200px;
    height: 200px;
    margin: 10px;
    padding: 15px;
    background-color: #292c36;
    border: 3px solid #ff8000;
    box-shadow: 0 6px 10px #1c1d24;
  }

  .card h2 {
    margin: 10px;
  }
</style>
