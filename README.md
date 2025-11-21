import React, { useState, useEffect } from 'react';
import { 
  Code, 
  Database, 
  Terminal, 
  Cpu, 
  BookOpen, 
  Send, 
  Linkedin, 
  Github, 
  Mail, 
  MapPin, 
  Layers,
  TrendingUp,
  BrainCircuit
} from 'lucide-react';

const Portfolio = () => {
  const [activeRole, setActiveRole] = useState(0);
  
  const roles = [
    "Student @ UCET, VBU",
    "Coding & DSA Learner",
    "Aspiring Software Engineer",
    "Passionate Tech & AI Explorer",
    "Aspiring Data Scientist",
    "Web Development Explorer"
  ];

  // Typing effect/Role switcher logic
  useEffect(() => {
    const interval = setInterval(() => {
      setActiveRole((prev) => (prev + 1) % roles.length);
    }, 3000);
    return () => clearInterval(interval);
  }, []);

  return (
    <div className="min-h-screen bg-slate-950 text-slate-200 font-sans selection:bg-emerald-500 selection:text-white">
      
      {/* Navbar */}
      <nav className="fixed top-0 w-full bg-slate-900/80 backdrop-blur-md border-b border-slate-800 z-50">
        <div className="max-w-6xl mx-auto px-4 py-4 flex justify-between items-center">
          <div className="font-bold text-xl tracking-tighter text-emerald-400">
            <span className="text-white">BK</span>.Dev
          </div>
          <div className="hidden md:flex space-x-8 text-sm font-medium text-slate-400">
            <a href="#about" className="hover:text-emerald-400 transition-colors">About</a>
            <a href="#philosophy" className="hover:text-emerald-400 transition-colors">Philosophy</a>
            <a href="#learning" className="hover:text-emerald-400 transition-colors">Approach</a>
            <a href="#roadmap" className="hover:text-emerald-400 transition-colors">Roadmap</a>
          </div>
          <a href="#connect" className="px-4 py-2 bg-emerald-600 hover:bg-emerald-500 text-white rounded-full text-sm font-semibold transition-all transform hover:scale-105">
            Let's Connect
          </a>
        </div>
      </nav>

      {/* Hero Section */}
      <header className="pt-32 pb-20 px-4">
        <div className="max-w-4xl mx-auto text-center space-y-6">
          <div className="inline-block px-3 py-1 rounded-full bg-slate-900 border border-slate-700 text-emerald-400 text-sm font-medium mb-4">
            Hello World, Welcome to my Portfolio
          </div>
          <h1 className="text-5xl md:text-7xl font-extrabold tracking-tight text-white">
            Hi there, I'm <br />
            <span className="text-transparent bg-clip-text bg-gradient-to-r from-emerald-400 to-cyan-500">
              Baishnavi Kumari
            </span>
          </h1>
          
          {/* Dynamic Role Switcher */}
          <div className="h-8 md:h-12 overflow-hidden relative mt-4">
             <p key={activeRole} className="text-xl md:text-2xl text-slate-400 animate-fade-in-up">
               {roles[activeRole]}
             </p>
          </div>
        </div>
      </header>

      {/* About Me Section */}
      <section id="about" className="py-20 bg-slate-900">
        <div className="max-w-4xl mx-auto px-4">
          <div className="flex flex-col md:flex-row gap-12 items-center">
            <div className="w-full md:w-1/3 flex justify-center">
              {/* Placeholder for Profile Image or abstract avatar */}
              <div className="w-48 h-48 rounded-full bg-gradient-to-tr from-emerald-500 to-cyan-600 p-1">
                <div className="w-full h-full rounded-full bg-slate-800 flex items-center justify-center">
                  <Terminal size={64} className="text-emerald-400" />
                </div>
              </div>
            </div>
            <div className="w-full md:w-2/3 space-y-6">
              <h2 className="text-3xl font-bold text-white flex items-center gap-2">
                <UserIcon /> About Me
              </h2>
              <p className="text-slate-300 leading-relaxed text-lg">
                I am a Computer Science undergraduate at <strong className="text-white">UCET, VBU Hazaribagh</strong>, 
                passionate about bridging the gap between raw logic and impactful data. currently laying the 
                foundation of my software engineering journey with core languages like <span className="text-emerald-400">C, C++, and Python</span>.
              </p>
              <p className="text-slate-300 leading-relaxed text-lg">
                My ultimate compass points toward the dynamic world of <strong className="text-white">Data Science</strong>. 
                I am not just learning to code; I am learning to think, analyze, and build solutions for the future.
              </p>
              
              <div className="border-l-4 border-emerald-500 pl-4 py-2 bg-slate-800/50 rounded-r-lg">
                <p className="italic text-emerald-300 font-medium">
                  "Code is the logic; Data is the story. My goal is to master the art of both."
                </p>
              </div>
            </div>
          </div>
        </div>
      </section>

      {/* Tech Philosophy */}
      <section id="philosophy" className="py-20 px-4">
        <div className="max-w-4xl mx-auto">
          <h2 className="text-3xl font-bold text-white mb-12 text-center">My Tech Philosophy</h2>
          <div className="grid grid-cols-1 md:grid-cols-3 gap-6">
            <PhilosophyCard 
              icon={<BrainCircuit />}
              title="Curiosity First"
              desc="Technology evolves daily. I believe in remaining a perpetual student, exploring AI frontiers and asking 'why' before 'how'."
            />
            <PhilosophyCard 
              icon={<Layers />}
              title="Solid Foundations"
              desc="Great skyscrapers need deep roots. I focus on mastering DSA and core Computer Science concepts before jumping into frameworks."
            />
            <PhilosophyCard 
              icon={<TrendingUp />}
              title="Data Driven"
              desc="In a world of noise, data provides clarity. My approach combines analytical rigor with creative problem solving."
            />
          </div>
        </div>
      </section>

      {/* Learning Approach Table */}
      <section id="learning" className="py-20 bg-slate-900 px-4">
        <div className="max-w-5xl mx-auto">
          <h2 className="text-3xl font-bold text-white mb-8 flex items-center gap-2">
            <BookOpen className="text-emerald-400" /> My Learning Approach
          </h2>
          <p className="text-slate-400 mb-8">
            A structured breakdown of how I am building my skill set for a Data Science career.
          </p>
          
          <div className="overflow-x-auto rounded-xl border border-slate-700 shadow-2xl">
            <table className="w-full text-left border-collapse">
              <thead>
                <tr className="bg-slate-800 text-emerald-400 border-b border-slate-700">
                  <th className="p-4 font-semibold">Phase</th>
                  <th className="p-4 font-semibold">Key Focus Area</th>
                  <th className="p-4 font-semibold">Tools & Languages</th>
                  <th className="p-4 font-semibold">Relevance to Data Science</th>
                </tr>
              </thead>
              <tbody className="text-slate-300">
                <tr className="border-b border-slate-800 hover:bg-slate-800/50 transition-colors">
                  <td className="p-4 font-medium text-white">Phase 1: The Foundation</td>
                  <td className="p-4">Logic Building & Algorithms</td>
                  <td className="p-4 text-sm">C, C++, DSA Basics</td>
                  <td className="p-4 text-sm">Optimizing code performance for handling large datasets efficiently.</td>
                </tr>
                <tr className="border-b border-slate-800 hover:bg-slate-800/50 transition-colors">
                  <td className="p-4 font-medium text-white">Phase 2: The Interface</td>
                  <td className="p-4">Web Development Basics</td>
                  <td className="p-4 text-sm">HTML, CSS, Basic JavaScript</td>
                  <td className="p-4 text-sm">Understanding how data is collected and displayed on the web.</td>
                </tr>
                <tr className="border-b border-slate-800 hover:bg-slate-800/50 transition-colors">
                  <td className="p-4 font-medium text-white">Phase 3: The Analysis</td>
                  <td className="p-4">Scripting & Manipulation</td>
                  <td className="p-4 text-sm">Python, NumPy, Pandas</td>
                  <td className="p-4 text-sm">The core toolkit for cleaning, analyzing, and interpreting raw data.</td>
                </tr>
                <tr>
                  <td className="p-4 font-medium text-white">Phase 4: The Intelligence</td>
                  <td className="p-4">Statistics & Machine Learning</td>
                  <td className="p-4 text-sm">SQL, Scikit-learn, Visualization</td>
                  <td className="p-4 text-sm">Building predictive models to derive actionable insights.</td>
                </tr>
              </tbody>
            </table>
          </div>
        </div>
      </section>

      {/* Tech Stack */}
      <section className="py-16 px-4 border-b border-slate-800">
         <div className="max-w-4xl mx-auto">
            <h3 className="text-xl font-semibold text-slate-400 mb-6 uppercase tracking-wider">Current Tech Stack</h3>
            <div className="flex flex-wrap gap-4">
              <TechBadge name="C Programming" />
              <TechBadge name="C++" />
              <TechBadge name="Python" />
              <TechBadge name="Data Structures" />
              <TechBadge name="HTML5 & CSS3" />
              <TechBadge name="Git & Github" />
              <TechBadge name="Problem Solving" />
            </div>
         </div>
      </section>

      {/* Roadmap 2025-26 */}
      <section id="roadmap" className="py-20 px-4 bg-slate-950">
        <div className="max-w-3xl mx-auto">
           <h2 className="text-3xl font-bold text-white mb-12 text-center">Journey Roadmap 2025-26</h2>
           <div className="relative border-l-2 border-emerald-500/30 ml-4 space-y-12">
             
             <RoadmapItem 
               year="2025 Q1-Q2"
               title="Solidifying Foundations"
               content="Mastering Advanced Data Structures in C++. Solving 200+ LeetCode problems. Deep dive into Object-Oriented Programming."
             />
             
             <RoadmapItem 
               year="2025 Q3-Q4"
               title="Web & Python Integration"
               content="Building full-stack web projects. Transitioning focus to Python for Data Analysis (Pandas/Matplotlib). Participating in first Hackathon."
             />

             <RoadmapItem 
               year="2026 Q1-Q2"
               title="Data Science Specialization"
               content="Learning SQL and Database management. Introduction to Machine Learning algorithms. Developing a predictive analysis project."
             />

             <RoadmapItem 
               year="2026 Q3-Q4"
               title="Professional Integration"
               content="Securing internships in Software Engineering or Data Analysis. Contributing to Open Source. Preparing for final placements."
             />

           </div>
        </div>
      </section>

      {/* Let's Connect */}
      <section id="connect" className="py-20 bg-gradient-to-b from-slate-900 to-slate-950 px-4">
        <div className="max-w-4xl mx-auto text-center">
          <h2 className="text-4xl font-bold text-white mb-6">Let's Connect</h2>
          <p className="text-slate-400 mb-10 max-w-lg mx-auto">
            I am always open to discussing code, data, and new opportunities. Feel free to reach out if you want to collaborate or just say hi!
          </p>
          
          <div className="grid grid-cols-1 md:grid-cols-3 gap-4 max-w-2xl mx-auto">
             <ContactCard icon={<Mail size={20}/>} text="Email Me" href="mailto:your.email@example.com" />
             <ContactCard icon={<Linkedin size={20}/>} text="LinkedIn" href="#" />
             <ContactCard icon={<Github size={20}/>} text="GitHub" href="#" />
          </div>

          <div className="mt-12 flex items-center justify-center gap-2 text-slate-500 text-sm">
            <MapPin size={16} />
            <span>VBU Hazaribagh, Jharkhand</span>
          </div>
        </div>
      </section>

      <footer className="py-6 text-center text-slate-600 text-sm border-t border-slate-900">
        <p>© 2025 Baishnavi Kumari. Crafted with logic and creativity.</p>
      </footer>

    </div>
  );
};

