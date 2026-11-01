<h1 align="center">Jayasimha Reddy K</h1>

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=19&pause=1000&color=00F0FF&center=true&vCenter=true&width=650&lines=Full+Stack+Developer+%26+Systems+Engineer;Building+Responsive+Web+Apps+%26+Fast+Backends;React+18+%7C+Node.js+%7C+FastAPI+%7C+C%2B%2B17;Ex-Research+Intern+%40+IISc+Bengaluru" alt="Typing SVG" />
</p>

<p align="center">
  <a href="https://github.com/JAYASIMHAREDDYK"><img src="https://img.shields.io/badge/GitHub-JAYASIMHAREDDYK-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub" /></a>
  <a href="https://linkedin.com/in/jayasimhareddyk"><img src="https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" /></a>
  <a href="mailto:jayasimhareddy.contact@gmail.com"><img src="https://img.shields.io/badge/Email-jayasimhareddy.contact@gmail.com-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email" /></a>
  <img src="https://img.shields.io/badge/Location-Bengaluru%2C%20India-blue?style=for-the-badge&logo=google-maps&logoColor=white" alt="Location" />
</p>

<p align="center">
  <img src="https://skillicons.dev/icons?i=react,nextjs,ts,js,nodejs,express,fastapi,python,postgres,mongodb,redis,kafka,cpp,docker,aws,linux,git,tailwind" alt="Tech Stack Icons" />
</p>

---

## About Me

I am a Full Stack Developer building complete, production-grade applications: from interactive client interfaces in React and Three.js to high-throughput distributed backends and low-level storage engines. I work comfortably across the entire stack, whether designing modular REST/SSE APIs, implementing real-time WebSockets, managing relational and document databases, or squeezing throughput out of single-threaded C++ event loops.

- **Education**: Computer Science Undergraduate (B.E., Class of 2027), MVJ College of Engineering, Bengaluru (CGPA: 8.0/10).
- **Industry Experience**: Former Software Engineering and Research Intern at the Computational Intelligence (CINT) Lab, Indian Institute of Science (IISc), Bengaluru.
- **End-to-End Delivery**: Built and deployed full-stack cloud applications on AWS EC2, engineered high-throughput Kafka/PostgreSQL ingestion pipelines, and wrote a C++17 RESP2 in-memory datastore matching 83% of Redis 7.0 throughput.

---

## 🏛️ Professional & Research Experience

### Software Engineering and Research Intern (Jul 2025 to Sep 2026)
**Indian Institute of Science (IISc), Computational Intelligence (CINT) Lab** | Bengaluru, India

- **CINT Lab Research Platform (Sole Full-Stack Developer)**: Designed, built, and deployed the laboratory portal end-to-end using React 18 on the frontend and Node.js, Express, and MongoDB on the backend. Secured authentication with JWT and implemented role-based access control (RBAC) separating administrative workflows from client portals. Deployed on AWS EC2 with continuous integration and deployment on git push (75 registered researchers, 50 active monthly).
- **YogaBud Full-Stack Refactor**: Transformed a monolithic Node.js application into modular micro-services with dedicated RAG retrieval, ONNX model inference, and real-time Server-Sent Events (SSE) streaming text directly to client interfaces. Live in production with ~150 registered users (55 to 70 active monthly).
- **GPU-Accelerated Transcription & Retrieval**: Built a Whisper pipeline on ONNX Runtime utilizing lab server GPUs to index a 135-video lecture library, reaching BM25 search retrieval latency of 3 ms with automated fallback to Groq and Anthropic Claude APIs.
- **Data Integrity & Booking Engine**: Enforced zero double-bookings across calendar reservations using unique compound database indexes in MongoDB.

---

## 📌 Featured Full-Stack & Systems Projects

### 1. [STRATOS: Spacecraft Fault Recovery](https://github.com/JAYASIMHAREDDYK/STRATOS)
*Full-Stack Deep RL Telemetry & 3D Simulation Platform*  
`React, Three.js WebGL, WebSockets, FastAPI, Python, PyTorch, Qwen3`

- **Interactive 3D Frontend**: Developed a real-time spacecraft visualization dashboard in Three.js and WebSockets, rendering live attitude, thermal, power, and compute states under radiation fault injections.
- **Dual-Layer Backend**: Built a high-speed FastAPI service bridging the frontend event stream to a POMDP physics simulation environment and deep reinforcement learning agent.
- **Model Fine-Tuning**: Fine-tuned Qwen3-1.7B with LoRA and GRPO: achieved **87.9% fault recovery** vs 79.4% for LSTM-PPO baselines, reducing catastrophic mission failures from 12.4% to 5.9% across 1,500 test episodes (3 random seeds).
- **Academic Recognition**: Co-authored a research paper under review for AISIGH-SD 2026 (IEEE).

