import React from "react";
import {
  Github, Linkedin, Mail, MapPin, ArrowUpRight, ArrowDown,
  Sparkles, Flame, Star, BookMarked, TrendingUp, Code2
} from "lucide-react";
import { PieChart, Pie, Cell, ResponsiveContainer } from "recharts";

const FONTS = `
@import url('https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=Inter:wght@400;500;600&family=JetBrains+Mono:wght@400;500&display=swap');
`;

const palette = {
  bg: "#09090b",
  surface: "#121214",
  surface2: "#1a1a1d",
  border: "#26262a",
  text: "#f2efe9",
  muted: "#8b8b92",
  gold: "#d9b45c",
  goldSoft: "#d9b45c22",
  violet: "#8b7cf6",
  violetSoft: "#8b7cf622",
};

const display = { fontFamily: "'Space Grotesk', sans-serif" };
const body = { fontFamily: "'Inter', sans-serif" };
const mono = { fontFamily: "'JetBrains Mono', monospace" };

const langData = [
  { name: "Python", value: 56.1, color: "#d9b45c" },
  { name: "JavaScript", value: 18.7, color: "#8b7cf6" },
  { name: "Java", value: 10.5, color: "#5fb3a3" },
  { name: "C++", value: 7.3, color: "#e0745c" },
  { name: "Other", value: 7.4, color: "#4a4a50" },
];

const techStack = ["Python", "JavaScript", "React", "Node.js", "HTML5", "CSS3", "Firebase", "Git", "C++", "VS Code"];

const projects = [
  {
    name: "EduForge",
    desc: "AI-powered learning platform with smart roadmaps, mock tests and progress analytics.",
    tags: ["React", "Firebase", "AI"],
  },
  {
    name: "My Portfolio",
    desc: "A responsive developer portfolio site showcasing my projects, skills and achievements.",
    tags: ["HTML", "CSS", "JavaScript"],
  },
  {
    name: "Stadium Command Centre",
    desc: "Real-time stadium monitoring dashboard built for smart, large-scale event management.",
    tags: ["React", "Tailwind", "Firebase"],
  },
  {
    name: "LeetCode Solutions",
    desc: "A growing archive of 250+ DSA problems solved with clean, explained Python code.",
    tags: ["Python", "DSA"],
  },
];

function ContributionGrid() {
  let s = 42;
  const rand = () => { s = (s * 9301 + 49297) % 233280; return s / 233280; };
  const levels = ["#1a1a1d", "#4a3a1c", "#8a6a24", "#c99a30", "#d9b45c"];
  const rows = 7, cols = 30;
  const grid = Array.from({ length: rows }, () => Array.from({ length: cols }, () => Math.floor(rand() * 5)));
  return (
    <div style={{ display: "flex", flexDirection: "column", gap: 3 }}>
      {grid.map((row, i) => (
        <div key={i} style={{ display: "flex", gap: 3 }}>
          {row.map((lvl, j) => (
            <div key={j} style={{ width: 8, height: 8, borderRadius: 2, backgroundColor: levels[lvl] }} />
          ))}
        </div>
      ))}
    </div>
  );
}

function StatChip({ icon: Icon, label, value }) {
  return (
    <div
      className="flex items-center gap-3 rounded-lg p-4"
      style={{ backgroundColor: palette.surface, border: `1px solid ${palette.border}` }}
    >
      <div
        className="flex items-center justify-center rounded-md p-2"
        style={{ backgroundColor: palette.goldSoft }}
      >
        <Icon size={16} style={{ color: palette.gold }} />
      </div>
      <div>
        <div className="text-xl font-semibold" style={{ ...display, color: palette.text }}>{value}</div>
        <div className="text-xs" style={{ ...body, color: palette.muted }}>{label}</div>
      </div>
    </div>
  );
}

