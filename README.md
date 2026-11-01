<h1 align="center">Jayasimha Reddy K</h1>

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=19&pause=1000&color=00F0FF&center=true&vCenter=true&width=650&lines=Low-Latency+Systems+%26+Backend+Engineer;C%2B%2B17+Epoll+Reactors+%7C+Distributed+Storage;Ex-Research+Intern+%40+IISc+Bengaluru;Building+High-Throughput%2C+Deterministic+Software" alt="Typing SVG" />
</p>

<p align="center">
  <a href="https://github.com/JAYASIMHAREDDYK"><img src="https://img.shields.io/badge/GitHub-JAYASIMHAREDDYK-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub" /></a>
  <a href="https://linkedin.com/in/jayasimhareddyk"><img src="https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" /></a>
  <a href="mailto:jayasimhareddy.contact@gmail.com"><img src="https://img.shields.io/badge/Email-jayasimhareddy.contact@gmail.com-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email" /></a>
  <img src="https://img.shields.io/badge/Location-Bengaluru%2C%20India-blue?style=for-the-badge&logo=google-maps&logoColor=white" alt="Location" />
</p>

<p align="center">
  <img src="https://skillicons.dev/icons?i=cpp,c,python,js,ts,nodejs,postgres,kafka,redis,docker,linux,git,bash,cmake,aws" alt="Tech Stack Icons" />
</p>

---

## About Me

I build low-latency systems, distributed datastores, and event-driven backends in modern C++ and Node.js/Python. Most of my work centers around non-blocking epoll reactors, cache-line conscious memory layouts, deterministic transaction pipelines, and crash-resilient replication protocols.

- **Education**: Computer Science Undergraduate (B.E., Class of 2027), MVJ College of Engineering, Bengaluru (CGPA: 8.0/10).
- **Research Experience**: Former Software Engineering and Research Intern at the Computational Intelligence (CINT) Lab, Indian Institute of Science (IISc), Bengaluru.
- **Core Track Record**: Built a C++17 RESP2 datastore reaching 83% of Redis 7.0 throughput on a 1M random keyspace, a 2,565 req/s Kafka/PostgreSQL transaction gateway, and production RAG services at IISc.

---

## 🏛️ Research Experience

### Software Engineering and Research Intern (Jul 2025 to Sep 2026)
**Indian Institute of Science (IISc), Computational Intelligence (CINT) Lab** | Bengaluru, India

- **YogaBud Modular Architecture**: Refactored the back end from a Node.js monolith into isolated modules with dedicated RAG retrieval, ONNX inference, and SSE streaming services; live in production with ~150 registered users (55 to 70 active monthly).
- **Whisper & Low-Latency RAG Pipeline**: Built a GPU-accelerated Whisper transcription pipeline on ONNX Runtime transcribing lab lectures into a 135-video RAG knowledge base, achieving BM25 retrieval at 3 ms with automatic Groq/Anthropic LLM fallback routing.
- **CINT Lab Research Platform**: Engineered the lab research portal as sole developer (React 18, Node.js, Express, MongoDB, JWT), deployed on AWS EC2 with automated CI/CD on git push; supporting 75 registered researchers (50 active monthly).
- **Data Integrity & RBAC**: Enforced zero double-bookings using unique compound database indexes and implemented granular Role-Based Access Control (RBAC) isolating public publication catalogs from internal experimental data.

---

## 📌 Featured Engineering Projects

### 1. [RedisClone](https://github.com/JAYASIMHAREDDYK/RedisClone)
*In-Memory Key-Value Datastore & Async Replication Engine in C++17*  
`C++17, Linux epoll, POSIX Sockets, TCP/IP, libFuzzer`

- **Head-to-Head vs Redis 7.0**: Reaches **83.4% SET** (766k ops/sec) and **80.1% GET** (970k ops/sec) on identical 1M-request benchmarks across a 1M random keyspace (`-r 1000000`). Sustains 2.49M SET and 2.80M GET ops/sec on single hot-key workloads.
- **Epoll Reactor**: Single-threaded edge-triggered Linux `epoll` reactor processing non-blocking TCP streams with pipelined batching and zero lock contention.
- **Progressive Dual-Table Rehashing**: Amortizes dictionary expansion incrementally across active requests ($O(1)$ per operation), bounding max resize latency jitter to under 1.2 ms.
- **Primary-Replica Streaming**: Circular ring buffer replication backlog with 64-bit continuous byte offsets, full snapshot sync (`PSYNC ? -1`), partial resync (`+CONTINUE`), and `WAIT` semi-sync durability barriers.
- **Quantified Failover Durability**: Measured write loss by injecting mid-stream `SIGKILL` into the primary: 0.0% loss on LAN, 59% to 62% under 10 ms simulated WAN delay, eliminated completely (0 of 10,000 writes lost) with `WAIT 1`.
- **Fuzzed & Sanitized**: Hardened with LLVM `libFuzzer`, ASan, and UBSan across 1.25M+ executions; found and fixed 4 edge-case vulnerabilities, backed by a committed seed corpus.

### 2. [Sluice](https://github.com/JAYASIMHAREDDYK/Sluice)
*High-Throughput Event-Driven Transaction Gateway*  
`Node.js, Fastify, Redis, Kafka, PostgreSQL, Docker`

