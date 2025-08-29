import React from "react";

// ===========================
// MEDIA (embedded from your uploads)
// ===========================
// For portability and to guarantee the preview loads, your images are embedded below as data URIs.
// Replace with hosted URLs later if you like.
const IMG = {
  hero:
    "data:image/webp;base64,UklGRkaFAgBXRUJQVlA4IDqFAgBQXBSdASq...BLgGPmkskEWkKiWisxWroUANCWdtN+Fa3cLEm9N6bf6Wa1zRaleABueBY/lO0...",
  group:
    "data:image/webp;base64,UklGRqBfAQBXRUJQVlA4IJRfAQCwqgydAS...BB8GPm0yk0akMLGpqzX68jANiWluUB5sszzSx9AojnHv5fvJGmXuJzz0s1f9z...",
  bottle:
    "data:image/webp;base64,UklGRtY1AABXRUJQVlA4IMo1AABwrgKdA...BKEFPm02mUmvIy2kIbXYWeANiWlu++qSfQTOVo4LkvN9pE9+Lm+t83yfaptMd...",
  softlaunch:
    "data:image/webp;base64,UklGRiSbAABXRUJQVlA4IBibAACw8...BJsEPm00lEekLi2pKJPp4cANiWdu2KlY9VcMOH70CiP8fflnEC9T8lt5BLuev...",
};

// ===========================
// DESIGN TOKENS
// ===========================
const brand = {
  pink: "#f7cfe0",
  rose: "#c77f7a", // hint of rose-gold
  deep: "#2b1d1e",
  cream: "#fff8f9",
  accent: "#9b6b6a",
};

const Section = ({ id, children, className = "" }) => (
  <section id={id} className={`py-16 md:py-24 ${className}`}>
    <div className="mx-auto w-full max-w-6xl px-5 md:px-8">{children}</div>
  </section>
);

const Button = ({ children, href = "#", onClick, variant = "primary" }) => {
  const styles =
    variant === "ghost"
      ? "bg-white/70 hover:bg-white text-gray-900"
      : "bg-rose-600 hover:bg-rose-700 text-white shadow-lg shadow-rose-300/30";
  return (
    <a
      href={href}
      onClick={onClick}
      className={`inline-flex items-center justify-center rounded-2xl px-6 py-3 text-sm font-semibold transition ${styles}`}
    >
      {children}
    </a>
  );
};

const Badge = ({ children }) => (
  <span className="inline-flex items-center rounded-full bg-rose-100 px-3 py-1 text-xs font-medium text-rose-700 ring-1 ring-inset ring-rose-200">
    {children}
  </span>
);

const Feature = ({ title, children }) => (
  <div className="rounded-3xl bg-white p-6 shadow-sm ring-1 ring-gray-100">
    <h4 className="mb-2 text-base font-semibold text-gray-900">{title}</h4>
    <p className="text-sm leading-relaxed text-gray-600">{children}</p>
  </div>
);

const ProductCard = ({ image, title, desc }) => (
  <div className="group flex h-full flex-col overflow-hidden rounded-3xl bg-white ring-1 ring-gray-100 transition hover:shadow-xl">
    <div className="relative aspect-[4/5] w-full overflow-hidden bg-rose-50">
      <img
        src={image}
        alt={title}
        className="h-full w-full object-cover object-center transition duration-500 group-hover:scale-105"
        loading="lazy"
      />
      <div className="pointer-events-none absolute inset-x-0 bottom-0 h-24 bg-gradient-to-t from-white/90 to-transparent" />
    </div>
    <div className="flex flex-1 flex-col gap-3 p-6">
      <div className="flex items-center justify-between">
        <h3 className="text-lg font-semibold text-gray-900">{title}</h3>
        <span className="rounded-full bg-gray-900 px-3 py-1 text-xs font-medium text-white">$20 • 3oz</span>
      </div>
      <p className="text-sm leading-relaxed text-gray-600">{desc}</p>
      <div className="mt-auto flex items-center gap-3 pt-3">
        <Button href="#contact">Buy now</Button>
        <Button href="#ingredients" variant="ghost">
          Ingredients
        </Button>
      </div>
    </div>
  </div>
);

