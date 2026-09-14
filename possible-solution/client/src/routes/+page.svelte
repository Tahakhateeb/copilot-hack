<script lang="ts">
    let menuOpen = false;
    let bookingOpen = false;
    let bookingSent = false;
    let activeService = 'Performance diagnostics';
    let selectedDate = '';

    const services = [
        { number: '01', title: 'Performance diagnostics', copy: 'Decode every signal. Tune every response.', tag: 'Precision' },
        { number: '02', title: 'Custom detailing', copy: 'A finish as considered as your build.', tag: 'Finish' },
        { number: '03', title: 'Maintenance plans', copy: 'Keep your everyday machine exceptional.', tag: 'Confidence' }
    ];

    function openBooking(service = 'Performance diagnostics') {
        activeService = service;
        bookingSent = false;
        bookingOpen = true;
        menuOpen = false;
    }

    function submitBooking() {
        bookingSent = true;
    }

    function closeBooking() {
        bookingOpen = false;
        bookingSent = false;
    }
</script>

<svelte:head>
    <title>TK Auto Hub — Built for the drive ahead</title>
    <meta name="description" content="TAHA KHATEEB AUTO HUB — a precision automotive studio for performance, protection and peace of mind." />
    <meta name="theme-color" content="#08090b" />
</svelte:head>

