
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <title>Unikyoyu — Share • Sell • Support</title>
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link
      href="https://fonts.googleapis.com/css2?family=Poppins:wght@500;700&family=Inter:wght@400;500;600&display=swap"
      rel="stylesheet"
    />
    <style>
      :root {
        /* NEW earthy palette */
        --ink: #1b1b1b;
        --dark: #2d2424; /* background / nav */
        --coffee: #5c3d2e; /* cards / accents */
        --rust: #b85c38; /* CTA */
        --sand: #e0c097; /* soft bg */
        --paper: #ffffff;
        --muted: #8b8b8b;
        --radius: 20px;
        --shadow: 0 18px 45px rgba(0, 0, 0, 0.18);
      }

      * {
        box-sizing: border-box;
      }
      html {
        scroll-behavior: smooth;
      }
      html,
      body {
        margin: 0;
        padding: 0;
        background: linear-gradient(180deg, var(--sand), #fff);
        color: var(--ink);
        font-family: Inter, system-ui, Segoe UI, Roboto, Helvetica, Arial,
          sans-serif;
      }
      a {
        color: inherit;
        text-decoration: none;
      }
      img {
        max-width: 100%;
        display: block;
      }

      /* Animations */
      @keyframes fadeUp {
        from {
          opacity: 0;
          transform: translateY(12px);
        }
        to {
          opacity: 1;
          transform: none;
        }
      }
      @keyframes pop {
        0% {
          transform: scale(0.96);
          opacity: 0.5;
        }
        100% {
          transform: scale(1);
          opacity: 1;
        }
      }

      /* Nav */
      .nav {
        position: sticky;
        top: 0;
        z-index: 50;
        background: rgba(45, 36, 36, 0.92);
        backdrop-filter: blur(6px);
        border-bottom: 1px solid rgba(255, 255, 255, 0.07);
      }
      .nav-inner {
        max-width: 1200px;
        margin: 0 auto;
        display: flex;
        align-items: center;
        gap: 18px;
        padding: 12px 18px;
      }
      .brand {
        display: flex;
        align-items: center;
        gap: 12px;
      }
      .brand svg {
        width: 44px;
        height: 44px;
      }
      .brand-title {
        font-family: Poppins, Inter, sans-serif;
        font-weight: 700;
        font-size: 1.35rem;
        letter-spacing: 0.3px;
        color: #fff;
      }

      .nav-links {
        margin-left: auto;
        display: flex;
        gap: 10px;
        flex-wrap: wrap;
      }
      .chip {
        padding: 10px 14px;
        border-radius: 999px;
        background: rgba(224, 192, 151, 0.15);
        color: #f6f6f6;
        border: 1px solid rgba(224, 192, 151, 0.25);
        transition: 0.25s ease;
        opacity: 0.95;
      }
      .chip:hover {
        transform: translateY(-2px);
        box-shadow: var(--shadow);
        opacity: 1;
      }
      .chip[data-cta] {
        background: var(--rust);
        border-color: transparent;
      }

      /* Hero */
      .hero {
        position: relative;
        min-height: 78vh;
        display: grid;
        place-items: center;
        overflow: hidden;
      }
      .hero::before {
        content: "";
        position: absolute;
        inset: 0;
        background: url("https://s3.amazonaws.com/shecodesio-production/uploads/files/000/172/356/original/Download_free_image_of_Pink_rainbow_background_pattern_texture_jacuzzi__by_Adjima_about_mobile_wallpaper__iphone_wallpaper__backgrounds__star__and_pink_wallpaper_14894381.jpg?1755428583")
          center/cover no-repeat;
        filter: brightness(0.55);
      }
      .hero-inner {
        position: relative;
        z-index: 1;
        max-width: 1200px;
        padding: 24px;
        display: grid;
        grid-template-columns: 1.1fr 0.9fr;
        gap: 28px;
        align-items: center;
      }
      @media (max-width: 900px) {
        .hero-inner {
          grid-template-columns: 1fr;
        }
      }
      .hero-card {
        background: rgba(255, 255, 255, 0.1);
        border: 1px solid rgba(255, 255, 255, 0.25);
        border-radius: var(--radius);
        padding: 28px;
        color: #fff;
        backdrop-filter: blur(8px);
        animation: fadeUp 0.6s ease both;
      }
      h1 {
        font-family: Poppins, Inter, sans-serif;
        font-size: clamp(2rem, 4vw, 3rem);
        line-height: 1.05;
        margin: 0 0 10px;
      }
      .hero p {
        opacity: 0.9;
        margin: 0 0 16px;
      }
      .cta-row {
        display: flex;
        gap: 12px;
        flex-wrap: wrap;
      }
      .btn {
        appearance: none;
        border: 0;
        padding: 12px 18px;
        border-radius: 14px;
        font-weight: 700;
        cursor: pointer;
        box-shadow: var(--shadow);
        transition: transform 0.15s ease, opacity 0.2s ease;
      }
      .btn:active {
        transform: translateY(1px);
      }
      .btn-primary {
        background: var(--rust);
        color: #fff;
      }
      .btn-ghost {
        background: rgba(255, 255, 255, 0.15);
        color: #fff;
        border: 1px solid rgba(255, 255, 255, 0.25);
      }

      /* Section shells */
      .section {
        max-width: 1200px;
        margin: 40px auto;
        padding: 0 18px;
      }
      .section h2 {
        font-family: Poppins, Inter, sans-serif;
        font-size: 1.6rem;
        margin: 0 0 14px;
      }
      .disclaimer {
        color:red;
        font-weight: 600;
      }

      /* Image-focused grids */
      .grid {
        display: grid;
        grid-template-columns: repeat(4, 1fr);
        gap: 16px;
      }
      @media (max-width: 1000px) {
        .grid {
          grid-template-columns: repeat(2, 1fr);
        }
      }
      @media (max-width: 560px) {
        .grid {
          grid-template-columns: 1fr;
        }
      }
      .tile {
        position: relative;
        border-radius: 18px;
        overflow: hidden;
        box-shadow: var(--shadow);
        cursor: pointer;
        transform: translateZ(0);
      }
      .tile img {
        aspect-ratio: 4/3;
        object-fit: cover;
        transition: transform 0.5s ease, filter 0.5s ease;
      }
      .tile:hover img {
        transform: scale(1.05);
        filter: saturate(1.05);
      }
      .tile .label {
        position: absolute;
        left: 12px;
        bottom: 12px;
        background: rgba(45, 36, 36, 0.7);
        color: #fff;
        padding: 8px 12px;
        border-radius: 999px;
        font-weight: 700;
        letter-spacing: 0.2px;
      }

      /* Cards (minimal text) */
      .card {
        background: #fff;
        border-radius: 18px;
        box-shadow: var(--shadow);
        overflow: hidden;
      }
      .card .body {
        padding: 14px;
      }
      .price {
        font-weight: 800;
        color: var(--coffee);
      }

      /* Info strip */
      .info {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        gap: 16px;
      }
      @media (max-width: 900px) {
        .info {
          grid-template-columns: 1fr;
        }
      }
      .tileInfo {
        background: linear-gradient(
          135deg,
          rgba(92, 61, 46, 0.1),
          rgba(184, 92, 56, 0.1)
        );
        border: 1px solid rgba(92, 61, 46, 0.15);
        border-radius: 18px;
        padding: 20px;
        animation: fadeUp 0.6s ease both;
      }

      /* Footer */
      footer {
        margin-top: 40px;
        background: var(--dark);
        color: #eee;
      }
      .foot {
        max-width: 1200px;
        margin: 0 auto;
        padding: 24px 18px;
        display: grid;
        grid-template-columns: 2fr 1fr 1fr;
        gap: 16px;
      }
      @media (max-width: 900px) {
        .foot {
          grid-template-columns: 1fr;
        }
      }
      .credit {
        font-size: 0.9rem;
        color: #bdbdbd;
      }

      /* Modals */
      dialog {
        border: 0;
        border-radius: 20px;
        box-shadow: var(--shadow);
        padding: 0;
        width: min(92vw, 560px);
        opacity: 0;
        transform: translateY(10px);
        transition: opacity 0.25s ease, transform 0.25s ease;
      }
      dialog[open] {
        opacity: 1;
        transform: none;
      }
      dialog::backdrop {
        background: rgba(0, 0, 0, 0.5);
        backdrop-filter: blur(2px);
      }
      .modal {
        padding: 22px;
      }
      .modal h3 {
        font-family: Poppins, Inter, sans-serif;
        margin: 0 0 8px;
      }
      .row {
        display: grid;
        grid-template-columns: 1fr 1fr;
        gap: 12px;
      }
      @media (max-width: 560px) {
        .row {
          grid-template-columns: 1fr;
        }
      }
      .field {
        display: flex;
        flex-direction: column;
        gap: 6px;
      }
      .field input,
      .field select {
        padding: 12px 12px;
        border-radius: 12px;
        border: 2px solid #eee;
        outline: none;
        transition: border 0.2s ease, box-shadow 0.2s ease;
      }
      .field input:focus,
      .field select:focus {
        border-color: var(--rust);
        box-shadow: 0 0 0 3px rgba(184, 92, 56, 0.15);
      }
      .modal menu {
        display: flex;
        gap: 10px;
        justify-content: flex-end;
        margin: 0;
      }

      .lock {
        display: inline-flex;
        align-items: center;
        gap: 8px;
        font-size: 0.9rem;
        background: rgba(224, 192, 151, 0.25);
        padding: 8px 12px;
        border-radius: 10px;
        border: 1px solid rgba(92, 61, 46, 0.15);
      }
      /* Card Container */
.card {
  background: #fff;
  border-radius: 16px;
  box-shadow: 0 4px 12px rgba(0,0,0,0.1);
  overflow: hidden;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  padding: 0;
  transition: transform 0.2s ease;
}

.card:hover {
  transform: translateY(-5px);
}

/* Card Images */
.card img {
  width: 100%;
  height: 350px;           /* set same height for all */
  object-fit: cover;       /* crop neatly while keeping aspect ratio */
  border-top-left-radius: 16px;
  border-top-right-radius: 16px;
}


/* Card Content */
.card-body {
  padding: 15px;
  flex: 1;                 /* let text area grow evenly */
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.card-title {
  font-size: 1rem;
  font-weight: bold;
  margin-bottom: 8px;
  color: #333;
}

.card-price {
  font-size: 1.1rem;
  color: #e5989b;          /* matches your palette */
  font-weight: bold;
}

    </style>
  </head>
  <body>
    <!-- Navigation -->
    <nav class="nav">
      <div class="nav-inner">
        <a class="brand" href="#home" aria-label="Unikyoyu home">
          <!-- NEW Minimal SVG Logo: circular emblem with book + leaf (growth/learning) -->
          <svg viewBox="0 0 72 72" aria-hidden="true" role="img">
            <
            <!-- leaf sprout from center -->
            <img
              src="https://s3.amazonaws.com/shecodesio-production/uploads/files/000/172/362/original/download_%284%29.jpg?1755432825"
              alt="Logo"
              width="72"
              height="72"
              style="border-radius: 50%"
            />
          </svg>
          <span class="brand-title">Unikyoyu</span>
        </a>
        <div class="nav-links">
          <a class="chip" href="#home">Home</a>
          <a class="chip" href="#browse">Browse</a>
          <a class="chip" data-requires-verify href="#sell">Sell / Donate</a>
          <a class="chip" href="#safety">Safety</a>
          <a class="chip" href="#about">About</a>
          <a class="chip" href="#contact">Contact</a>
          <a class="chip" data-cta data-requires-verify href="#dashboard"
            >Dashboard</a
          >
        </div>
      </div>
    </nav>

    <!-- Hero: minimal words, big imagery -->
    <header id="home" class="hero">
      <div class="hero-inner">
        <div class="hero-card" style="animation-delay: 0.05s">
          <h1>Share.Connect.Thrive.</h1>
          <p>
            Student‑only marketplace. Lower cost. Lower waste. Higher community.
          </p>
          <div class="cta-row">
            <button
              class="btn btn-primary"
              data-requires-verify
              onclick="navigateHash('#sell')"
            >
              Post Item
            </button>
            <a class="btn btn-ghost" href="#browse">Browse</a>
          </div>
          <p id="hello" class="lock" style="margin-top: 12px">
            🔒 Public tabs are open. Full access after university email
            verification.
          </p>
        </div>
        <div class="hero-card" style="animation-delay: 0.15s">
          <img
            alt="Students exchanging books"
            src="https://s3.amazonaws.com/shecodesio-production/uploads/files/000/172/354/original/hands.jpg?1755427750"
          />
        </div>
      </div>
    </header>

    <!-- Browse grid (image heavy, short labels) -->
    <section id="browse" class="section">
      <h2>Pick a category</h2>
      <div class="grid">
        <a class="tile" href="#listings"
          ><img
            src="https://s3.amazonaws.com/shecodesio-production/uploads/files/000/172/357/original/Green_Homescreen_Wallpaper_with_Floral.jpg?1755429023"
            alt="Books"
          /><span class="label">Books & Notes</span></a
        >
        <a class="tile" href="#listings"
          ><img
            src="https://s3.amazonaws.com/shecodesio-production/uploads/files/000/172/359/original/Illustration_vector_graphic_cartoon_character_of_checklist.jpg?1755430241"
            alt="Question Papers"
          /><span class="label">PYQs</span></a
        >
        <a class="tile" href="#listings"
          ><img
            src="https://s3.amazonaws.com/shecodesio-production/uploads/files/000/172/360/original/Premium_Vector___Hostel_for_young_people_concept.jpg?1755430459"
            alt="Hostel"
          /><span class="label">Hostel</span></a
        >
        <a class="tile" href="#listings"
          ><img
            src="https://s3.amazonaws.com/shecodesio-production/uploads/files/000/172/363/original/Sports_Collage_Abstract_Art_Print.jpg?1755433685"
            alt="Sports"
          /><span class="label">Sports</span></a
        >
      </div>
    </section>

    <!-- Listings teaser (minimal copy) -->
    <section id="listings" class="section">
      <h2>Fresh finds</h2>
      <div class="grid">
        <article class="card">
          <img
            alt="Physics book"
            src="https://s3.amazonaws.com/shecodesio-production/uploads/files/000/172/364/original/cscscs.jpg?1755433882"
          />
          <div class="body">
            <div class="price">₹250</div>
            <div>HC Verma Vol 1</div>
          </div>
        </article>
        <article class="card">
          <img
            alt="Chair"
            src="https://s3.amazonaws.com/shecodesio-production/uploads/files/000/172/365/original/download_%285%29.jpg?1755434164"
          />
          <div class="body">
            <div class="price">₹600</div>
            <div>Study Chair</div>
          </div>
        </article>
        <article class="card">
          <img
            alt="Cricket"
            src="https://s3.amazonaws.com/shecodesio-production/uploads/files/000/172/366/original/Morrant_Super_Ultralite_Junior___Youth_Cricket_Batting_Pads_-_Small_Junior___White.jpg?1755434311"
          />
          <div class="body">
            <div class="price">Free</div>
            <div>Cricket Pads</div>
          </div>
        </article>
        <article class="card">
          <img
            alt="Calculator"
            src="https://s3.amazonaws.com/shecodesio-production/uploads/files/000/172/367/original/sg-11134201-22110-jaet6xdimgkv63.jpg?1755434479"
          />
          <div class="body">
            <div class="price">₹450</div>
            <div>Casio FX-991EX</div>
          </div>
        </article>
      </div>
    </section>

    <!-- Values strip -->
    <section class="section info">
      <div class="tileInfo">
        <strong>Verified students</strong>
        <p class="muted">Campus email keeps it safe.</p>
      </div>
      <div class="tileInfo">
        <strong>Reuse & save</strong>
        <p class="muted">Eco + budget friendly.</p>
      </div>
      <div class="tileInfo">
        <strong>Donate</strong>
        <p class="muted">Pass it forward.</p>
      </div>
    </section>

    <!-- Safety (public) -->
    <section id="safety" class="section">
      <h2>Safety</h2>
      <ul class="muted">
        <li>Meet on campus / public spots.</li>
        <li>Check item before paying.</li>
        <li>Never share OTPs. Report issues.</li>
      </ul>
    </section>

    <!-- About (public) -->
    <section id="about" class="section">
      <h2>About</h2>
      <p class="muted">
        Unikyoyu is a student‑only marketplace. Short, simple, visual. Built for
        everyday campus life.
      </p>
    </section>

    <!-- Contact (public) -->
    <section id="contact" class="section">
      <h2>Contact</h2>
      <p class="muted">hello@unikyoyu@gmail.com</p>
    </section>
    <!--disclaimer-->
    
      <div class="disclaimer">
        <section id="Disclaimer" class="section">
      <h2>Disclaimer</h2>
        <p class="muted">
          <li>‼️Users can only list original, physical study materials.</li>
          <li>
            ‼️The sale or exchange of PDFs, scanned notes, software licenses, or
            course logins is strictly prohibited.Unikyoyu is not responsible for
            any transactions or interactions between users.
          </li>
          <li>
            ‼️The seller is responsible for ensuring they have the legal right
            to sell the items they list.
          </li>
        </p>
      </div>
    </section>

    <footer>
      <div class="foot">
        <div>
          <div class="brand" style="margin-bottom: 8px">
            <svg viewBox="0 0 72 72" aria-hidden="true" role="img">
              <img
                src="https://s3.amazonaws.com/shecodesio-production/uploads/files/000/172/362/original/download_%284%29.jpg?1755432825"
                alt="Logo"
                width="44"
                height="44"
                style="border-radius: 50%"
              />
            </svg>
            <span class="brand-title">Unikyoyu</span>
          </div>
          <p class="credit">
            © <span id="year"></span> Unikyoyu — Share|Connect|Thrive
          </p>
        </div>
        <div>
          <strong>Public</strong>
          <ul class="credit">
            <li><a href="#home">Home</a></li>
            <li><a href="#browse">Browse</a></li>
            <li><a href="#safety">Safety</a></li>
            <li><a href="#about">About</a></li>
            <li><a href="#contact">Contact</a></li>
          </ul>
        </div>
        <div>
          <strong>Account</strong>
          <ul class="credit">
            <li><a href="#sell" data-requires-verify>Sell / Donate</a></li>
            <li><a href="#dashboard" data-requires-verify>Dashboard</a></li>
          </ul>
        </div>
      </div>
    </footer>

    <!-- Onboarding modal (name / university / country / city) -->
    <dialog id="introModal">
      <form class="modal" method="dialog" id="introForm">
        <h3>Welcome 👋</h3>
        <p class="muted">Personalize your campus feed.</p>
        <div class="row" style="margin: 12px 0 8px">
          <div class="field">
            <label for="name">Name</label
            ><input id="name" name="name" required placeholder="e.g., Asha" />
          </div>
          <div class="field">
            <label for="university">University</label
            ><input
              id="university"
              name="university"
              required
              placeholder="e.g., NIT Trichy"
            />
          </div>
          <div class="field">
            <label for="country">Country</label
            ><input
              id="country"
              name="country"
              required
              placeholder="e.g., India"
            />
          </div>
          <div class="field">
            <label for="city">City</label
            ><input id="city" name="city" required placeholder="e.g., Jaipur" />
          </div>
        </div>
        <menu>
          <button class="btn" value="cancel">Not now</button>
          <button class="btn btn-primary" value="ok">Continue</button>
        </menu>
      </form>
    </dialog>

    <!-- Verification modal (university email) with Cancel option -->
    <dialog id="verifyModal">
      <form class="modal" method="dialog" id="verifyForm">
        <h3>University Email</h3>
        <p class="muted">Unlock full access. Student‑only.</p>
        <div class="field" style="margin: 12px 0 8px">
          <label for="email">Email</label>
          <input
            id="email"
            name="email"
            type="email"
            required
            placeholder="name@college.ac.in"
          />
          <small class="muted"
            >Examples: <code>@*.ac.in</code>, <code>@*.edu</code>,
            <code>@*.edu.in</code></small
          >
        </div>
        <menu>
          <button class="btn" value="cancel" id="cancelVerify">Cancel</button>
          <button class="btn btn-primary" value="ok">Verify</button>
        </menu>
      </form>
    </dialog>

    <script>
      const byId = (id) => document.getElementById(id);
      const introModal = byId("introModal");
      const verifyModal = byId("verifyModal");
      const hello = byId("hello");

      const saveUser = (data) =>
        localStorage.setItem("unikyoyu:user", JSON.stringify(data));
      const getUser = () => {
        try {
          return JSON.parse(localStorage.getItem("unikyoyu:user") || "null");
        } catch {
          return null;
        }
      };

      const setVerified = (email) =>
        localStorage.setItem(
          "unikyoyu:verified",
          JSON.stringify({ email, at: Date.now() })
        );
      const isVerified = () => !!localStorage.getItem("unikyoyu:verified");

      function personalize() {
        const u = getUser();
        const y = new Date().getFullYear();
        document.getElementById("year").textContent = y;
        if (u) {
          hello.textContent = `Hi ${u.name} • ${u.university} • ${u.city}`;
        }
      }

      // Show intro on first visit
      window.addEventListener("DOMContentLoaded", () => {
        personalize();
        if (!getUser()) introModal.showModal();
        document.querySelectorAll("[data-requires-verify]").forEach((el) => {
          el.addEventListener("click", (e) => {
            if (!isVerified()) {
              e.preventDefault();
              verifyModal.showModal();
            }
          });
        });
      });

      // Intro form handling
      byId("introForm").addEventListener("close", function () {
        if (this.returnValue === "ok") {
          const name = byId("name").value.trim();
          const university = byId("university").value.trim();
          const country = byId("country").value.trim();
          const city = byId("city").value.trim();
          if (name && university && country && city) {
            saveUser({ name, university, country, city });
            personalize();
          }
        }
      });

      // Verification helpers (no regex backslashes to keep it simple)
      function looksLikeUniversityEmail(email) {
        const e = (email || "").toLowerCase();
        const basic =
          e.includes("@") && e.split("@")[1] && e.split("@")[1].includes(".");
        const uniHints =
          e.includes(".ac.") ||
          e.endsWith(".ac.in") ||
          e.endsWith(".edu") ||
          e.endsWith(".edu.in");
        return basic && uniHints;
      }

      // Allow Cancel gracefully
      byId("cancelVerify").addEventListener("click", () => {
        verifyModal.close();
      });

      byId("verifyForm").addEventListener("close", function () {
        if (this.returnValue === "ok") {
          const email = byId("email").value.trim();
          if (looksLikeUniversityEmail(email)) {
            setVerified(email);
            // micro pop
            const n = document.createElement("div");
            n.textContent = "Verified — welcome to the community!";
            n.style.position = "fixed";
            n.style.bottom = "20px";
            n.style.left = "50%";
            n.style.transform = "translateX(-50%)";
            n.style.background = "var(--rust)";
            n.style.color = "#fff";
            n.style.padding = "12px 16px";
            n.style.borderRadius = "12px";
            n.style.boxShadow = "var(--shadow)";
            n.style.animation = "pop .3s ease both";
            document.body.appendChild(n);
            setTimeout(() => n.remove(), 2200);
          } else {
            alert("Use a valid university email (e.g., name@college.ac.in)");
            verifyModal.showModal();
          }
        }
      });

      // Programmatic navigation honoring guard
      function navigateHash(hash) {
        if (
          [
            "#home",
            "#browse",
            "#safety",
            "#about",
            "#contact",
            "#listings",
          ].includes(hash)
        ) {
          location.hash = hash;
          return;
        }
        if (isVerified()) location.hash = hash;
        else verifyModal.showModal();
      }
      window.navigateHash = navigateHash;
    </script>
  </body>
</html>