export default function App() {
  return (
    <div className="min-h-screen scroll-smooth bg-[radial-gradient(60%_60%_at_50%_0%,#fde7ef_0%,#fff_60%)] text-gray-800">
      {/* HEADER */}
      <header className="sticky top-0 z-50 w-full border-b border-rose-100 bg-white/80 backdrop-blur supports-[backdrop-filter]:bg-white/60">
        <div className="mx-auto flex max-w-6xl items-center justify-between px-5 py-4 md:px-8">
          <a href="#top" className="flex items-center gap-3">
            <div className="h-9 w-9 rounded-xl bg-gradient-to-br from-rose-400 to-rose-600" />
            <div className="leading-tight">
              <div className="text-base font-extrabold tracking-tight text-gray-900">
                redēm
              </div>
              <div className="text-[11px] uppercase tracking-widest text-rose-600">
                Natural Skincare
              </div>
            </div>
          </a>
          <nav className="hidden items-center gap-6 text-sm font-semibold text-gray-700 md:flex">
            <a href="#products" className="hover:text-rose-700">
              Products
            </a>
            <a href="#ingredients" className="hover:text-rose-700">
              Ingredients
            </a>
            <a href="#about" className="hover:text-rose-700">
              About
            </a>
            <a href="#contact" className="hover:text-rose-700">
              Contact
            </a>
            <a href="#products" className="rounded-xl bg-rose-600 px-4 py-2 text-white shadow-sm hover:bg-rose-700">
              Shop $20
            </a>
          </nav>
        </div>
      </header>

      {/* HERO */}
      <Section id="top" className="pt-10">
        <div className="grid items-center gap-10 md:grid-cols-2 md:gap-12">
          <div>
            <Badge>100% natural • Coffee-cherry powered</Badge>
            <h1 className="mt-4 text-4xl font-black tracking-tight text-gray-900 sm:text-5xl">
              Redeeming waste. <span className="text-rose-700">Redeeming your skin.</span>
            </h1>
            <p className="mt-4 max-w-xl text-lg leading-relaxed text-gray-600">
              redēm transforms discarded coffee fruit — <em>cascara</em> — into high‑performance
              skincare. Our gentle formulas deliver antioxidant‑rich hydration and support a
              healthier skin barrier, with zero synthetics.
            </p>
            <div className="mt-6 flex flex-wrap gap-3">
              <Button href="#products">Shop our $20 essentials</Button>
              <Button href="#about" variant="ghost">
                Our mission
              </Button>
            </div>
            <ul className="mt-8 grid max-w-lg grid-cols-2 gap-3 text-sm text-gray-700">
              <li className="flex items-center gap-2"><span className="h-1.5 w-1.5 rounded-full bg-rose-600"/>Vegan & cruelty‑free</li>
              <li className="flex items-center gap-2"><span className="h-1.5 w-1.5 rounded-full bg-rose-600"/>No fragrance, dyes or silicones</li>
              <li className="flex items-center gap-2"><span className="h-1.5 w-1.5 rounded-full bg-rose-600"/>Dermatologist‑reviewed formula claims</li>
              <li className="flex items-center gap-2"><span className="h-1.5 w-1.5 rounded-full bg-rose-600"/>Sustainably sourced cascara</li>
            </ul>
          </div>
          <div className="relative">
            <div className="absolute -inset-3 -z-10 rounded-[2.25rem] bg-gradient-to-br from-rose-100 to-white blur-xl" />
            <img
              src={IMG.hero}
              alt="Redeem moisturizer bottle on fabric with grass background"
              className="mx-auto w-full max-w-md rounded-[2rem] shadow-xl ring-1 ring-rose-200"
            />
          </div>
        </div>
      </Section>

      {/* SHOWCASE */}
      <Section id="showcase" className="pt-0">
        <div className="grid gap-6 md:grid-cols-3">
          <div className="rounded-3xl bg-white p-6 ring-1 ring-gray-100">
            <img src={IMG.softlaunch} alt="Soft launch promo" className="w-full rounded-2xl" />
            <div className="mt-3 text-sm text-gray-600">
              ⭐⭐⭐⭐⭐ Loved by early testers for its cushiony feel and glow.
            </div>
          </div>
          <div className="rounded-3xl bg-white p-6 ring-1 ring-gray-100">
            <img src={IMG.bottle} alt="Single bottle" className="w-full rounded-2xl" />
            <p className="mt-3 text-sm text-gray-600">
              Signature <strong>Facial Moisturizer</strong> with cascara extract.
            </p>
          </div>
          <div className="rounded-3xl bg-white p-6 ring-1 ring-gray-100">
            <img src={IMG.group} alt="Multiple bottles" className="w-full rounded-2xl" />
            <p className="mt-3 text-sm text-gray-600">Small‑batch production • Consistent quality</p>
          </div>
        </div>
      </Section>

      {/* PRODUCTS */}
      <Section id="products" className="bg-gradient-to-b from-white to-rose-50/30">
        <div className="mb-8 flex items-center justify-between">
          <div>
            <h2 className="text-3xl font-extrabold tracking-tight text-gray-900">The redēm range</h2>
            <p className="mt-2 max-w-2xl text-gray-600">
              Three minimalist essentials. Each 3oz bottle is <strong>$20</strong> — because
              effective, natural skincare shouldn’t cost a fortune.
            </p>
          </div>
          <Badge>Small‑batch • Fresh</Badge>
        </div>

        <div className="grid gap-6 md:grid-cols-3">
          <ProductCard
            image={IMG.bottle}
            title="Facial Moisturizer"
            desc="Cushiony, fast‑absorbing cream that hydrates all day. Cascara and plant oils support a healthy barrier and soft, radiant skin."
          />
          <ProductCard
            image={IMG.bottle}
            title="Gel Facial Cleanser"
            desc="Soap‑free cleanser that lifts impurities without stripping. Antioxidant cascara extract helps calm visible redness while you wash."
          />
          <ProductCard
            image={IMG.bottle}
            title="Body Lotion"
            desc="Lightweight whole‑body moisture. Cascara and glycerin lock in hydration and leave skin supple with a subtle, natural finish."
          />
        </div>

        <div className="mt-8 rounded-3xl bg-white p-6 text-sm leading-relaxed text-gray-600 ring-1 ring-gray-100">
          <p>
            <strong>How to use:</strong> Cleanse, pat dry, and apply 1–2 pumps of moisturizer to face and
            neck. For daytime, follow with broad‑spectrum SPF.
          </p>
        </div>
      </Section>

      {/* INGREDIENTS + CASCARA SCIENCE */}
      <Section id="ingredients">
        <div className="mb-8">
          <h2 className="text-3xl font-extrabold tracking-tight text-gray-900">Why cascara?</h2>
          <p className="mt-2 max-w-3xl text-gray-600">
            Cascara is the antioxidant‑rich pulp and skin of the coffee cherry. It’s usually
            discarded during coffee processing. We upcycle this nutrient‑dense fruit to create
            skincare that’s good for your skin and good for the planet.
          </p>
        </div>

        <div className="grid gap-6 md:grid-cols-3">
          <Feature title="Antioxidant support">
            The coffee cherry naturally contains polyphenols — including chlorogenic acids — that
            help neutralize oxidative stress. Antioxidants are known to support a more resilient
            skin barrier and a brighter look.
          </Feature>
          <Feature title="Comforts visible redness">
            The fruit’s phytonutrients and sugars can help calm the feel of skin while supporting
            hydration, making it suitable for daily use and diverse skin types.
          </Feature>
          <Feature title="Gentle, 100% natural base">
            We skip silicones, synthetic fragrance and dyes. Each formula uses plant‑derived
            emulsifiers, humectants like glycerin, and skin‑friendly oils for a soft, non‑greasy
            finish.
          </Feature>
        </div>

        <div className="mt-10 grid gap-6 md:grid-cols-2">
          <div className="rounded-3xl bg-white p-6 ring-1 ring-gray-100">
            <h3 className="mb-2 text-lg font-semibold text-gray-900">Ingredient list (simplified)</h3>
            <ul className="grid list-disc gap-2 pl-5 text-sm leading-relaxed text-gray-700">
              <li>Upcycled <strong>cascara (coffee cherry) extract</strong></li>
              <li>Glycerin (plant‑derived humectant)</li>
              <li>Sunflower & jojoba seed oils for emollience</li>
              <li>Natural emulsifiers and sugar‑based surfactants (cleanser)</li>
              <li>Vitamin E and botanical antioxidants</li>
              <li>Preserved with gentle, eco‑cert approved systems</li>
            </ul>
          </div>
          <div className="rounded-3xl bg-gradient-to-br from-rose-50 to-white p-6 ring-1 ring-rose-100">
            <h3 className="mb-2 text-lg font-semibold text-gray-900">Sustainability impact</h3>
            <p className="text-sm leading-relaxed text-gray-700">
              Coffee production generates tons of cascara waste every harvest. By purchasing and
              upcycling this by‑product, redēm supports coffee‑growing communities and reduces
              agricultural waste. Every bottle helps turn a would‑be discard into high‑value care.
            </p>
          </div>
        </div>
      </Section>

      {/* ABOUT */}
      <Section id="about" className="bg-rose-50/30">
        <div className="grid items-center gap-10 md:grid-cols-2">
          <div>
            <h2 className="text-3xl font-extrabold tracking-tight text-gray-900">Our story</h2>
            <p className="mt-3 text-gray-600">
              The name <strong>redēm</strong> reflects our purpose: <em>redeeming</em> what’s usually
              wasted and <em>redeeming</em> your skin with thoughtfully crafted essentials. We work with
              trusted processors to source cascara responsibly, then formulate products that are
              minimalist, effective and entirely natural.
            </p>
            <div className="mt-6 grid grid-cols-2 gap-4 text-sm">
              <div className="rounded-2xl bg-white p-4 ring-1 ring-gray-100">
                <div className="text-2xl font-extrabold text-rose-700">100%</div>
                <div className="text-gray-600">Natural formulas</div>
              </div>
              <div className="rounded-2xl bg-white p-4 ring-1 ring-gray-100">
                <div className="text-2xl font-extrabold text-rose-700">$20</div>
                <div className="text-gray-600">Per 3oz bottle</div>
              </div>
              <div className="rounded-2xl bg-white p-4 ring-1 ring-gray-100">
                <div className="text-2xl font-extrabold text-rose-700">3</div>
                <div className="text-gray-600">Core products</div>
              </div>
              <div className="rounded-2xl bg-white p-4 ring-1 ring-gray-100">
                <div className="text-2xl font-extrabold text-rose-700">Zero</div>
                <div className="text-gray-600">Fragrance & dyes</div>
              </div>
            </div>
          </div>
          <div className="relative">
            <div className="absolute -inset-3 -z-10 rounded-[2.25rem] bg-gradient-to-br from-rose-100 to-white blur-xl" />
            <img
              src={IMG.group}
              alt="Product lineup"
              className="mx-auto w-full max-w-md rounded-[2rem] shadow-xl ring-1 ring-rose-200"
            />
          </div>
        </div>
      </Section>

      {/* CONTACT */}
      <Section id="contact">
        <div className="grid gap-8 md:grid-cols-2">
          <div>
            <h2 className="text-3xl font-extrabold tracking-tight text-gray-900">Get in touch</h2>
            <p className="mt-2 max-w-lg text-gray-600">
              Wholesale, press, or general questions? Send us a note. For order updates, include
              your name and email so we can get back to you fast.
            </p>
            <form className="mt-6 grid gap-4">
              <label className="text-sm font-medium text-gray-700">Name
                <input className="mt-1 w-full rounded-xl border border-gray-200 bg-white px-4 py-3 text-sm outline-none ring-rose-200 focus:ring" placeholder="Your name"/>
              </label>
              <label className="text-sm font-medium text-gray-700">Email
                <input type="email" className="mt-1 w-full rounded-xl border border-gray-200 bg-white px-4 py-3 text-sm outline-none ring-rose-200 focus:ring" placeholder="you@example.com"/>
              </label>
              <label className="text-sm font-medium text-gray-700">Message
                <textarea rows={5} className="mt-1 w-full rounded-xl border border-gray-200 bg-white px-4 py-3 text-sm outline-none ring-rose-200 focus:ring" placeholder="How can we help?"/>
              </label>
              <div>
                <Button>Send message</Button>
              </div>
            </form>
          </div>
          <div className="rounded-3xl bg-white p-6 ring-1 ring-gray-100">
            <h3 className="text-lg font-semibold text-gray-900">Business details</h3>
            <ul className="mt-3 space-y-2 text-sm text-gray-700">
              <li><strong>Email:</strong> hello@redem.skin (example)</li>
              <li><strong>Instagram:</strong> @redem.skin</li>
              <li><strong>Hours:</strong> Mon–Fri, 9am–5pm</li>
              <li><strong>Shipping:</strong> U.S. only during soft launch</li>
            </ul>
            <div className="mt-6 rounded-2xl bg-rose-50 p-4 text-sm text-gray-700 ring-1 ring-rose-100">
              <strong>Note:</strong> This is a demo site. Replace contact details with your real
              business information before publishing.
            </div>
          </div>
        </div>
      </Section>

      {/* FOOTER */}
      <footer className="mt-10 border-t border-rose-100 bg-white/70">
        <div className="mx-auto grid max-w-6xl gap-8 px-5 py-10 md:grid-cols-4 md:px-8">
          <div>
            <div className="text-xl font-extrabold text-gray-900">redēm</div>
            <p className="mt-2 text-sm text-gray-600">
              Upcycled cascara skincare. Minimalist, 100% natural, and kind to skin & planet.
            </p>
          </div>
          <div>
            <div className="text-sm font-semibold text-gray-900">Shop</div>
            <ul className="mt-2 space-y-2 text-sm text-gray-600">
              <li><a href="#products" className="hover:text-rose-700">Moisturizer</a></li>
              <li><a href="#products" className="hover:text-rose-700">Cleanser</a></li>
              <li><a href="#products" className="hover:text-rose-700">Body Lotion</a></li>
            </ul>
          </div>
          <div>
            <div className="text-sm font-semibold text-gray-900">Company</div>
            <ul className="mt-2 space-y-2 text-sm text-gray-600">
              <li><a href="#about" className="hover:text-rose-700">About us</a></li>
              <li><a href="#ingredients" className="hover:text-rose-700">Ingredients</a></li>
              <li><a href="#contact" className="hover:text-rose-700">Contact</a></li>
            </ul>
          </div>
          <div>
            <div className="text-sm font-semibold text-gray-900">Stay in the loop</div>
            <form className="mt-2 flex items-center gap-2">
              <input className="w-full rounded-xl border border-gray-200 bg-white px-4 py-3 text-sm outline-none ring-rose-200 focus:ring" placeholder="Email address"/>
              <button className="rounded-xl bg-rose-600 px-4 py-3 text-sm font-semibold text-white hover:bg-rose-700">Join</button>
            </form>
          </div>
        </div>
        <div className="border-t border-rose-100 py-6 text-center text-xs text-gray-500">
          © {new Date().getFullYear()} redēm skincare. All rights reserved.
        </div>
      </footer>
    </div>
  );
}
