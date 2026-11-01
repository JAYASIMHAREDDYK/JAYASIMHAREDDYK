<h1 align="center">Jayasimha Reddy K</h1>

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=19&pause=1000&color=00F0FF&center=true&vCenter=true&width=650&lines=Low-Latency+Systems+%26+Backend+Engineer;C%2B%2B17+Epoll+Reactors+%7C+Distributed+Storage;Ex-Research+Intern+%40+IISc+Bangalore;Building+High-Throughput%2C+Deterministic+Software" alt="Typing SVG" />
</p>

<p align="center">
  <a href="https://github.com/JAYASIMHAREDDYK"><img src="https://img.shields.io/badge/GitHub-JAYASIMHAREDDYK-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub" /></a>
  <a href="https://linkedin.com"><img src="https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" /></a>
  <a href="mailto:[EMAIL_ADDRESS]"><img src="https://img.shields.io/badge/Email-Contact%20Me-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email" /></a>
  <img src="https://img.shields.io/badge/Location-Bangalore%2C%20India-blue?style=for-the-badge&logo=google-maps&logoColor=white" alt="Location" />
</p>

<p align="center">
  <img src="https://skillicons.dev/icons?i=cpp,c,python,js,ts,nodejs,postgres,kafka,redis,docker,linux,git,bash,cmake" alt="Tech Stack Icons" />
</p>

---

## About Me

I write low-latency systems and distributed backends in modern C++ and Node.js. Most of my work focuses on single-threaded event loops, non-blocking network I/O, deterministic data structures, and replication backlogs that stay consistent under crash failures.

- **Computer Science Undergraduate**: MVJ College of Engineering, Bangalore (Class of 2027).
- **Core Focus**: High-throughput storage engines, progressive rehashing, cache line optimization, and crash-resilient replication protocols.
- **Engineering Philosophy**: Measure with hardware counters and flame graphs. Fuzz network parsers with address sanitizers. Do not guess bottlenecks.

---

## Research Internship: Indian Institute of Science (IISc), Bengaluru

**Role**: SDE & Research Project Intern  
**Laboratory**: Computational Intelligence Lab (CINT Lab, AE129), Department of Aerospace Engineering  
**Principal Investigator**: Dr. S. N. Omkar  

- Engineered the lab research platform, structuring authenticated access to flight benchmarks and publication datasets with fine-grained Role-Based Access Control (RBAC).
- Built low-latency routing layers and FastAPI streaming middleware with Server-Sent Events (SSE) for real-time model telemetry.
- Automated data ingestion pipelines, cutting manual benchmark processing overhead and establishing reproducible experiment workflows across research groups.

---

## 📌 Featured Systems Projects

### 1. [RedisClone](https://github.com/JAYASIMHAREDDYK/RedisClone)
*In-Memory Key-Value Datastore & Async Replication Engine in C++17*

- **Head-to-Head vs Redis 7.0**: Reaches **83.4% SET** (766k ops/sec) and **80.1% GET** (970k ops/sec) on identical 1M-request benchmarks across a 1M random keyspace (`-r 1000000`). Reaches 2.49M SET and 2.80M GET ops/sec on single hot-key workloads.
- **Epoll Reactor**: Single-threaded edge-triggered Linux `epoll` reactor processing non-blocking TCP streams with pipelined batching and zero lock contention.
- **Progressive Dual-Table Rehashing**: Amortizes dictionary expansion incrementally across active requests ($O(1)$ per operation), bounding max resize latency jitter to under 1.2 ms.
- **Primary-Replica Streaming**: Circular ring buffer replication backlog with 64-bit continuous byte offsets, full snapshot sync (`PSYNC ? -1`), partial resync (`+CONTINUE`), and `WAIT` semi-sync durability barriers.
- **Quantified Failover Durability**: Measured write loss by injecting mid-stream `SIGKILL` into the primary: 0.0% loss on LAN, 59% to 62% under 10 ms simulated WAN delay, eliminated completely (0 of 10,000 writes lost) with `WAIT 1`.
- **Fuzzed & Sanitized**: Hardened with LLVM `libFuzzer`, ASan, and UBSan across 1.25M+ executions, identifying and fixing 4 edge-case vulnerabilities before production.

