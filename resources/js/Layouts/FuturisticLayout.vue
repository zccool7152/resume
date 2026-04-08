<script setup lang="ts">
import { ref } from 'vue';

// PERMANENT PROFILE LOCK
const profileImg = "https://i.pravatar.cc/250?img=11";

interface Job {
  company: string;
  role: string;
  location: string;
  date: string;
  details: string[];
}

const skillRows = [
  {
    row: [
      { cat: 'Languages', items: ['PHP 8.3', 'JavaScript', 'SQL', 'C#', 'HTML5'] },
      { cat: 'Frameworks', items: ['F3', 'Laravel', 'Vue.js', 'Angular', 'jQuery'] },
      { cat: 'Backend', items: ['REST APIs', 'JSON', 'EDI', 'Integrations'] }
    ]
  },
  {
    row: [
      { cat: 'Databases', items: ['MySQL Opt.', 'Schema Design', 'Refactoring'] },
      { cat: 'Tools', items: ['Git', 'Agile', 'PHPUnit', 'CI/CD', 'SDLC'] }
    ]
  }
];

const experience = ref<Job[]>([
  {
    company: "Independent Software Consultant",
    role: "Senior Software Engineer",
    location: "Remote",
    date: "March 2024 – Present",
    details: [
      "System Architecture Audits: PHP 8.3+ migrations focusing on Readonly Classes and Typed Constants.",
      "API Prototyping: Designed secure RESTful API structures utilizing OAuth 2.0/JWT and OpenAPI/Swagger.",
      "Database Engineering: Indexing strategies reducing server overhead by 20%."
    ]
  },
  {
    company: "ApplicantPro",
    role: "Software Engineer / Integrations Specialist",
    location: "Remote",
    date: "Nov 2021 – March 2024",
    details: [
      "Architected applications using F3 and MySQL, increasing responsiveness by 25%.",
      "Maintained 99.9% uptime for mission-critical PHP APIs.",
      "Refactored legacy code and optimized SQL queries to reduce load times.",
      "Collaborated in Agile environment with peer code reviews and PHPUnit testing."
    ]
  },
  {
    company: "Independent Software Consultant",
    role: "Software Engineer / Integration Specialist",
    location: "Remote",
    date: "March 2017 – Nov 2021",
    details: [
      "Full-Stack Development: Leveraged Laravel and Vue.js for responsive data-driven apps.",
      "Integration Specialist: Developed custom middleware for Amazon MWS and social graph APIs.",
      "Legacy Modernization: Transitioned PHP 5.6 environments to PHP 7.x."
    ]
  },
  {
    company: "Dreambox Services",
    role: "Software Engineer",
    location: "Remote",
    date: "July 2009 – March 2017",
    details: [
      "Designed scalable architecture for ASP.NET web applications using C#.",
      "Developed core algorithms increasing program efficiency.",
      "Conducted thorough code reviews and unit testing for releases."
    ]
  },
  {
    company: "Royal Canin",
    role: "IT Support / EDI Coordinator",
    location: "St. Charles, MO",
    date: "May 2008 – July 2009",
    details: ["Managed high-volume EDI transactions Facilitating seamless B2B exchange."]
  },
  {
    company: "Robert Half",
    role: "Software Consultant",
    location: "St. Louis, MO",
    date: "June 2007 – May 2008",
    details: ["Developed custom business software utilizing Laravel and MySQL."]
  }
]);

const raindrops = Array.from({ length: 20 }, (_, i) => ({
  left: (i * 5) + '%',
  delay: (Math.random() * 2) + 's',
  duration: (1 + Math.random() * 2) + 's'
}));

const copyToClipboard = (text: string) => {
  navigator.clipboard.writeText(text);
  alert(`Neural Data Copied: ${text}`);
};
</script>