/* Helper Components */

const PhilosophyCard = ({ icon, title, desc }) => (
  <div className="p-6 bg-slate-900 border border-slate-800 rounded-xl hover:border-emerald-500/50 transition-all group">
    <div className="w-12 h-12 bg-slate-800 rounded-lg flex items-center justify-center text-emerald-400 mb-4 group-hover:scale-110 transition-transform">
      {icon}
    </div>
    <h3 className="text-xl font-semibold text-white mb-2">{title}</h3>
    <p className="text-slate-400 text-sm leading-relaxed">{desc}</p>
  </div>
);

const TechBadge = ({ name }) => (
  <span className="px-4 py-2 bg-slate-900 border border-slate-700 rounded-full text-slate-300 text-sm font-medium hover:border-emerald-400 hover:text-emerald-400 transition-colors cursor-default">
    {name}
  </span>
);

const RoadmapItem = ({ year, title, content }) => (
  <div className="relative pl-8">
    <div className="absolute -left-[9px] top-0 w-4 h-4 rounded-full bg-emerald-500 border-4 border-slate-950"></div>
    <span className="text-emerald-400 font-bold text-sm mb-1 block">{year}</span>
    <h3 className="text-xl font-semibold text-white mb-2">{title}</h3>
    <p className="text-slate-400">{content}</p>
  </div>
);

const ContactCard = ({ icon, text, href }) => (
  <a href={href} className="flex items-center justify-center gap-3 p-4 bg-slate-800 rounded-lg text-white hover:bg-emerald-600 transition-colors">
    {icon}
    <span className="font-medium">{text}</span>
  </a>
);

// Simple Icon wrapper if needed, or use Lucide directly
const UserIcon = () => (
  <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth="2" strokeLinecap="round" strokeLinejoin="round" className="text-emerald-400"><path d="M19 21v-2a4 4 0 0 0-4-4H9a4 4 0 0 0-4 4v2"></path><circle cx="12" cy="7" r="4"></circle></svg>
);

// Add simple animation style for the typing effect
const style = document.createElement('style');
style.textContent = `
  @keyframes fadeInUp {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
  }
  .animate-fade-in-up {
    animation: fadeInUp 0.5s ease-out forwards;
  }
`;
document.head.appendChild(style);

export default Portfolio;

<!--
**Baishnavi06/Baishnavi06** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
