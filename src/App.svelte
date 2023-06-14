<script lang="ts">
  import projects from "./projects";

  function ageCalculator() {
    // YY/MM/DD FTW
    // Define the birth date as an object with year, month, and day properties.
    let birthDate = {
      year: 2009,
      month: 1,
      day: 8,
    };

    // Get the current date and time in UTC.
    let currentYear = new Date().getUTCFullYear();
    let currentDay = new Date().getUTCDate();
    let currentMonth = new Date().getUTCMonth();

    // Calculate the age by subtracting the birth year from the current year.
    let age = currentYear - birthDate.year;

    // If the birth month and day are later than the current month and day,
    // subtract 1 from the age to adjust for incomplete year.
    if (currentDay < birthDate.day && currentMonth < birthDate.month) age--;

    // Return the calculated age in years.
    return age;
  }
</script>

<main>
  <div class="top">
    <h1>&#123 Brisolo32 &#125</h1>
    <p>I do stuff</p>
  </div>
  <div class="about-contact">
    <div class="about">
      <p>
        Hey yall! Im Davi (AKA: Brisolo32), I'm {ageCalculator()} years old and learned
        coding at about 9. I know: TypeScript, Dart, Svelte, and a bit of Rust. Under
        this there will be some projects I've made and/or worked/colaborated!
      </p>
    </div>
    <div class="contact">
      <p id="contact-title">Contact:</p>
      <ul>
        <li>Twitter: @brisoli2</li>
        <li>
          Mastodon: <a rel="me" href="https://mastodon.social/@brisolo32"
            >@brisolo32</a
          >
        </li>
        <li>Reddit: u/OkTaien</li>
        <li>Discord: Brisolo32#2968</li>
        <li>Github: Brisolo32</li>
      </ul>
    </div>
  </div>
  <div class="projects">
    {#each projects.projects as project}
      <div class="card">
        <div class="img"><img src={project.icon} alt="" /></div>
        <span>{project.name}</span>
        <p>{project.desc}</p>
      </div>
    {/each}
  </div>
</main>

<style>
</style>