### 2. [Sluice](https://github.com/JAYASIMHAREDDYK/Sluice)
*High-Throughput Event-Driven Transaction Gateway (Fastify, Kafka, Redis, PostgreSQL)*

- **Atomic Rate Limiting**: Token-bucket algorithm implemented directly via atomic Redis Lua scripts for sub-millisecond throttle enforcement.
- **Distributed Idempotency Guard**: 30-second in-flight lease locking with SHA-256 payload hashing to prevent double-processing of financial events.
- **Decoupled Pipeline**: High-throughput Kafka producer (`acks: -1`) decoupling ingress from asynchronous PostgreSQL batch persistence workers with Dead-Letter-Queue (DLQ) retry routing.

### 3. [OrderMatchingEngine (OME)](https://github.com/JAYASIMHAREDDYK/OrderMatchingEngine)
*Deterministic Low-Latency Limit Order Book in Modern C++*

- **Nanosecond-Scale Execution**: Price-time priority (`FIFO`) trade matching engine designed for deterministic latency.
- **Cache-Conscious Memory Layout**: Contiguous order book structures minimizing cache-line misses and dynamic heap allocations during high-frequency order placement, cancellation, and execution.

### 4. [PolyCache](https://github.com/JAYASIMHAREDDYK/PolyCache)
*Multi-Tiered In-Memory Caching Subsystem*

- **Pluggable Eviction**: Supports $O(1)$ LFU frequency doubly-linked buckets, sampled LRU, and FIFO policies.
- **Dual-Layer Invalidation**: Active TTL expiration combined with proactive touch tracking for read-heavy microservice environments.

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
    <td align="center"><b>Distributed Systems</b></td>
    <td>
      <img src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white" />
      <img src="https://img.shields.io/badge/Apache_Kafka-231F20?style=flat-square&logo=apachekafka&logoColor=white" />
      <img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white" />
      <img src="https://img.shields.io/badge/Replication_Streams-00C853?style=flat-square&logo=apache&logoColor=white" />
      <img src="https://img.shields.io/badge/WAL_Durability-7B1FA2?style=flat-square&logo=sqlite&logoColor=white" />
    </td>
  </tr>
  <tr>
    <td align="center"><b>Sanitizers & Profiling</b></td>
    <td>
      <img src="https://img.shields.io/badge/LLVM_libFuzzer-268B07?style=flat-square&logo=llvm&logoColor=white" />
      <img src="https://img.shields.io/badge/AddressSanitizer_(ASan)-E53935?style=flat-square&logo=clang&logoColor=white" />
      <img src="https://img.shields.io/badge/UBSan-FB8C00?style=flat-square&logo=llvm&logoColor=white" />
      <img src="https://img.shields.io/badge/perf_flamegraphs-D81B60?style=flat-square&logo=linux&logoColor=white" />
      <img src="https://img.shields.io/badge/taskset_affinity-546E7A?style=flat-square&logo=gnubash&logoColor=white" />
    </td>
  </tr>
  <tr>
    <td align="center"><b>DevOps & Build</b></td>
    <td>
      <img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white" />
      <img src="https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white" />
      <img src="https://img.shields.io/badge/CMake-064F8C?style=flat-square&logo=cmake&logoColor=white" />
      <img src="https://img.shields.io/badge/Make-000000?style=flat-square&logo=gnu&logoColor=white" />
      <img src="https://img.shields.io/badge/Debian/Ubuntu-E95420?style=flat-square&logo=ubuntu&logoColor=white" />
    </td>
  </tr>
</table>

---

## 📈 Activity & Stats

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=JAYASIMHAREDDYK&show_icons=true&theme=tokyonight&hide_border=true&bg_color=0d1117&title_color=00f0ff&icon_color=00f0ff&text_color=c0caf5" alt="GitHub Stats" height="165" />
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=JAYASIMHAREDDYK&layout=compact&theme=tokyonight&hide_border=true&bg_color=0d1117&title_color=00f0ff&text_color=c0caf5" alt="Top Languages" height="165" />
</p>

<p align="center">
  <img src="https://github-readme-streak-stats.herokuapp.com/?user=JAYASIMHAREDDYK&theme=tokyonight&hide_border=true&background=0d1117&ring=00f0ff&fire=00f0ff&currStreakLabel=00f0ff&sideLabels=c0caf5&dates=7aa2f7" alt="GitHub Streak" />
</p>