- **Ingestion Scale**: Sustains **2,565 req/s** with p50 21.9 ms and zero errors across 102,617 requests under k6 load tests.
- **Idempotency Guarantees**: Guaranteed single application of retries with a Lua token-bucket limiter and SHA-256 idempotency keys: 10,000 concurrent duplicate requests produced exactly 1 Kafka message and 1 PostgreSQL row.
- **Fault-Tolerant Persistence**: Designed an at-least-once persistence worker with sorted row locks, offsets committed strictly after DB commits, and a dead-letter topic after 5 retries (625 tx/s).
- **Outage Verification**: Verified zero request loss during an injected 30-second PostgreSQL outage under active load; Kafka successfully buffered the backlog without dropping transactions.

### 3. [STRATOS: Spacecraft Fault Recovery](https://github.com/JAYASIMHAREDDYK/STRATOS)
*Deep Reinforcement Learning Satellite Recovery Simulator*  
`Python, PyTorch, Qwen3, LoRA, GRPO, Three.js, FastAPI`

- **POMDP Simulator**: Built a partially observable Markov decision process satellite simulator modeling thermal, power, compute, and memory states with radiation fault injection and noisy sensor diagnostics.
- **RL Fine-Tuning**: Fine-tuned Qwen3-1.7B with LoRA and GRPO: achieved **87.9% recovery** vs 79.4% for LSTM-PPO, cutting catastrophic failures from 12.4% down to 5.9% across 1,500 evaluation episodes (3 random seeds).
- **Real-Time Visualization**: Engineered a real-time 3D telemetry dashboard using Three.js and WebSockets with a FastAPI routing layer.
- **Academic Publication**: Co-authored a research paper under review for AISIGH-SD 2026 (IEEE).

### 4. [OrderMatchingEngine (OME)](https://github.com/JAYASIMHAREDDYK/OrderMatchingEngine)
*Deterministic Low-Latency Limit Order Book in Modern C++*  
`C++17, Memory Alignment, Cache-Conscious Data Structures`

- **Price-Time Execution**: Nanosecond-scale trade matching engine implementing strict price-time priority (`FIFO`) execution.
- **Zero-Allocation Hot Path**: Cache-friendly contiguous order book structures minimizing cache-line invalidation and dynamic heap allocations during high-frequency order placement, cancellation, and execution.

---

## 🛠️ Technical Stack & Tooling

<table>
  <tr>
    <td align="center" width="130"><b>Languages</b></td>
    <td>
      <img src="https://img.shields.io/badge/C++17/20-00599C?style=flat-square&logo=c%2B%2B&logoColor=white" />
      <img src="https://img.shields.io/badge/C-A8B9CC?style=flat-square&logo=c&logoColor=black" />
      <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" />
      <img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white" />
      <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black" />
      <img src="https://img.shields.io/badge/SQL-4479A1?style=flat-square&logo=postgresql&logoColor=white" />
      <img src="https://img.shields.io/badge/Bash-4EAA25?style=flat-square&logo=gnu-bash&logoColor=white" />
    </td>
  </tr>
  <tr>
    <td align="center"><b>Systems & Kernels</b></td>
    <td>
      <img src="https://img.shields.io/badge/Linux_epoll-FCC624?style=flat-square&logo=linux&logoColor=black" />
      <img src="https://img.shields.io/badge/POSIX_Sockets-333333?style=flat-square&logo=gnubash&logoColor=white" />
      <img src="https://img.shields.io/badge/Reactor_Pattern-00F0FF?style=flat-square&logo=fastapi&logoColor=black" />
      <img src="https://img.shields.io/badge/Memory_Alignment-FF6B6B?style=flat-square&logo=cplusplus&logoColor=white" />
      <img src="https://img.shields.io/badge/Copy_on_Write-4D96FF?style=flat-square&logo=linux&logoColor=white" />
    </td>
  </tr>
  <tr>
    <td align="center"><b>Distributed & Data</b></td>
    <td>
      <img src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white" />
      <img src="https://img.shields.io/badge/Apache_Kafka-231F20?style=flat-square&logo=apachekafka&logoColor=white" />
      <img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white" />
      <img src="https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white" />
      <img src="https://img.shields.io/badge/Replication_Streams-00C853?style=flat-square&logo=apache&logoColor=white" />
      <img src="https://img.shields.io/badge/WAL_Durability-7B1FA2?style=flat-square&logo=sqlite&logoColor=white" />
    </td>
  </tr>
  <tr>
    <td align="center"><b>Testing & Profiling</b></td>
    <td>
      <img src="https://img.shields.io/badge/LLVM_libFuzzer-268B07?style=flat-square&logo=llvm&logoColor=white" />
      <img src="https://img.shields.io/badge/AddressSanitizer_(ASan)-E53935?style=flat-square&logo=clang&logoColor=white" />
      <img src="https://img.shields.io/badge/UBSan-FB8C00?style=flat-square&logo=llvm&logoColor=white" />
      <img src="https://img.shields.io/badge/perf_flamegraphs-D81B60?style=flat-square&logo=linux&logoColor=white" />
      <img src="https://img.shields.io/badge/taskset_affinity-546E7A?style=flat-square&logo=gnubash&logoColor=white" />
    </td>
  </tr>
  <tr>
    <td align="center"><b>Cloud & DevOps</b></td>
    <td>
      <img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white" />
      <img src="https://img.shields.io/badge/AWS_EC2-FF9900?style=flat-square&logo=amazonec2&logoColor=white" />
      <img src="https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white" />
      <img src="https://img.shields.io/badge/CMake-064F8C?style=flat-square&logo=cmake&logoColor=white" />
      <img src="https://img.shields.io/badge/Make-000000?style=flat-square&logo=gnu&logoColor=white" />
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