### 2. [Sluice](https://github.com/JAYASIMHAREDDYK/Sluice)
*High-Throughput Event-Driven Transaction Gateway*  
`Node.js, Fastify, Redis, Apache Kafka, PostgreSQL, Docker`

- **High-Velocity Ingestion**: Sustains **2,565 req/s** with p50 21.9 ms and zero errors across 102,617 requests under automated k6 load suites.
- **Strict Idempotency Guard**: Implemented token-bucket rate limiting via atomic Redis Lua scripts and SHA-256 idempotency locks: 10,000 concurrent duplicate requests produce exactly 1 Kafka message and 1 PostgreSQL row.
- **Asynchronous Persistence Worker**: Designed an at-least-once ledger worker with sorted row locks and offset commits tied strictly to database commits (625 tx/s), with automated Dead-Letter-Queue (DLQ) retry routing.
- **Resilience Under Failure**: Verified zero request loss during a simulated 30-second PostgreSQL outage under load; Kafka buffered the entire backlog without data corruption.

### 3. [RedisClone](https://github.com/JAYASIMHAREDDYK/RedisClone)
*In-Memory Key-Value Datastore & Async Replication Engine in C++17*  
`C++17, Linux epoll, POSIX Sockets, TCP/IP, LLVM libFuzzer`

- **Head-to-Head vs Redis 7.0**: Reaches **83.4% SET** (766k ops/sec) and **80.1% GET** (970k ops/sec) throughput on identical 1M-request benchmarks across a 1M random keyspace (`-r 1000000`). Sustains 2.49M SET and 2.80M GET ops/sec on single hot-key workloads.
- **Reactor Architecture**: Single-threaded edge-triggered Linux `epoll` reactor handling non-blocking TCP streams with pipelined batching.
- **Progressive Dual-Table Rehashing**: Amortizes hash table expansion incrementally across queries ($O(1)$ per operation), bounding resize latency jitter to under 1.2 ms.
- **Primary-Replica Streaming**: Circular ring buffer replication backlog with continuous byte offsets, full snapshot synchronization (`PSYNC ? -1`), partial resync (`+CONTINUE`), and `WAIT` semi-sync barriers.
- **Quantified Failover Durability**: Measured write loss by injecting mid-stream `SIGKILL` into the primary: 0.0% loss on LAN, 59% to 62% under 10 ms simulated WAN delay, eliminated completely (0 of 10,000 writes lost) with `WAIT 1`.
- **Fuzzed & Hardened**: Fuzzed with LLVM `libFuzzer`, ASan, and UBSan across 1.25M+ executions; found and fixed 4 edge-case vulnerabilities, backed by a committed seed corpus.

### 4. [OrderMatchingEngine (OME)](https://github.com/JAYASIMHAREDDYK/OrderMatchingEngine)
*Deterministic Low-Latency Limit Order Book in Modern C++*  
`C++17, Memory Alignment, Cache-Conscious Data Structures`

- **Deterministic Trade Matching**: Nanosecond-scale trade execution matching orders with strict price-time priority (`FIFO`).
- **Contiguous Memory Structures**: Cache-conscious order book layouts minimizing cache misses and dynamic heap allocations during high-frequency order placement, cancellation, and execution.

---

## 🛠️ Full-Stack Technical Stack & Tooling

