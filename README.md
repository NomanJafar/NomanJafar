# Noman Jafar

**Founder & Lead Engineer at [ProveMVP](https://provemvp.com)** · Lahore, Pakistan

I turn startup ideas into working products. At ProveMVP we put a real product in front of real users in 14 days, then hand the founder a written keep, change, or stop. On the side, I go deep on how LLMs are served in production.

[provemvp.com](https://provemvp.com) · [info@provemvp.com](mailto:info@provemvp.com) · [LinkedIn](https://www.linkedin.com/in/noman-jafar/)

---

## What I ship

**[2-Week MVP](https://provemvp.com/services/two-week-mvp)**: one flow, a live URL, first users, and a decision by day 14. Code lives in the client's GitHub from the first commit. [Pricing](https://provemvp.com/pricing) is on the site.

Recent work (case studies on provemvp.com):

| Product | What it is | Stack |
|---|---|---|
| [Checkout Guard](https://provemvp.com/work/checkout-guard) | Shopify app that blocks bad orders at checkout without code. Spec to production in 8 days, ~100 tests. | React Router, Shopify Functions (WASM), Prisma, Postgres |
| [Family Handbook](https://provemvp.com/work/family-handbook) | Platform for families to write their values into a printed handbook, with chat, calling, and payments | Django REST, React, Stripe, Celery |
| [Kharcha](https://provemvp.com/work/kharcha) | Offline-first expense tracker in English and Urdu | Expo, React Native, SQLite, Node |
| [Emma Vault](https://provemvp.com/work/emma-vault) | Website and subscription flow for an encrypted on-device vault | React, Stripe, Firebase |
| [Elysium](https://provemvp.com/work/elysium) | Multi-store commerce backend and admin panel | Fastify, TypeScript, Postgres, Neo4j, Auth0 |

**Stack I reach for:** TypeScript, Next.js, React Native / Expo, NestJS, Node, .NET, Python / Django, PostgreSQL, Docker, AWS, Shopify.

---

## Deep dive: LLM inference infrastructure

A [portfolio of hands-on projects](https://github.com/NomanJafar/inference-infra-portfolio) on serving models, measuring them honestly, and making them faster and cheaper, all on free-tier T4 GPUs. Measured so far:

| Project | Headline result |
|---|---|
| [servellm](https://github.com/NomanJafar/servellm) | Continuous batching on vLLM took aggregate throughput from 67 to 1,637 tok/s at 64 users (24x) while per-user ITL rose only 14.7 → 36.8 ms |
| [tokenbench](https://github.com/NomanJafar/tokenbench) | Load-testing harness: found the saturation point where the server generated *more* tokens but goodput halved and only 29% of requests met SLO |
| [kvcalc](https://github.com/NomanJafar/kvcalc) | Predicted KV cache capacity within 1.7% of vLLM's reported 340k tokens; prefix caching cut cache use from 24% to 5.4% |
| [quantlab](https://github.com/NomanJafar/quantlab) | INT8 and INT4 cut single-stream latency 2.4x and 3.2x; INT8 lossless, 4-bit costs 8–15 GSM8K points |
| [specdec](https://github.com/NomanJafar/specdec) | Speculative decoding: k=1 gave +30% throughput at 4 users; k=5 was a net loss everywhere |
| [fusedkernels](https://github.com/NomanJafar/fusedkernels) | Hand-written Triton softmax beat `torch.softmax` by up to 35% (240 vs 178 GB/s) |

Every repo has a concept primer, CPU-runnable tests, the GPU notebooks that produced the numbers, and the runs that disproved the hypothesis.

---

Have an idea you need to prove? [Book a 20-minute call](https://provemvp.com/#contact) or email [info@provemvp.com](mailto:info@provemvp.com).
