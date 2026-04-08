<script setup lang="ts">
import { ref } from 'vue';
import FuturisticLayout from '@/Layouts/FuturisticLayout.vue';

defineOptions({ layout: FuturisticLayout });

const profileImg = "https://pravatar.cc";

const experience = ref([
  {
    company: "Independent Software Consultant",
    role: "Senior Software Engineer",
    date: "March 2024 – Present",
    details: [
      "System Architecture Audits: PHP 8.3+ migrations using Readonly Classes and Typed Constants.",
      "API Prototyping: Designed secure RESTful API structures utilizing OAuth 2.0/JWT.",
      "Database Engineering: Indexing strategies reducing server overhead by 20%."
    ]
  },
  {
    company: "ApplicantPro",
    role: "Software Engineer / Integrations Specialist",
    date: "Nov 2021 – March 2024",
    details: [
      "Architected web applications using F3 and MySQL, increasing responsiveness by 25%.",
      "Maintained 99.9% uptime for mission-critical PHP APIs.",
      "Refactored legacy code and optimized SQL queries to reduce load times."
    ]
  },
  {
    company: "Independent Software Consultant",
    role: "Software Engineer / Integration Specialist",
    date: "March 2017 – Nov 2021",
    details: [
      "Full-Stack Development: Managed full-cycle development using Laravel and Vue.js.",
      "Integration Specialist: Developed custom middleware for Amazon MWS and social graph APIs.",
      "Legacy Modernization: Transitioned PHP 5.6 environments to PHP 7.x."
    ]
  },
  {
    company: "Dreambox Services",
    role: "Software Engineer",
    date: "July 2009 – March 2017",
    details: [
      "Designed scalable architecture for ASP.NET web applications using C#.",
      "Developed core algorithms that increased program efficiency.",
      "Conducted thorough code reviews and unit testing for high-quality releases."
    ]
  },
  {
    company: "Royal Canin",
    role: "IT Support Specialist / EDI Coordinator",
    date: "May 2008 – July 2009",
    details: ["Managed high-volume EDI transactions Facilitating seamless B2B exchange."]
  },
  {
    company: "Robert Half",
    role: "Software Consultant",
    date: "June 2007 – May 2008",
    details: ["Developed custom business software utilizing the Laravel framework and MySQL."]
  }
]);

const copyToClipboard = (text: string) => {
  navigator.clipboard.writeText(text);
  alert(`Neural Data Copied: ${text}`);
};
</script>

<template>
  <div class="max-w-5xl mx-auto space-y-12 pb-32">
    
    <!-- BIO SECTION: Optimized for both modes -->
    <section id="bio" class="p-10 bg-white dark:bg-slate-900 border border-slate-300 dark:border-blue-900/30 rounded-2xl transition-colors duration-500">
      <h2 class="text-blue-600 dark:text-blue-400 font-bold uppercase tracking-[0.4em] mb-6 flex items-center gap-4 text-[10px]">
        <span class="h-[1px] w-8 bg-blue-600 dark:bg-blue-400"></span> Summary_Archive
      </h2>
      <p class="text-lg leading-relaxed text-slate-700 dark:text-slate-300">
        Senior Software Engineer with <span class="font-bold text-slate-900 dark:text-white">15+ years of experience</span>. Specialized in <span class="text-blue-600 dark:text-blue-400">PHP 8.3</span>, MySQL optimization, and building high-performance micro-framework solutions.
      </p>
    </section>

    <!-- EXPERIENCE: Full Timeline -->
    <section id="exp" class="space-y-10">
      <h2 class="font-black uppercase tracking-[0.4em] flex items-center gap-4 text-xs text-slate-900 dark:text-white">
        <span class="h-[1px] w-8 bg-current"></span> Professional_Timeline
      </h2>
      
      <div v-for="job in experience" :key="job.company + job.date" class="relative pl-8 border-l border-blue-500/20 pb-8 last:pb-0">
        <div class="absolute -left-[5px] top-0 h-2 w-2 rounded-full bg-blue-500 shadow-[0_0_10px_rgba(59,130,246,0.5)]"></div>
        <div class="flex justify-between items-baseline mb-1">
          <h3 class="text-xl font-black uppercase italic dark:text-slate-100">{{ job.company }}</h3>
          <span class="text-[9px] font-bold text-blue-600 dark:text-blue-400 bg-blue-500/10 px-2 py-1 rounded">{{ job.date }}</span>
        </div>
        <p class="text-blue-500 dark:text-blue-400 font-bold text-[10px] uppercase mb-4 tracking-widest">{{ job.role }}</p>
        <ul class="space-y-2">
          <li v-for="detail in job.details" :key="detail" class="text-sm opacity-80 dark:opacity-70 flex gap-3 leading-relaxed dark:text-slate-300">
            <span class="text-blue-500 font-bold">>></span> {{ detail }}
          </li>
        </ul>
      </div>

      <!-- EDUCATION BLOCK with Icon -->
      <div class="p-8 border border-blue-500/20 rounded-xl bg-blue-500/5 dark:bg-blue-400/5 relative overflow-hidden mt-12">
        <i class="bi bi-mortarboard absolute -right-4 -bottom-4 text-blue-500 text-7xl opacity-10"></i>
        <h3 class="text-[10px] font-black text-blue-500 dark:text-blue-400 uppercase tracking-widest mb-4 flex items-center gap-2">
          <i class="bi bi-mortarboard-fill"></i> Academic_Credential
        </h3>
        <p class="text-lg font-black uppercase dark:text-white">B.S. Information Technology</p>
        <p class="text-sm opacity-70 italic dark:text-slate-400 text-slate-600">Vatterott College, Fenton, MO</p>
      </div>
    </section>
  </div>
</template>
