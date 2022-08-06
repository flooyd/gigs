<script>
  import loginOrRegister from "../stores/auth";
  import Auth from "./Auth.svelte";
  import LoginForm from "./LoginForm.svelte";
</script>

<main>
  {#if !$loginOrRegister}
    <h1>Welcome 👋</h1>
    <p>I offer a variety of services at fixed prices!</p>
    <div class="serviceContainer">
      <div class="service">Business Window Washing</div>
      <div class="service">Residential Window Washing</div>
      <div class="service">Vehicle Window Washing</div>
      <div class="service">Vehicle Washing</div>
      <div class="service">Lawn Mowing</div>
    </div>
    <Auth />
  {/if}
  {#if $loginOrRegister}
    <LoginForm />
  {/if}
</main>

<style>
  main {
    margin-top: 50px;
    padding-top: 31px;
  }

  p {
    margin: 20px 0px;
    text-align: center;
  }

  .serviceContainer {
    width: fit-content;
    margin: 0 auto;
    text-align: left;
    border: 3px solid #333;
    padding: 13px;
  }

  .service {
    margin: 13px 0px;
    text-align: center;
    width: fit-content;
  }

  .service:before {
    content: "✅";
    margin-right: 20px;
  }
</style>