export default function PremiumDevProfile() {
  return (
    <div style={{ backgroundColor: palette.bg, minHeight: "100vh", color: palette.text, ...body }}>
      <style>{FONTS}</style>

      {/* ambient glow */}
      <div className="relative overflow-hidden">
        <div
          style={{
            position: "absolute", top: -120, left: "10%", width: 480, height: 480,
            background: `radial-gradient(circle, ${palette.gold}22 0%, transparent 70%)`,
            filter: "blur(40px)", pointerEvents: "none",
          }}
        />
        <div
          style={{
            position: "absolute", top: 80, right: "5%", width: 420, height: 420,
            background: `radial-gradient(circle, ${palette.violet}1c 0%, transparent 70%)`,
            filter: "blur(40px)", pointerEvents: "none",
          }}
        />

        {/* Nav */}
        <div className="relative z-10 max-w-6xl mx-auto px-6 md:px-10 pt-8 flex items-center justify-between">
          <div
            className="w-10 h-10 rounded-full flex items-center justify-center text-sm font-semibold"
            style={{ border: `1px solid ${palette.border}`, ...display, color: palette.gold }}
          >
            DK
          </div>
          <div className="hidden sm:flex items-center gap-8 text-sm" style={{ color: palette.muted, ...body }}>
            <span>Work</span>
            <span>Stack</span>
            <span>Contact</span>
          </div>
          <div
            className="text-xs px-3 py-1.5 rounded-full flex items-center gap-1.5"
            style={{ border: `1px solid ${palette.border}`, ...mono, color: palette.muted }}
          >
            <span style={{ width: 6, height: 6, borderRadius: 999, backgroundColor: "#5fd97a", display: "inline-block" }} />
            open to work
          </div>
        </div>

        {/* Hero */}
        <div className="relative z-10 max-w-6xl mx-auto px-6 md:px-10 pt-16 pb-20">
          <p
            className="text-xs tracking-[0.3em] uppercase mb-6"
            style={{ ...mono, color: palette.gold }}
          >
            // Full Stack Developer — AI Enthusiast
          </p>

          <h1
            style={{
              ...display,
              fontWeight: 600,
              fontSize: "clamp(3rem, 10vw, 8rem)",
              lineHeight: 0.95,
              letterSpacing: "-0.02em",
              margin: 0,
            }}
          >
            <span style={{ color: palette.text }}>Dhiraj</span>
            <br />
            <span
              style={{
                background: `linear-gradient(90deg, ${palette.gold}, #f3e0ad, ${palette.gold})`,
                WebkitBackgroundClip: "text",
                backgroundClip: "text",
                color: "transparent",
              }}
            >
              Kumar
            </span>
          </h1>

          <div className="mt-8 flex flex-wrap items-center gap-x-8 gap-y-3">
            <p className="text-base md:text-lg max-w-xl" style={{ color: palette.muted, ...body }}>
              CSE (IoT) student building full-stack &amp; AI-driven products — from idea to
              production. Currently sharpening DSA and shipping side projects.
            </p>
          </div>

          <div className="mt-8 flex flex-wrap items-center gap-3">
            <span
              className="flex items-center gap-1.5 text-xs px-3 py-2 rounded-full"
              style={{ border: `1px solid ${palette.border}`, color: palette.muted, ...mono }}
            >
              <MapPin size={13} /> Patna, Bihar, India
            </span>
            <a
              href="#"
              className="flex items-center gap-1.5 text-xs px-4 py-2 rounded-full"
              style={{ backgroundColor: palette.text, color: palette.bg, ...mono, fontWeight: 600 }}
            >
              View Resume <ArrowUpRight size={13} />
            </a>
            <a
              href="#"
              className="flex items-center gap-1.5 text-xs px-4 py-2 rounded-full"
              style={{ border: `1px solid ${palette.border}`, color: palette.text, ...mono }}
            >
              <Github size={13} /> GitHub
            </a>
          </div>
        </div>
      </div>

      {/* Content */}
      <div className="max-w-6xl mx-auto px-6 md:px-10 pb-24 space-y-16">

        {/* Stats row */}
        <div className="grid grid-cols-2 md:grid-cols-4 gap-4">
          <StatChip icon={TrendingUp} label="Contributions" value="204" />
          <StatChip icon={Flame} label="Current Streak" value="26" />
          <StatChip icon={Star} label="Stars Earned" value="132" />
          <StatChip icon={BookMarked} label="Repositories" value="18" />
        </div>

        {/* Activity + Languages */}
        <div className="grid grid-cols-1 lg:grid-cols-[1.4fr_1fr] gap-6">
          <div className="rounded-xl p-6" style={{ backgroundColor: palette.surface, border: `1px solid ${palette.border}` }}>
            <div className="flex items-center justify-between mb-6">
              <h3 className="text-sm uppercase tracking-wider" style={{ ...mono, color: palette.muted }}>
                Contribution activity
              </h3>
              <Sparkles size={15} style={{ color: palette.gold }} />
            </div>
            <div className="overflow-x-auto">
              <ContributionGrid />
            </div>
          </div>

          <div className="rounded-xl p-6" style={{ backgroundColor: palette.surface, border: `1px solid ${palette.border}` }}>
            <h3 className="text-sm uppercase tracking-wider mb-6" style={{ ...mono, color: palette.muted }}>
              Language mix
            </h3>
            <div className="flex items-center gap-5">
              <div style={{ width: 120, height: 120 }} className="shrink-0">
                <ResponsiveContainer width="100%" height="100%">
                  <PieChart>
                    <Pie data={langData} dataKey="value" innerRadius={36} outerRadius={58} paddingAngle={2} stroke="none">
                      {langData.map((d, i) => <Cell key={i} fill={d.color} />)}
                    </Pie>
                  </PieChart>
                </ResponsiveContainer>
              </div>
              <div className="space-y-2 flex-1">
                {langData.map((d) => (
                  <div key={d.name} className="flex items-center justify-between text-xs">
                    <span className="flex items-center gap-2" style={{ color: palette.text, ...body }}>
                      <span style={{ width: 7, height: 7, borderRadius: 999, backgroundColor: d.color, display: "inline-block" }} />
                      {d.name}
                    </span>
                    <span style={{ color: palette.muted, ...mono }}>{d.value}%</span>
                  </div>
                ))}
              </div>
            </div>
          </div>
        </div>

        {/* Stack */}
        <div>
          <h3 className="text-sm uppercase tracking-wider mb-5" style={{ ...mono, color: palette.muted }}>
            Toolkit
          </h3>
          <div className="flex flex-wrap gap-2.5">
            {techStack.map((t) => (
              <span
                key={t}
                className="text-sm px-4 py-2 rounded-full"
                style={{ border: `1px solid ${palette.border}`, backgroundColor: palette.surface, color: palette.text, ...body }}
              >
                {t}
              </span>
            ))}
          </div>
        </div>

        {/* Projects */}
        <div>
          <div className="flex items-baseline justify-between mb-6">
            <h3 className="text-sm uppercase tracking-wider" style={{ ...mono, color: palette.muted }}>
              Selected work
            </h3>
            <span className="text-xs" style={{ ...mono, color: palette.muted }}>{projects.length} projects</span>
          </div>
          <div className="grid grid-cols-1 md:grid-cols-2 gap-4">
            {projects.map((p) => (
              <a
                key={p.name}
                href="#"
                className="group rounded-xl p-6 block transition-colors"
                style={{ backgroundColor: palette.surface, border: `1px solid ${palette.border}` }}
              >
                <div className="flex items-start justify-between mb-4">
                  <div
                    className="w-10 h-10 rounded-lg flex items-center justify-center"
                    style={{ backgroundColor: palette.violetSoft }}
                  >
                    <Code2 size={18} style={{ color: palette.violet }} />
                  </div>
                  <ArrowUpRight
                    size={16}
                    style={{ color: palette.muted }}
                    className="group-hover:opacity-100 opacity-40 transition-opacity"
                  />
                </div>
                <h4 className="text-lg font-semibold mb-2" style={{ ...display, color: palette.text }}>
                  {p.name}
                </h4>
                <p className="text-sm mb-4" style={{ color: palette.muted, ...body, lineHeight: 1.5 }}>
                  {p.desc}
                </p>
                <div className="flex flex-wrap gap-1.5">
                  {p.tags.map((tag) => (
                    <span
                      key={tag}
                      className="text-[11px] px-2 py-1 rounded"
                      style={{ backgroundColor: palette.goldSoft, color: palette.gold, ...mono }}
                    >
                      {tag}
                    </span>
                  ))}
                </div>
              </a>
            ))}
          </div>
        </div>

        {/* Contact */}
        <div
          className="rounded-xl p-10 md:p-14 text-center"
          style={{ backgroundColor: palette.surface, border: `1px solid ${palette.border}` }}
        >
          <p className="text-xs uppercase tracking-[0.3em] mb-4" style={{ ...mono, color: palette.gold }}>
            Let's build something
          </p>
          <h3
            style={{ ...display, fontSize: "clamp(1.75rem, 5vw, 3.25rem)", fontWeight: 600, lineHeight: 1.1 }}
          >
            Open to internships, collabs
            <br />
            &amp; interesting problems.
          </h3>
          <div className="mt-8 flex flex-wrap justify-center gap-3">
            <a
              href="mailto:dhirajkumar09.business@gmail.com"
              className="flex items-center gap-2 text-sm px-5 py-2.5 rounded-full"
              style={{ backgroundColor: palette.text, color: palette.bg, fontWeight: 600, ...body }}
            >
              <Mail size={15} /> Say hello
            </a>
            <a
              href="#"
              className="flex items-center gap-2 text-sm px-5 py-2.5 rounded-full"
              style={{ border: `1px solid ${palette.border}`, color: palette.text, ...body }}
            >
              <Linkedin size={15} /> LinkedIn
            </a>
            <a
              href="#"
              className="flex items-center gap-2 text-sm px-5 py-2.5 rounded-full"
              style={{ border: `1px solid ${palette.border}`, color: palette.text, ...body }}
            >
              <Github size={15} /> GitHub
            </a>
          </div>
        </div>

        <div className="flex items-center justify-between text-xs pt-4" style={{ ...mono, color: palette.muted, borderTop: `1px solid ${palette.border}` }}>
          <span>© 2026 Dhiraj Kumar</span>
          <span className="flex items-center gap-1">Made with care <ArrowDown size={12} className="rotate-45" /></span>
        </div>
      </div>
    </div>
  );
}
