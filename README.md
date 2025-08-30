import { useState } from "react";
import { motion } from "framer-motion";
import { Check, Star, Zap, Timer, Shield, MessageCircle } from "lucide-react";

// ====== Quick Config (edit these) ======
const BRAND = "Fit with Rahul";
const PHONE = "8210571855"; // WhatsApp number
const WHATSAPP_MSG = encodeURIComponent(
  "Hi Rahul! I want to join the 7-Day Free Trial. Please add me."
);
const WHATSAPP_LINK = `https://wa.me/91${PHONE}?text=${WHATSAPP_MSG}`;
// If you build a Google Form for lead capture, paste its link here:
const FORM_URL = "https://forms.gle/your-form-id"; // <- replace when ready
// Razorpay / payment link (optional for later):
const PAYMENT_LINK = ""; // e.g., https://rzp.io/l/fitwithrahul499

export default function Landing() {
  const [email, setEmail] = useState("");

  const handleForm = (e) => {
    e.preventDefault();
    if (FORM_URL && FORM_URL.includes("http")) {
      window.open(FORM_URL, "_blank");
    } else {
      window.open(WHATSAPP_LINK, "_blank");
    }
  };

  return (
    <div className="min-h-screen bg-slate-50 text-slate-800">
      {/* Header */}
      <header className="sticky top-0 z-30 backdrop-blur bg-white/70 border-b border-slate-200">
        <div className="max-w-6xl mx-auto px-4 py-3 flex items-center justify-between">
          <div className="flex items-center gap-2">
            <div className="h-9 w-9 rounded-2xl bg-slate-900 text-white grid place-items-center font-bold">FR</div>
            <span className="font-semibold">{BRAND}</span>
          </div>
          <nav className="hidden md:flex items-center gap-6 text-sm">
            <a href="#trial" className="hover:text-slate-950">Free Trial</a>
            <a href="#vip" className="hover:text-slate-950">₹499 VIP</a>
            <a href="#proof" className="hover:text-slate-950">Results</a>
            <a href="#faq" className="hover:text-slate-950">FAQ</a>
          </nav>
          <a href={WHATSAPP_LINK} target="_blank" className="rounded-2xl px-4 py-2 bg-slate-900 text-white text-sm shadow hover:opacity-90">Join Free Trial</a>
        </div>
      </header>

      {/* Hero */}
      <section className="relative overflow-hidden">
        <div className="max-w-6xl mx-auto px-4 pt-14 pb-8 grid md:grid-cols-2 gap-8 items-center">
          <motion.div initial={{ opacity: 0, y: 20 }} animate={{ opacity: 1, y: 0 }} transition={{ duration: 0.6 }}>
            <h1 className="text-3xl md:text-5xl font-bold leading-tight">
              Transform Your Body in 7 Days — <span className="text-slate-600">Free Trial Coaching</span>
            </h1>
            <p className="mt-4 text-slate-600">
              Simple workouts. Easy Indian meals. Personal WhatsApp guidance. Start your 7-day trial now — then continue for just <span className="font-semibold text-slate-900">₹499/month</span>.
            </p>
            <div className="mt-6 flex flex-wrap gap-3">
              <a href={WHATSAPP_LINK} target="_blank" className="rounded-2xl px-5 py-3 bg-slate-900 text-white shadow-lg hover:opacity-90 flex items-center gap-2">
                <Zap className="h-5 w-5" /> Join Free Trial
              </a>
              <a href="#vip" className="rounded-2xl px-5 py-3 bg-white border border-slate-300 text-slate-800 shadow hover:bg-slate-50">See ₹499 VIP Plan</a>
            </div>
            <div className="mt-4 flex items-center gap-2 text-sm text-slate-500">
              <Shield className="h-4 w-4" /> Limited spots weekly for personal attention
            </div>
          </motion.div>

          <motion.div initial={{ opacity: 0, y: 20 }} animate={{ opacity: 1, y: 0 }} transition={{ duration: 0.8 }} className="md:justify-self-end">
            <div className="relative h-64 md:h-80 rounded-3xl bg-gradient-to-br from-slate-900 to-slate-600 shadow-2xl p-1">
              <div className="h-full w-full rounded-3xl bg-white grid place-items-center p-6">
                <div className="text-center">
                  <div className="text-5xl font-extrabold">7-Day</div>
                  <div className="mt-1 text-slate-600">Transformation Starter</div>
                  <div className="mt-6 grid grid-cols-3 gap-4 text-left text-sm">
                    {[
                      "Daily mini-workouts",
                      "Diet hacks that fit Indian meals",
                      "WhatsApp support",
                    ].map((t) => (
                      <div key={t} className="flex items-start gap-2">
                        <Check className="h-4 w-4 mt-0.5" /> <span>{t}</span>
                      </div>
                    ))}
                  </div>
                  <a href={WHATSAPP_LINK} target="_blank" className="mt-6 inline-block rounded-2xl px-5 py-2.5 bg-slate-900 text-white shadow hover:opacity-90">Start Free Trial</a>
                </div>
              </div>
            </div>
          </motion.div>
        </div>
      </section>

      {/* Trust Bar */}
      <section className="border-y border-slate-200 bg-white">
        <div className="max-w-6xl mx-auto px-4 py-6 grid md:grid-cols-3 gap-4 text-sm">
          <div className="flex items-center gap-3"><Star className="h-5 w-5" /> Beginner-friendly coaching</div>
          <div className="flex items-center gap-3"><Timer className="h-5 w-5" /> 5–10 min daily tasks</div>
          <div className="flex items-center gap-3"><Shield className="h-5 w-5" /> No fad diets, sustainable</div>
        </div>
      </section>

      {/* Free Trial Section */}
      <section id="trial" className="bg-slate-50">
        <div className="max-w-6xl mx-auto px-4 py-14">
          <div className="grid md:grid-cols-2 gap-10 items-start">
            <div>
              <h2 className="text-2xl md:text-3xl font-bold">What you get in the Free 7‑Day Trial</h2>
              <p className="mt-3 text-slate-600">Get quick wins and clarity. If you love it, continue with VIP coaching for ₹499/month.</p>
              <ul className="mt-6 space-y-3 text-slate-700">
                {[
                  "Daily 5‑minute mini‑workouts (at home)",
                  "Simple diet tips with protein in every meal",
                  "Accountability prompts and motivation",
                  "Direct WhatsApp access to Coach Rahul",
                ].map((t) => (
                  <li key={t} className="flex items-start gap-3"><Check className="h-5 w-5 mt-0.5" /> {t}</li>
                ))}
              </ul>

              <div className="mt-8 flex gap-3 flex-wrap">
                <a href={WHATSAPP_LINK} target="_blank" className="rounded-2xl px-5 py-3 bg-slate-900 text-white shadow hover:opacity-90">Join Free Trial on WhatsApp</a>
                <a href={FORM_URL || "#"} target="_blank" className="rounded-2xl px-5 py-3 bg-white border border-slate-300 shadow hover:bg-slate-50">Or Fill Quick Form</a>
              </div>
            </div>

            <div className="bg-white rounded-3xl p-6 shadow-sm border border-slate-200">
              <h3 className="font-semibold text-lg">Join in 10 seconds</h3>
              <p className="text-sm text-slate-500 mb-4">Prefer sharing details first? Use the quick form; we’ll reach out on WhatsApp.</p>
              <form onSubmit={handleForm} className="space-y-3">
                <input type="text" placeholder="Your name" className="w-full rounded-xl border border-slate-300 px-4 py-2.5 focus:outline-none focus:ring-2 focus:ring-slate-300"/>
                <input type="tel" placeholder="WhatsApp number" className="w-full rounded-xl border border-slate-300 px-4 py-2.5 focus:outline-none focus:ring-2 focus:ring-slate-300"/>
                <input type="email" value={email} onChange={(e)=>setEmail(e.target.value)} placeholder="Email (optional)" className="w-full rounded-xl border border-slate-300 px-4 py-2.5 focus:outline-none focus:ring-2 focus:ring-slate-300"/>
                <button type="submit" className="w-full rounded-xl px-4 py-2.5 bg-slate-900 text-white shadow hover:opacity-90">Submit & Continue</button>
                <p className="text-xs text-slate-500">By continuing, you agree to be contacted on WhatsApp.</p>
              </form>
            </div>
          </div>
        </div>
      </section>

      {/* VIP Plan */}
      <section id="vip" className="bg-white border-y border-slate-200">
        <div className="max-w-6xl mx-auto px-4 py-14">
          <div className="grid md:grid-cols-2 gap-10 items-start">
            <div>
              <h2 className="text-2xl md:text-3xl font-bold">Continue with VIP Coaching — Only ₹499/month</h2>
              <p className="mt-3 text-slate-600">Less than ₹17/day. Get a plan that actually fits your routine, plus accountability to stick with it.</p>
              <ul className="mt-6 space-y-3 text-slate-700">
                {[
                  "Customized diet plan for your goals & foods",
                  "Personalized gym/home workout plan",
                  "1‑to‑1 chat support for doubts anytime",
                  "Weekly progress tracking & adjustments",
                ].map((t) => (
                  <li key={t} className="flex items-start gap-3"><Check className="h-5 w-5 mt-0.5" /> {t}</li>
                ))}
              </ul>
              <div className="mt-8 flex gap-3 flex-wrap">
                {PAYMENT_LINK ? (
                  <a href={PAYMENT_LINK} target="_blank" className="rounded-2xl px-5 py-3 bg-slate-900 text-white shadow hover:opacity-90">Pay ₹499 & Join VIP</a>
                ) : (
                  <a href={WHATSAPP_LINK} target="_blank" className="rounded-2xl px-5 py-3 bg-slate-900 text-white shadow hover:opacity-90">Message to Join VIP</a>
                )}
                <a href="#faq" className="rounded-2xl px-5 py-3 bg-white border border-slate-300 shadow hover:bg-slate-50">Read FAQs</a>
              </div>
            </div>

            {/* Price Card */}
            <div className="bg-slate-900 text-white rounded-3xl p-6 md:p-8 shadow-2xl">
              <div className="text-slate-300 text-sm">VIP COACHING</div>
              <div className="mt-2 text-5xl font-extrabold">₹499<span className="text-lg font-semibold">/month</span></div>
              <div className="mt-2 text-slate-300">Start after your 7‑day trial</div>
              <div className="mt-6 space-y-3 text-slate-100">
                {[
                  "Custom diet & workout plan",
                  "Daily accountability",
                  "Form checks & technique tips",
                  "Flexible for fasting/work schedules",
                ].map((t) => (
                  <div key={t} className="flex items-start gap-3"><Check className="h-5 w-5 mt-0.5" /> {t}</div>
                ))}
              </div>
              {PAYMENT_LINK ? (
                <a href={PAYMENT_LINK} target="_blank" className="mt-8 inline-block rounded-2xl px-5 py-3 bg-white text-slate-900 font-semibold shadow hover:opacity-90">Pay & Join Now</a>
              ) : (
                <a href={WHATSAPP_LINK} target="_blank" className="mt-8 inline-block rounded-2xl px-5 py-3 bg-white text-slate-900 font-semibold shadow hover:opacity-90">Chat on WhatsApp</a>
              )}
            </div>
          </div>
        </div>
      </section>

      {/* Proof / Testimonials */}
      <section id="proof" className="bg-slate-50">
        <div className="max-w-6xl mx-auto px-4 py-14">
          <h2 className="text-2xl md:text-3xl font-bold">Real People. Real Wins.</h2>
          <p className="mt-2 text-slate-600">Add your clients’ feedback screenshots or your own transformation photos here.</p>

          <div className="mt-8 grid md:grid-cols-3 gap-6">
            {[1,2,3].map((i) => (
              <div key={i} className="bg-white rounded-3xl p-5 shadow-sm border border-slate-200">
                <div className="flex items-center gap-2 text-amber-500 mb-2">
                  <Star className="h-4 w-4" /> <Star className="h-4 w-4" /> <Star className="h-4 w-4" /> <Star className="h-4 w-4" /> <Star className="h-4 w-4" />
                </div>
                <p className="text-sm text-slate-700">“I used Rahul’s simple tips and felt more energetic in one week. Diet was super practical.”</p>
                <div className="mt-3 text-xs text-slate-500">— Client Name</div>
              </div>
            ))}
          </div>
        </div>
      </section>

      {/* FAQ */}
      <section id="faq" className="bg-white border-t border-slate-200">
        <div className="max-w-6xl mx-auto px-4 py-14">
          <h2 className="text-2xl md:text-3xl font-bold">Frequently Asked Questions</h2>
          <div className="mt-6 grid md:grid-cols-2 gap-6">
            <FAQ q="Is the 7‑day trial really free?" a="Yes. You’ll get daily guidance for 7 days. If you like the results and support, you can continue with VIP for ₹499/month." />
            <FAQ q="Do I need a gym?" a="No. Trial includes simple home workouts. For VIP, I can design gym or home plans based on your preference." />
            <FAQ q="What about diet?" a="I’ll guide you to add protein to each meal using normal Indian foods (eggs, paneer, dal, sprouts, chicken). No extreme dieting." />
            <FAQ q="How do I pay ₹499?" a="Click the Join VIP button. If a payment link isn’t shown, you’ll chat with me on WhatsApp and I’ll share UPI/Razorpay." />
          </div>
        </div>
      </section>

      {/* Footer */}
      <footer className="bg-slate-950 text-slate-200">
        <div className="max-w-6xl mx-auto px-4 py-10 grid md:grid-cols-3 gap-6 items-start">
          <div>
            <div className="text-lg font-semibold">{BRAND}</div>
            <p className="text-sm text-slate-400 mt-2">Practical fitness coaching for beginners. Built around your routine — not the other way around.</p>
          </div>
          <div>
            <div className="font-semibold">Quick Links</div>
            <ul className="mt-3 space-y-2 text-sm">
              <li><a href="#trial" className="hover:underline">Free Trial</a></li>
              <li><a href="#vip" className="hover:underline">₹499 VIP</a></li>
              <li><a href="#proof" className="hover:underline">Results</a></li>
              <li><a href="#faq" className="hover:underline">FAQ</a></li>
            </ul>
          </div>
          <div>
            <div className="font-semibold">Join Now</div>
            <p className="text-sm text-slate-400 mt-2">Message me on WhatsApp to start your 7‑day free trial.</p>
            <a href={WHATSAPP_LINK} target="_blank" className="mt-3 inline-block rounded-2xl px-4 py-2 bg-white text-slate-900 font-semibold shadow hover:opacity-90">WhatsApp Me</a>
            <div className="text-xs text-slate-500 mt-3">© {new Date().getFullYear()} {BRAND}. All rights reserved.</div>
          </div>
        </div>
      </footer>

      {/* Floating WhatsApp */}
      <a href={WHATSAPP_LINK} target="_blank" aria-label="Chat on WhatsApp" className="fixed bottom-5 right-5 z-40">
        <div className="h-12 w-12 rounded-full bg-emerald-500 grid place-items-center shadow-2xl hover:scale-105 transition">
          <MessageCircle className="h-6 w-6 text-white" />
        </div>
      </a>
    </div>
  );
}

function FAQ({ q, a }) {
  const [open, setOpen] = useState(false);
  return (
    <div className="border border-slate-200 rounded-2xl p-4">
      <button onClick={() => setOpen(!open)} className="w-full flex items-center justify-between text-left">
        <span className="font-medium">{q}</span>
        <span className="text-slate-400">{open ? "–" : "+"}</span>
      </button>
      {open && <p className="mt-2 text-sm text-slate-600">{a}</p>}
    </div>
  );
}