<template>
  <div class="min-h-screen bg-slate-100 text-slate-900 font-mono overflow-hidden">
    
    <!-- HEADER -->
    <header class="h-40 bg-slate-900 fixed top-0 w-full z-40 flex items-center px-12 overflow-hidden border-b-2 border-blue-500/30">
      <div class="lightning-strike strike-1"></div>
      <div class="lightning-strike strike-2"></div>
      <div class="lightning-glow"></div>

      <!-- Left Text -->
      <div class="z-10 pl-32">
        <h1 class="text-4xl font-black text-white uppercase italic tracking-tighter header-glow">Timothy Dunn</h1>
        <p class="text-blue-400 text-xs tracking-[0.2em] uppercase mt-1">Senior Software Engineer | Full-Stack PHP & Integrations Specialist</p>
      </div>

      <!-- RIGHT CONTACT INFO (Restored) -->
      <div class="ml-auto text-right z-10 hidden lg:block font-bold">
        <div class="text-slate-400 text-[10px] space-y-1">
          <p @click="copyToClipboard('zccool4718@outlook.com')" class="cursor-pointer hover:text-blue-400 tracking-widest uppercase"><i class="bi bi-envelope text-blue-500 mr-2"></i>zccool4718@outlook.com</p>
          <p class="tracking-widest uppercase"><i class="bi bi-geo-alt text-blue-500 mr-2"></i>Kansas City, MO</p>
          <p class="tracking-widest uppercase"><i class="bi bi-telephone text-blue-500 mr-2"></i>(636) 252-1554</p>
        </div>
      </div>
    </header>

    <div class="flex h-screen pt-40">
      <!-- SIDEBAR -->
      <aside class="w-24 bg-slate-900 border-r border-blue-900/40 flex flex-col items-center z-30 relative overflow-hidden">
        <div v-for="(drop, i) in raindrops" :key="i" class="raindrop" :style="{ left: drop.left, animationDelay: drop.delay, animationDuration: drop.duration }"></div>
        <nav class="mt-48 flex flex-col gap-8 relative z-10">
          <a href="#bio" class="w-14 h-14 flex items-center justify-center rounded-lg border border-blue-900/60 hover:bg-blue-500/20 transition-all cursor-pointer"><i class="bi bi-cpu text-blue-400 text-2xl"></i></a>
          <a href="#skills" class="w-14 h-14 flex items-center justify-center rounded-lg border border-blue-900/60 hover:bg-blue-500/20 transition-all cursor-pointer"><i class="bi bi-grid-3x3-gap text-blue-400 text-2xl"></i></a>
          <!-- RESTORED COPY ICON -->
          <button @click="copyToClipboard('zccool4718@outlook.com')" class="w-14 h-14 flex items-center justify-center rounded-lg border border-slate-700 hover:bg-white/10 transition-all text-slate-400">
            <i class="bi bi-clipboard-check text-2xl"></i>
          </button>
        </nav>
      </aside>

      <!-- HEXAGON PROFILE (Geometric Fix) -->
      <div class="fixed left-24 top-40 z-50 transform -translate-x-1/2 -translate-y-1/2">
        <div class="hexagon w-40 h-44 bg-gradient-to-b from-blue-400 to-slate-900 p-[2px] shadow-2xl">
          <div class="hexagon w-full h-full bg-slate-900 flex items-center justify-center overflow-hidden">
            <img :src="profileImg" class="w-full h-full object-cover grayscale brightness-110">
          </div>
        </div>
      </div>

      <!-- MAIN CONTENT -->
      <main class="flex-1 overflow-y-auto p-12 bg-slate-100">
        <div class="max-w-5xl mx-auto space-y-12 pb-32">
          
          <section id="bio" class="p-10 bg-white border border-slate-300 rounded-2xl shadow-sm">
            <h2 class="text-blue-600 font-bold uppercase tracking-[0.4em] mb-6 flex items-center gap-4 text-xs">
              <span class="h-[1px] w-8 bg-blue-600"></span> Summary_Archive
            </h2>
            <p class="text-lg leading-relaxed text-slate-700">Senior Software Engineer with 15+ years of experience. Expert in PHP 8.3, MySQL optimization, and building high-performance micro-framework solutions.</p>
          </section>

          <!-- SKILLS MATRIX (2-Row Restored) -->
          <section id="skills" class="space-y-4">
            <div v-for="(rowGroup, rIdx) in skillRows" :key="rIdx" :class="['grid gap-4', rIdx === 0 ? 'grid-cols-1 md:grid-cols-3' : 'grid-cols-1 md:grid-cols-2']">
              <div v-for="skill in rowGroup.row" :key="skill.cat" class="p-4 bg-slate-200/50 border border-slate-300 rounded-xl">
                <h3 class="text-[9px] font-black uppercase text-blue-600 mb-3 tracking-widest">{{ skill.cat }}</h3>
                <div class="flex flex-wrap gap-1">
                  <span v-for="item in skill.items" :key="item" class="px-2 py-1 bg-white border border-slate-300 text-[10px] font-bold rounded shadow-sm">{{ item }}</span>
                </div>
              </div>
            </div>
          </section>

          <section id="exp" class="space-y-10">
            <h2 class="font-black uppercase tracking-[0.4em] flex items-center gap-4 text-xs">
              <span class="h-[1px] w-8 bg-current"></span> Professional_Timeline
            </h2>
            <div v-for="job in experience" :key="job.company + job.date" class="relative pl-8 border-l border-blue-500/20 pb-8 last:pb-0">
              <div class="absolute -left-[5px] top-0 h-2 w-2 rounded-full bg-blue-500"></div>
              <div class="flex flex-wrap justify-between items-baseline mb-1">
                <h3 class="text-xl font-black uppercase italic">{{ job.company }}</h3>
                <span class="text-[9px] font-bold text-blue-600 bg-blue-50 px-2 py-1 rounded">{{ job.date }}</span>
              </div>
              <p class="text-blue-500 font-bold text-[10px] uppercase mb-4 tracking-widest">{{ job.role }} | {{ job.location }}</p>
              <ul class="space-y-2">
                <li v-for="detail in job.details" :key="detail" class="text-sm opacity-80 flex gap-3">
                  <span class="text-blue-500 font-bold">>></span> {{ detail }}
                </li>
              </ul>
            </div>

            <!-- EDUCATION -->
            <div class="p-8 border border-blue-500/20 rounded-xl bg-blue-500/5 relative overflow-hidden mt-12">
              <i class="bi bi-mortarboard absolute -right-4 -bottom-4 text-blue-500 text-7xl opacity-10"></i>
              <h3 class="text-[10px] font-black text-blue-500 uppercase tracking-widest mb-4 flex items-center gap-2"><i class="bi bi-mortarboard-fill"></i> Academic_Node</h3>
              <p class="text-lg font-black uppercase">Bachelor of Science in IT</p>
              <p class="text-sm opacity-70 italic text-slate-600">Vatterott College, Fenton, MO</p>
            </div>
          </section>
        </div>
      </main>
    </div>
  </div>
</template>

<style scoped>
.hexagon { clip-path: polygon(50% 0%, 100% 25%, 100% 75%, 50% 100%, 0% 75%, 0% 25%); }
.raindrop { position: absolute; top: -10%; width: 1px; height: 50px; background: linear-gradient(to bottom, transparent, #3b82f6); opacity: 0.4; animation: fall linear infinite; }
@keyframes fall { to { transform: translateY(120vh); } }
.lightning-glow { position: absolute; inset: 0; background: #60a5fa; opacity: 0; animation: flash 8s infinite; }
.lightning-strike { position: absolute; top: 0; width: 2px; height: 100%; background: white; opacity: 0; }
.strike-1 { left: 20%; transform: skewX(-15deg); animation: bolt 6s infinite; }
.strike-2 { left: 80%; transform: skewX(10deg); animation: bolt 10s infinite 2s; }
@keyframes flash { 0%, 94%, 98%, 100% { opacity: 0; } 95%, 97% { opacity: 0.15; } }
@keyframes bolt { 0%, 98%, 100% { opacity: 0; transform: scaleY(0); } 99% { opacity: 0.8; transform: scaleY(1.4); } }
.header-glow { text-shadow: 0 0 15px rgba(59,130,246,0.6); }
</style>