<table>
  <tr>
    <td align="center" width="140"><b>Frontend & UI</b></td>
    <td>
      <img src="https://img.shields.io/badge/React_18-61DAFB?style=flat-square&logo=react&logoColor=black" />
      <img src="https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white" />
      <img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white" />
      <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black" />
      <img src="https://img.shields.io/badge/Three.js_(3D)-000000?style=flat-square&logo=threedotjs&logoColor=white" />
      <img src="https://img.shields.io/badge/Tailwind_CSS-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white" />
      <img src="https://img.shields.io/badge/HTML5/CSS3-E34F26?style=flat-square&logo=html5&logoColor=white" />
    </td>
  </tr>
  <tr>
    <td align="center"><b>Backend & APIs</b></td>
    <td>
      <img src="https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=nodedotjs&logoColor=white" />
      <img src="https://img.shields.io/badge/Fastify-000000?style=flat-square&logo=fastify&logoColor=white" />
      <img src="https://img.shields.io/badge/Express.js-000000?style=flat-square&logo=express&logoColor=white" />
      <img src="https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white" />
      <img src="https://img.shields.io/badge/WebSockets-010101?style=flat-square&logo=socketdotio&logoColor=white" />
      <img src="https://img.shields.io/badge/Server--Sent_Events-FF6B6B?style=flat-square&logo=fastapi&logoColor=white" />
      <img src="https://img.shields.io/badge/JWT_Auth_&_RBAC-000000?style=flat-square&logo=jsonwebtokens&logoColor=white" />
    </td>
  </tr>
  <tr>
    <td align="center"><b>Languages & Systems</b></td>
    <td>
      <img src="https://img.shields.io/badge/C++17/20-00599C?style=flat-square&logo=c%2B%2B&logoColor=white" />
      <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" />
      <img src="https://img.shields.io/badge/Linux_epoll-FCC624?style=flat-square&logo=linux&logoColor=black" />
      <img src="https://img.shields.io/badge/POSIX_Sockets-333333?style=flat-square&logo=gnubash&logoColor=white" />
      <img src="https://img.shields.io/badge/Bash-4EAA25?style=flat-square&logo=gnu-bash&logoColor=white" />
    </td>
  </tr>
  <tr>
    <td align="center"><b>Databases & Messaging</b></td>
    <td>
      <img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white" />
      <img src="https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white" />
      <img src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white" />
      <img src="https://img.shields.io/badge/Apache_Kafka-231F20?style=flat-square&logo=apachekafka&logoColor=white" />
      <img src="https://img.shields.io/badge/SQL-4479A1?style=flat-square&logo=postgresql&logoColor=white" />
    </td>
  </tr>
  <tr>
    <td align="center"><b>Cloud & DevOps</b></td>
    <td>
      <img src="https://img.shields.io/badge/AWS_EC2-FF9900?style=flat-square&logo=amazonec2&logoColor=white" />
      <img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white" />
      <img src="https://img.shields.io/badge/GitHub_Actions_CI/CD-2088FF?style=flat-square&logo=githubactions&logoColor=white" />
      <img src="https://img.shields.io/badge/CMake-064F8C?style=flat-square&logo=cmake&logoColor=white" />
      <img src="https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white" />
    </td>
  </tr>
  <tr>
    <td align="center"><b>Testing & Reliability</b></td>
    <td>
      <img src="https://img.shields.io/badge/k6_Load_Testing-7D64FF?style=flat-square&logo=k6&logoColor=white" />
      <img src="https://img.shields.io/badge/LLVM_libFuzzer-268B07?style=flat-square&logo=llvm&logoColor=white" />
      <img src="https://img.shields.io/badge/AddressSanitizer_(ASan)-E53935?style=flat-square&logo=clang&logoColor=white" />
      <img src="https://img.shields.io/badge/UBSan-FB8C00?style=flat-square&logo=llvm&logoColor=white" />
      <img src="https://img.shields.io/badge/Postman-FF6C37?style=flat-square&logo=postman&logoColor=white" />
    </td>
  </tr>
</table>

---

## 🏆 Honours & Achievements

- **2nd Prize, CODEX 2026**: Solar Irradiance Forecasting competition, organized by Don Bosco College, Bangalore.
- **Top 100 out of 30,000+ Participants**: Meta PyTorch OpenEnv Hackathon (Scaler School).

---

## 📈 Activity & Stats

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=JAYASIMHAREDDYK&show_icons=true&theme=tokyonight&hide_border=true&bg_color=0d1117&title_color=00f0ff&icon_color=00f0ff&text_color=c0caf5" alt="GitHub Stats" height="165" />
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=JAYASIMHAREDDYK&layout=compact&theme=tokyonight&hide_border=true&bg_color=0d1117&title_color=00f0ff&text_color=c0caf5" alt="Top Languages" height="165" />
</p>

<p align="center">
  <img src="https://github-readme-streak-stats.herokuapp.com/?user=JAYASIMHAREDDYK&theme=tokyonight&hide_border=true&background=0d1117&ring=00f0ff&fire=00f0ff&currStreakLabel=00f0ff&sideLabels=c0caf5&dates=7aa2f7" alt="GitHub Streak" />
</p>
