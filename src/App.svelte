<script>
  import Faq from "./lib/Faq.svelte";

  import iconStar from "./assets/icon-star.svg";

  let faqs = [
    {
      id: 1,
      title: "What is Frontend Mentor, and how will it help me?",
      content:
        "Frontend Mentor offers realistic coding challenges to help developers improve their frontend coding skills with projects in HTML, CSS, and JavaScript. It's suitable for all levels and ideal for portfolio building.",
    },
    {
      id: 2,
      title: "Is Frontend Mentor free?",
      content:
        "Yes, Frontend Mentor offers both free and premium coding challenges, with the free option providing access to a range of projects suitable for all skill levels.",
    },
    {
      id: 3,
      title: "Can I use Frontend Mentor projects in my portfolio?",
      content:
        "Yes, you can use projects completed on Frontend Mentor in your portfolio. It's an excellent way to showcase your skills to potential employers!",
    },
    {
      id: 4,
      title: "How can I get help if I'm stuck on a Frontend Mentor challenge?",
      content:
        "The best place to get help is inside Frontend Mentor's Discord community. There's a help channel where you can ask questions and seek support from other community members.",
    },
  ];
</script>

<main class="main">
  <div class="container">
    <div class="title">
      <img src={iconStar} alt="Star Icon" />
      <h1>FAQs</h1>
    </div>

    <div class="faqs-container">
      {#each faqs as faq (faq.id)}
        <Faq {faq} />
        {#if faq.id !== faqs.length}
          <hr />
        {/if}
      {/each}
    </div>
  </div>
</main>

<style>
  .main {
    display: flex;
    align-items: center;
    justify-content: center;

    max-height: 100%;
    min-height: 100vh;
    background-image: url("./assets/background-pattern-desktop.svg");
    background-repeat: no-repeat;
    background-color: hsl(275, 100%, 97%);
    background-size: 100% auto;
    padding: 2.4rem 0;
  }

  @media only screen and (max-width: 42.5rem) {
    .main {
      background-image: url("./assets/background-pattern-mobile.svg");
    }
  }

  .container {
    max-width: 51.2rem;
    width: 91.666667%;
    padding: 3.2rem;
    background-color: hsl(0, 0%, 100%);
    border-radius: 0.8rem;
    box-shadow:
      0 20px 25px -5px rgb(0 0 0 / 0.1),
      0 8px 10px -6px rgb(0 0 0 / 0.1);
  }

  .title {
    display: flex;
    align-items: center;
    gap: 2rem;

    margin-bottom: 3.2rem;
  }

  .title h1 {
    font-size: 4.8rem;
    font-weight: 700;
    line-height: 1;
  }

  .faqs-container {
    display: flex;
    flex-direction: column;
    gap: 0.8rem;
  }

  .faqs-container hr {
    margin: 1.6rem 0;
    border-top: 1px solid hsl(275, 100%, 97%);
  }
</style>
