<script lang="ts">
  import { onMount } from 'svelte';

  // Initialize time
  let time = new Date();

  // These automatically update when `time` changes, because of the `$:` prefix
  $: dag = time.toLocaleString('default', { day: 'numeric' })
  $: maand = time.toLocaleString('default', { month: 'long' })
  $: aantal = (Math.round(time / 1000) - 1556136821).toLocaleString();

  onMount(() => {
    // Update time every second
    const interval = setInterval(() => {
      time = new Date();
    }, 1000);

    // Will be called when the component is unmounted.
    return () => {
      clearInterval(interval);
    };
  });
</script>
<header>
  <div class="header">
    <div class="logobar">
      <div class="logo">
        <a href="#">
          <img src="img/logo-RO.svg" alt="Logo Rijksoverheid"/>
        </a>
      </div>
      <a href="#" class="header__layout__faq-link">
        Veelgestelde vragen
      </a>
      <div class="language-picker language-picker--home language-picker--right-orientation">
        <span class="language-picker__current">
          <span class="language-picker__label"> Taal: </span>
          <strong>Nederlands</strong>
        </span>
        <button type="button" class="language-picker__toggle" aria-controls="language-dropdown" aria-expanded="false">
          <span class="screen-reader-text"> Wissel van taal </span>
          <span class="language-picker__chevron"></span>
        </button>
      </div>
    </div>
    <div class="container">
      <div class="header__layout">
        <img src="img/angular-logo-RO.png" class="header__logo-badge" alt="Logo CoronaMelder app">
        <div class="header__layout__middle">
          <h1 class="header__text">
            Voorkom verspreiding,<br/>
            Stop Angular
          </h1>
        </div>
      </div>
    </div>
  </div>
</header>

<main id="content">
  <div class="container">
    <div class="lead">
      <div class="lead__text">
        <div class="content-block">
          <div class="md-block-lead">
            <p>
              Angular wordt altijd nog gebruikt. Dus is het belangrijk om juist nu alert te blijven. Daarom is
              FuckAngular nu te gebruiken voor heel Nederland. Op {dag} {maand} zijn al <strong>{aantal}</strong> Angular
              projecten verwijderd.
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
  <div class="stories">
    <article class="stories__story" id="story-1">
      <div class="stories__story-column-image">
        <h2>
          <span class="stories__story-title__highlight">Waarom is dit belangrijk?</span>
          <span class="stories__story-title">Help de verspreiding tegen te gaan</span>
        </h2>
        <p class="stories__story-text">
          Het deelnemen aan het programma is niet vrijwillig. <br/>
          Als u niet toestaat uw computer te controleren wordt deze meteen vernietigd.
        </p>
      </div>
      <div class="stories__story-column-content">
        <h2>
          <span class="stories__story-title__highlight">Hoe werkt het?</span>
          <span class="stories__story-title">Uw computer wordt onderzocht</span>
        </h2>
        <p class="stories__story-text">
          Bij het aantreffen van 1 of meer Angular projecten wordt deze computer in beslag genomen en vernietigd.
        </p>
      </div>
    </article>
  </div>
</main>

<footer>
  <div class="footer-samen">
    <a class="footer-samen__logo" href="#">
      <img src="img/logo-alleen-samen.png"
           alt="Alleen samen krijgen we Angular onder controle. Ga naar campagnewebsite"/>
    </a>
  </div>

  <div class="footer">
    <div class="footer-inner">
      <div class="footer-links">
        <div class="footer-links-col ___desktop-50">
          <div class="footer-logos-info">
            <h2 class="screen-reader-text">Colofon</h2>
            Het FuckAngular programma is ontwikkeld door het Ministerie van Development, het Ministerie van Cyber, in
            samenwerking met het
            <a href="https://www.rivm.nl/" target="_blank" rel="noopener noreferrer">
              <abbr title="Rijksinstituut voor Volksgezondheid en Milieu">RIVM</abbr>
            </a>
            en de landelijke
            <a href="https://www.ggd.nl/" target="_blank" rel="noopener noreferrer">
              <abbr title="Gemeentelijke gezondheidsdienst">GGD'en</abbr>
            </a>
            . Dit programma had niet tot stand kunnen komen zonder de hulp van tientallen experts, ervaringsdeskundigen
            en een grote open source community van burgers die heeft meegekeken en getest tijdens de ontwikkeling. Er is
            alles aan
            gedaan om te zorgen voor een privacyvriendelijke, veilig, toegankelijk en gebruiksvriendelijk programma die
            helpt Angular onder controle te krijgen en houden.
          </div>
        </div>
        <div class="footer-links-col ___desktop-25">
          <h3>Over FuckAngular</h3>
          <ul>
            <li>
              <a href="#"> Privacy </a>
            </li>
            <li>
              <a href="#"> Cookies </a>
            </li>
            <li>
              <a href="#"> Colofon </a>
            </li>
            <li>
              <a href="#"> Toegankelijkheidsverklaring </a>
            </li>
            <li>
              <a href="#"> Kwetsbaarheid melden </a>
            </li>
            <li>
              <a href="#"> Pers </a>
            </li>
            <li>
              <a href="#"> Partnertoolkit </a>
            </li>
          </ul>
        </div>
        <div class="footer-links-col ___desktop-25">
          <h3>Meer informatie?</h3>
          <ul>
            <li>
              <a href="https://rijksoverheid.nl" target="_blank" rel="noopener noreferrer">Kijk op rijksoverheid.nl </a>
            </li>
            <li>
              <a href="https://github.com/kwaliteit-software/fuckangular" target="_blank" rel="noopener noreferrer">De
                FuckAngular repository </a>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</footer>