<div class="site-shell">
    <div class="grain"></div>
    <header class="site-header">
        <a class="brand" href="#top" aria-label="TK Auto Hub home">
            <span class="brand-mark"><span>TK</span></span>
            <span class="brand-text"><strong>TAHA KHATEEB</strong><small>AUTO HUB</small></span>
        </a>

        <nav class:open={menuOpen} aria-label="Main navigation">
            <a href="#services" on:click={() => (menuOpen = false)}>Services</a>
            <a href="#method" on:click={() => (menuOpen = false)}>Our method</a>
            <a href="#studio" on:click={() => (menuOpen = false)}>The studio</a>
            <a href="#contact" on:click={() => (menuOpen = false)}>Contact</a>
            <button class="nav-cta" on:click={() => openBooking()}>Book a visit <span>↗</span></button>
        </nav>

        <button class="menu-toggle" aria-label={menuOpen ? 'Close menu' : 'Open menu'} aria-expanded={menuOpen} on:click={() => (menuOpen = !menuOpen)}>
            <span></span><span></span>
        </button>
    </header>

    <main id="top">
        <section class="hero">
            <div class="hero-copy">
                <p class="eyebrow"><span></span> Automotive care, re-engineered</p>
                <h1>Make every<br /><em>drive</em> count.</h1>
                <p class="hero-intro">The details matter. From first ignition to final polish, we bring precision, craft and a little more soul to the way you move.</p>
                <div class="hero-actions">
                    <button class="button button-primary" on:click={() => openBooking()}>Start your build <span>↗</span></button>
                    <a class="text-link" href="#services">Explore services <span>↓</span></a>
                </div>
            </div>

            <div class="hero-art" aria-label="Abstract illustration of a sports car" role="img">
                <div class="art-glow"></div>
                <div class="speed-line line-one"></div><div class="speed-line line-two"></div><div class="speed-line line-three"></div>
                <svg viewBox="0 0 700 420" class="car-art" aria-hidden="true">
                    <defs>
                        <linearGradient id="carBody" x1="0" x2="1" y1="0" y2="1">
                            <stop offset="0" stop-color="#f6f7f8" /><stop offset=".32" stop-color="#aab0b6" /><stop offset=".57" stop-color="#34383e" /><stop offset="1" stop-color="#0c0e12" />
                        </linearGradient>
                        <linearGradient id="window" x1="0" x2="1"><stop stop-color="#172331" /><stop offset="1" stop-color="#020407" /></linearGradient>
                        <filter id="shadow"><feGaussianBlur stdDeviation="12" /></filter>
                    </defs>
                    <ellipse cx="362" cy="356" rx="240" ry="24" fill="#020305" opacity=".75" filter="url(#shadow)" />
                    <path d="M91 317 C137 304 167 257 222 220 C265 191 348 180 409 194 C455 204 480 238 524 256 L612 282 C637 290 653 307 649 326 L625 341 L106 341 C83 337 74 328 91 317Z" fill="url(#carBody)" stroke="#e8edf1" stroke-width="2" />
                    <path d="M232 219 C269 191 326 185 389 198 L464 246 L200 249Z" fill="url(#window)" stroke="#aeb8c2" stroke-width="2" />
                    <path d="M391 200 L464 246 L400 245Z" fill="#0a1119" stroke="#7c8995" stroke-width="1" />
                    <path d="M111 317 C187 299 278 297 356 300 C458 304 548 294 628 316" fill="none" stroke="#fb1d39" stroke-width="5" opacity=".9" />
                    <path d="M140 288 L198 276 M492 274 L584 290" stroke="#ffffff" opacity=".28" stroke-width="3" />
                    <circle cx="187" cy="336" r="40" fill="#090b0e" stroke="#aab0b6" stroke-width="5" /><circle cx="187" cy="336" r="20" fill="#30353a" stroke="#f01e39" stroke-width="4" /><circle cx="187" cy="336" r="6" fill="#dce1e5" />
                    <circle cx="554" cy="336" r="40" fill="#090b0e" stroke="#aab0b6" stroke-width="5" /><circle cx="554" cy="336" r="20" fill="#30353a" stroke="#f01e39" stroke-width="4" /><circle cx="554" cy="336" r="6" fill="#dce1e5" />
                    <path d="M90 311 L56 314 L40 329 L78 331" fill="#ef1c37" /><path d="M614 288 L647 292 L674 309 L650 316" fill="#f7f8f8" opacity=".8" />
                </svg>
                <div class="art-caption"><span>01 / 04</span><span>Drive with intent</span></div>
            </div>
            <div class="hero-bottom"><span>Est. 2024 / Dubai</span><span>Scroll to discover <i>↓</i></span></div>
        </section>

        <section class="marquee" aria-label="Our values">
            <div>PRECISION <b>✦</b> PERFORMANCE <b>✦</b> PRESENCE <b>✦</b> PRECISION <b>✦</b> PERFORMANCE <b>✦</b></div>
        </section>

        <section class="services section" id="services">
            <div class="section-heading">
                <div><p class="eyebrow"><span></span> What we do</p><h2>Built around<br /><em>your</em> drive.</h2></div>
                <p class="section-note">No two cars are the same. No two owners should feel like they are on the same plan. We listen first, then make it personal.</p>
            </div>
            <div class="service-grid">
                {#each services as service, i}
                    <article class="service-card" class:featured={i === 0}>
                        <div class="service-top"><span class="service-number">{service.number}</span><span class="service-arrow">↗</span></div>
                        <div class="service-icon">{i === 0 ? '⌁' : i === 1 ? '◌' : '◒'}</div>
                        <h3>{service.title}</h3><p>{service.copy}</p>
                        <button on:click={() => openBooking(service.title)}>Discover <span>↗</span></button>
                    </article>
                {/each}
            </div>
        </section>

        <section class="manifesto section" id="method">
            <div class="manifesto-visual"><span class="circle circle-one"></span><span class="circle circle-two"></span><span class="visual-label">TK / 001</span><div class="visual-center">TK</div></div>
            <div class="manifesto-copy"><p class="eyebrow"><span></span> The TK standard</p><h2>Good enough<br />is <em>not</em> our lane.</h2><p>We are a new kind of automotive studio: part workshop, part atelier, entirely invested in getting the details right. Expect honest advice, engineered solutions and a finish that turns heads for the right reasons.</p><a class="text-link" href="#contact">Meet the people behind it <span>↗</span></a></div>
        </section>

        <section class="studio section" id="studio">
            <div class="studio-copy"><p class="eyebrow"><span></span> The studio</p><h2>Where the<br /><em>magic</em> happens.</h2><p>Come for the service. Stay for the conversation. Our 3,500 sq ft studio is a calm, considered space for cars that deserve more than a quick fix.</p><div class="studio-meta"><div><strong>3,500</strong><small>sq ft / studio</small></div><div><strong>06</strong><small>specialist bays</small></div><div><strong>24h</strong><small>response time</small></div></div></div>
            <div class="studio-visual"><div class="bay bay-one">TK<span>01</span></div><div class="bay bay-two">AUTO<span>02</span></div><div class="blue-light"></div></div>
        </section>

        <section class="contact section" id="contact">
            <div><p class="eyebrow"><span></span> Ready when you are</p><h2>Let's make your<br /><em>next move.</em></h2></div>
            <div class="contact-action"><p>Tell us what you drive, what you need, or just what you have in mind. We’ll take it from there.</p><button class="button button-primary" on:click={() => openBooking()}>Book a consultation <span>↗</span></button><a href="mailto:hello@tkautohub.com">hello@tkautohub.com</a></div>
        </section>
    </main>

    <footer><a class="brand" href="#top"><span class="brand-mark"><span>TK</span></span><span class="brand-text"><strong>TAHA KHATEEB</strong><small>AUTO HUB</small></span></a><span>© 2024 TK Auto Hub. Built for the drive ahead.</span><div><a href="#services">Services</a><a href="#contact">Instagram</a><a href="#contact">Contact</a></div></footer>
</div>

{#if bookingOpen}
    <div class="modal-backdrop" role="presentation" on:click={(event) => event.target === event.currentTarget && closeBooking()}>
        <section class="booking-modal" role="dialog" aria-modal="true" aria-labelledby="booking-title">
            <button class="modal-close" aria-label="Close booking form" on:click={closeBooking}>×</button>
            {#if bookingSent}
                <div class="success-state"><div class="success-mark">✓</div><p class="eyebrow"><span></span> Request received</p><h2>You're on<br /><em>the list.</em></h2><p>We’ll be in touch within 24 hours to confirm your consultation.</p><button class="button button-primary" on:click={closeBooking}>Done <span>↗</span></button></div>
            {:else}
                <p class="eyebrow"><span></span> Start a conversation</p><h2 id="booking-title">Book your<br /><em>next move.</em></h2>
                <form on:submit|preventDefault={submitBooking}>
                    <label>Name<input required name="name" placeholder="Your name" /></label>
                    <label>Email<input required type="email" name="email" placeholder="you@email.com" /></label>
                    <label>What can we help with?<select bind:value={activeService}><option>Performance diagnostics</option><option>Custom detailing</option><option>Maintenance plans</option><option>Something else</option></select></label>
                    <label>Preferred date<input required type="date" bind:value={selectedDate} /></label>
                    <button class="button button-primary form-submit" type="submit">Send request <span>↗</span></button>
                </form>
            {/if}
        </section>
    </div>
{/if}

<style>
    :global(*) { box-sizing: border-box; } :global(html) { scroll-behavior: smooth; } :global(body) { margin: 0; background: #08090b; color: #f2f3f4; font-family: 'Manrope', sans-serif; } :global(button), :global(input), :global(select) { font: inherit; }
    .site-shell { min-height: 100vh; overflow: hidden; position: relative; background: radial-gradient(circle at 75% 10%, rgba(39, 51, 67, .22), transparent 28%), #08090b; } .grain { pointer-events: none; position: fixed; inset: 0; opacity: .045; z-index: 10; background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 180 180' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='.8'/%3E%3C/svg%3E"); }
    .site-header { height: 86px; display: flex; align-items: center; justify-content: space-between; padding: 0 6vw; position: absolute; top: 0; width: 100%; z-index: 5; border-bottom: 1px solid rgba(255,255,255,.08); } .brand { display: inline-flex; align-items: center; gap: 12px; color: #f2f3f4; text-decoration: none; } .brand-mark { width: 38px; height: 38px; border: 1px solid #ef1e3b; display: grid; place-items: center; transform: skew(-12deg); color: #ef1e3b; font: 500 14px 'DM Mono', monospace; } .brand-mark span { transform: skew(12deg); } .brand-text { display: flex; flex-direction: column; line-height: 1.15; letter-spacing: .11em; font-size: 10px; } .brand-text small { color: #89919b; font: 10px 'DM Mono', monospace; letter-spacing: .2em; margin-top: 4px; }
    nav { display: flex; align-items: center; gap: clamp(18px, 3vw, 45px); } nav a, .nav-cta { color: #a8afb7; text-decoration: none; font: 11px 'DM Mono', monospace; letter-spacing: .08em; transition: color .2s; } nav a:hover { color: white; } .nav-cta { border: 1px solid rgba(255,255,255,.25); background: transparent; color: #fff; padding: 13px 17px; cursor: pointer; } .nav-cta span, .button span { color: #fb2442; padding-left: 8px; } .menu-toggle { display: none; }
    .hero { min-height: 745px; height: 100vh; max-height: 900px; padding: 160px 6vw 40px; display: grid; grid-template-columns: .9fr 1.1fr; align-items: center; position: relative; } .hero:before { content: ''; position: absolute; width: 55vw; height: 55vw; max-width: 760px; max-height: 760px; right: -10vw; top: 5%; border: 1px solid rgba(111, 131, 154, .15); border-radius: 50%; box-shadow: 0 0 0 70px rgba(111,131,154,.025), 0 0 0 140px rgba(111,131,154,.018); } .hero-copy { position: relative; z-index: 2; max-width: 570px; } .eyebrow { color: #8f98a2; display: flex; align-items: center; gap: 11px; font: 10px 'DM Mono', monospace; letter-spacing: .14em; text-transform: uppercase; } .eyebrow span { height: 1px; width: 27px; background: #ef1e3b; display: inline-block; } h1, h2 { letter-spacing: -.065em; line-height: .92; font-weight: 600; margin: 22px 0; } h1 { font-size: clamp(60px, 8.3vw, 126px); } h2 { font-size: clamp(47px, 6vw, 88px); } h1 em, h2 em { color: #ef1e3b; font-style: normal; } .hero-intro { max-width: 350px; color: #969ea8; line-height: 1.7; font-size: 14px; } .hero-actions { display: flex; gap: 30px; align-items: center; margin-top: 36px; } .button { cursor: pointer; border: 0; padding: 17px 23px; font: 11px 'DM Mono', monospace; letter-spacing: .06em; text-transform: uppercase; } .button-primary { background: #f0f1f2; color: #111214; } .button-primary:hover { background: #ef1e3b; color: white; } .text-link { color: #d1d5d9; font: 11px 'DM Mono', monospace; text-decoration: none; border-bottom: 1px solid #60666d; padding-bottom: 9px; } .text-link span { color: #ef1e3b; padding-left: 10px; font-size: 16px; }
    .hero-art { height: 510px; position: relative; z-index: 1; display: flex; align-items: center; justify-content: center; } .car-art { width: 100%; max-width: 700px; overflow: visible; transform: translateX(3%); } .art-glow { position: absolute; width: 280px; height: 160px; background: #263d53; filter: blur(80px); opacity: .35; right: 23%; top: 35%; } .speed-line { position: absolute; height: 1px; background: linear-gradient(90deg, transparent, #536779, transparent); transform: rotate(-12deg); opacity: .5; } .line-one { width: 220px; right: 7%; top: 36%; } .line-two { width: 310px; right: 1%; top: 47%; } .line-three { width: 170px; right: 14%; top: 59%; } .art-caption { position: absolute; bottom: 45px; right: 5%; display: flex; gap: 40px; color: #737d88; font: 10px 'DM Mono', monospace; text-transform: uppercase; letter-spacing: .12em; } .art-caption span:first-child { color: #ef1e3b; } .hero-bottom { position: absolute; bottom: 37px; left: 6vw; right: 6vw; display: flex; justify-content: space-between; color: #67717c; text-transform: uppercase; letter-spacing: .12em; font: 10px 'DM Mono', monospace; } .hero-bottom i { color: #ef1e3b; font-size: 15px; font-style: normal; padding-left: 8px; }
    .marquee { background: #ef1e3b; color: #0d0e10; white-space: nowrap; overflow: hidden; padding: 18px 0; font: 12px 'DM Mono', monospace; letter-spacing: .2em; } .marquee div { animation: slide 25s linear infinite; width: max-content; } .marquee b { margin: 0 25px; font-weight: 400; } @keyframes slide { to { transform: translateX(-30%); } }
    .section { padding: 140px 9vw; } .section-heading { display: flex; justify-content: space-between; align-items: end; margin-bottom: 70px; } .section-heading h2 { margin-bottom: 0; } .section-note { max-width: 290px; color: #8e969e; font-size: 13px; line-height: 1.75; margin: 0 5vw 7px 20px; }
    .service-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1px; background: rgba(255,255,255,.12); } .service-card { min-height: 370px; background: #0b0d10; padding: 30px; display: flex; flex-direction: column; border-top: 2px solid transparent; transition: background .25s, transform .25s; } .service-card:hover, .service-card.featured { background: linear-gradient(145deg, #131920, #0b0d10); border-top-color: #ef1e3b; transform: translateY(-5px); } .service-top { display: flex; justify-content: space-between; color: #5f6872; font: 11px 'DM Mono', monospace; } .service-arrow { color: #ef1e3b; font-size: 20px; } .service-icon { color: #d9dee2; font-size: 54px; font-weight: 200; margin: 43px 0 25px; } .service-card h3 { font-size: 21px; letter-spacing: -.04em; margin: 0 0 12px; } .service-card p { color: #838c96; font-size: 13px; line-height: 1.6; max-width: 220px; margin: 0; } .service-card button { background: transparent; border: 0; color: #c4cbd1; cursor: pointer; font: 11px 'DM Mono', monospace; text-align: left; margin-top: auto; padding: 35px 0 0; } .service-card button span { color: #ef1e3b; font-size: 18px; padding-left: 8px; }
    .manifesto { display: grid; grid-template-columns: 1fr 1fr; gap: 12vw; align-items: center; background: #0c0e11; } .manifesto-visual { aspect-ratio: 1; max-width: 470px; border-radius: 50%; border: 1px solid #2b3742; position: relative; display: grid; place-items: center; overflow: hidden; background: radial-gradient(circle, #192632 0, #0c1116 38%, transparent 39%); } .manifesto-visual:before { content: ''; position: absolute; width: 65%; height: 65%; border: 1px solid #ef1e3b; border-radius: 50%; opacity: .7; } .circle { position: absolute; border: 1px solid rgba(120,144,165,.2); border-radius: 50%; } .circle-one { width: 120%; height: 120%; } .circle-two { width: 30%; height: 30%; } .visual-label { position: absolute; top: 17%; left: 15%; color: #82909d; font: 10px 'DM Mono', monospace; } .visual-center { color: #f2f3f4; font: 700 80px 'Manrope'; letter-spacing: -.15em; margin-right: 15px; z-index: 1; } .manifesto-copy { max-width: 500px; } .manifesto-copy h2 { margin-bottom: 32px; } .manifesto-copy > p:not(.eyebrow) { color: #8e969e; line-height: 1.8; font-size: 14px; max-width: 400px; margin-bottom: 36px; }
    .studio { display: grid; grid-template-columns: .8fr 1.2fr; gap: 10vw; align-items: center; } .studio-copy { max-width: 370px; } .studio-copy h2 { margin-bottom: 30px; } .studio-copy > p:not(.eyebrow) { color: #8e969e; line-height: 1.8; font-size: 14px; } .studio-meta { display: flex; gap: 25px; margin-top: 48px; } .studio-meta div { border-left: 1px solid #ef1e3b; padding-left: 12px; } .studio-meta strong { display: block; font-size: 23px; font-weight: 500; } .studio-meta small { color: #6e7882; display: block; margin-top: 7px; font: 9px 'DM Mono', monospace; text-transform: uppercase; } .studio-visual { height: 420px; background: linear-gradient(125deg, #1a1e20, #07090b 60%); position: relative; overflow: hidden; border: 1px solid #242b31; } .studio-visual:before, .studio-visual:after { content: ''; position: absolute; top: 0; bottom: 0; width: 1px; background: #343a3e; transform: skew(-22deg); left: 36%; } .studio-visual:after { left: 72%; } .bay { position: absolute; font: 700 clamp(50px, 8vw, 130px) 'Manrope'; color: rgba(255,255,255,.05); letter-spacing: -.1em; } .bay span { font: 11px 'DM Mono'; color: #ef1e3b; vertical-align: top; letter-spacing: 0; } .bay-one { left: 3%; top: 5%; } .bay-two { right: -3%; bottom: 5%; color: rgba(255,255,255,.1); } .blue-light { position: absolute; width: 60%; height: 20px; background: #147db3; filter: blur(20px); opacity: .5; transform: rotate(-35deg); right: 5%; top: 50%; }
    .contact { border-top: 1px solid #23272c; border-bottom: 1px solid #23272c; display: flex; justify-content: space-between; align-items: end; gap: 30px; } .contact h2 { margin-bottom: 0; } .contact-action { max-width: 300px; } .contact-action p { color: #8e969e; line-height: 1.7; font-size: 13px; margin: 0 0 25px; } .contact-action .button { display: block; margin-bottom: 25px; } .contact-action > a { color: #bac0c6; font: 11px 'DM Mono', monospace; text-decoration: none; border-bottom: 1px solid #ef1e3b; padding-bottom: 5px; }
    footer { padding: 40px 6vw; display: flex; justify-content: space-between; align-items: center; color: #626b75; font: 10px 'DM Mono', monospace; gap: 25px; } footer .brand { color: white; transform: scale(.8); transform-origin: left center; } footer > div { display: flex; gap: 22px; } footer > div a { color: #929aa2; text-decoration: none; }
    .modal-backdrop { position: fixed; inset: 0; z-index: 20; display: grid; place-items: center; background: rgba(0,0,0,.75); backdrop-filter: blur(8px); padding: 20px; } .booking-modal { width: min(100%, 550px); max-height: 90vh; overflow-y: auto; background: #111519; border: 1px solid #35404a; padding: 50px; position: relative; box-shadow: 0 25px 100px rgba(0,0,0,.7); } .modal-close { position: absolute; right: 20px; top: 15px; color: #98a1a8; background: transparent; border: 0; cursor: pointer; font-size: 28px; } .booking-modal h2 { font-size: 57px; margin: 25px 0 35px; } form { display: grid; gap: 17px; } label { color: #7e8993; display: grid; gap: 7px; font: 10px 'DM Mono', monospace; text-transform: uppercase; letter-spacing: .08em; } input, select { width: 100%; padding: 13px 0; border: 0; border-bottom: 1px solid #3a444d; background: transparent; color: #f2f3f4; outline: none; border-radius: 0; } input:focus, select:focus { border-color: #ef1e3b; } select option { background: #111519; } input::placeholder { color: #55606a; } .form-submit { margin-top: 12px; width: 100%; } .success-state { text-align: left; } .success-mark { color: #0b0d10; background: #ef1e3b; width: 48px; height: 48px; display: grid; place-items: center; font-size: 24px; margin-bottom: 28px; } .success-state h2 { margin: 22px 0; } .success-state > p:not(.eyebrow) { color: #929ba4; font-size: 14px; margin-bottom: 30px; }
    @media (max-width: 800px) { .site-header { padding: 0 6vw; } nav { display: none; position: absolute; top: 85px; left: 0; right: 0; padding: 22px 6vw 28px; background: #101316; border-bottom: 1px solid #323940; flex-direction: column; align-items: flex-start; gap: 24px; } nav.open { display: flex; } .nav-cta { width: 100%; text-align: left; } .menu-toggle { display: flex; flex-direction: column; gap: 6px; border: 0; background: transparent; padding: 10px 0 10px 10px; } .menu-toggle span { width: 25px; height: 1px; background: #f4f4f4; } .hero { display: block; height: auto; min-height: 780px; padding-top: 150px; } .hero-copy { max-width: 500px; } .hero-art { height: 350px; margin-top: 25px; } .hero:before { width: 90vw; height: 90vw; right: -24vw; top: 28%; } .art-caption { bottom: 15px; } .hero-bottom { bottom: 20px; } .section { padding: 95px 7vw; } .section-heading { display: block; margin-bottom: 45px; } .section-note { margin: 25px 0 0; } .service-grid, .manifesto, .studio { grid-template-columns: 1fr; } .service-card { min-height: 320px; } .manifesto-visual { max-width: 340px; margin: 0 auto; order: 2; } .manifesto-copy { order: 1; } .studio-visual { order: 2; height: 320px; } .studio-copy { order: 1; } .contact { display: block; } .contact-action { margin-top: 45px; } footer { flex-wrap: wrap; padding: 30px 7vw; } footer > div { order: 3; width: 100%; } .booking-modal { padding: 40px 25px; } }
    @media (max-width: 450px) { h1 { font-size: 59px; } .hero-intro { font-size: 13px; } .hero-actions { gap: 20px; flex-wrap: wrap; } .hero-art { height: 270px; } .hero-bottom span:last-child { display: none; } .studio-meta { gap: 15px; } .studio-meta strong { font-size: 19px; } .booking-modal h2 { font-size: 47px; } }
</style>
