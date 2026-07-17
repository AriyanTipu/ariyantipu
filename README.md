<div align="center">

# Hi, I'm Ariyan Tipu 👋

**Machine Learning Engineer | MSc Data Science @ King's College London | Building ML systems**

[![Email](https://img.shields.io/badge/Email-ariyantipu39%40gmail.com-D14836?style=flat&logo=gmail&logoColor=white)](mailto:ariyantipu39@gmail.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-ariyantipu-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/ariyantipu/)
![Location](https://img.shields.io/badge/Location-London%2C%20UK-444444?style=flat&logo=googlemaps&logoColor=white)

</div>

---

### 👨‍💻 About me

I'm a Mathematics graduate moving into **Machine Learning Engineering**. My focus is on building reliable, maintainable and scalable ML systems: not just training models, but the data infrastructure, API deployment and software engineering practices that let them run in production.

I'm currently preparing for an MSc in Data Science at **King's College London** (starting September 2026).

---

### 🚀 Featured Projects

Three public, actively maintained repositories. Each one ships with CI, tests and a written design rationale rather than just a notebook.

#### [realtime-orders-platform](https://github.com/AriyanTipu/realtime-orders-platform)

*Real-time order and inventory operations platform for e-commerce, built around the two problems toy CRUD tutorials skip: safe concurrency and live updates without polling.*

![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)
![Django](https://img.shields.io/badge/Django-092E20?logo=django&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?logo=fastapi&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?logo=postgresql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?logo=redis&logoColor=white)
![C++](https://img.shields.io/badge/C%2B%2B17-00599C?logo=cplusplus&logoColor=white)
![Vue.js](https://img.shields.io/badge/Vue_3-4FC08D?logo=vuedotjs&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?logo=typescript&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?logo=docker&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?logo=githubactions&logoColor=white)

- Made overselling impossible by construction: every stock change goes through row-level locks (`SELECT ... FOR UPDATE`) taken in a fixed, deadlock-free order, proven with a test that fires eight genuinely concurrent buy requests against five units of stock.
- Built a FastAPI WebSocket gateway that streams order and stock updates to a Vue 3 dashboard via PostgreSQL `LISTEN`/`NOTIFY`, so an event can never be broadcast for a transaction that later rolled back.
- Wrote a warehouse pick-path optimiser twice on purpose: a pure Python reference implementation and a C++17 engine (via pybind11), with 150 randomised tests proving they always agree; the C++ version is up to 117.6x faster on larger orders.
- Took a "top sellers per warehouse" query from 104.98 ms to 4.08 ms (25.7x faster) with a partial covering index, documented end to end with real query plans.
- Full CI/CD pipeline across four languages: linting, testing and building Django, FastAPI, C++ and Vue/TypeScript on every push, with production images published to GitHub Container Registry.

#### [opening-theory-engine](https://github.com/AriyanTipu/opening-theory-engine)

*A small fine-tuned language model that explains chess opening moves, where every stage of training and serving is checked against Stockfish ground truth rather than anyone's opinion.*

![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?logo=pytorch&logoColor=white)
![Hugging Face](https://img.shields.io/badge/Transformers-FFD21E?logo=huggingface&logoColor=black)
![JAX](https://img.shields.io/badge/JAX-white?logo=jax&logoColor=black&color=lightgrey)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?logo=fastapi&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?logo=docker&logoColor=white)
![Stockfish](https://img.shields.io/badge/Stockfish-white?color=555555)

- Fine-tuned Qwen2.5-3B-Instruct with QLoRA, then aligned it with Direct Preference Optimisation (DPO), where the preference pairs come from objective engine evidence rather than human labels: a deterministic parser checks every factual claim in a candidate explanation against Stockfish's actual evaluation and principal variation.
- Wrote a custom JAX (`jit`/`vmap`) batch scorer to run that verification at scale across sampled candidates.
- Served the model behind FastAPI with an explain-verify-regenerate loop: every response ships with its own verification report, and a failed check triggers one automatic regeneration before the best attempt is returned.
- Backed the whole pipeline with 82 tests, and CI runs the entire flow end to end in miniature (real Stockfish engine, a tiny model, every stage) on every push.

#### [olist-customer-retention](https://github.com/AriyanTipu/olist-customer-retention)

*Churn modelling, survival analysis and A/B test design on 99,441 real e-commerce orders, with an emphasis on statistical honesty over flattering numbers.*

![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)
![Apache Spark](https://img.shields.io/badge/PySpark-E25A1C?logo=apachespark&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?logo=scikitlearn&logoColor=white)
![R](https://img.shields.io/badge/R-276DC3?logo=r&logoColor=white)
![MATLAB](https://img.shields.io/badge/MATLAB-0076A8?color=0076A8)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?logo=fastapi&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?logo=docker&logoColor=white)

- Built a PySpark pipeline across nine relational tables from the Olist Brazilian e-commerce dataset, comparing logistic regression against gradient boosting for repeat-purchase prediction under a 0.975% base rate, with the model selection rule (cross-validated average precision) pre-registered before looking at the holdout set.
- Ran a full survival analysis in R (Kaplan-Meier, Cox, Weibull AFT) on 93,350 purchase spells, then independently cross-checked the key fit in MATLAB/Octave by re-deriving the maximum likelihood estimate from first principles, agreeing with R to within 2e-07.
- Designed and power-analysed an A/B test, showing that detecting a realistic +15% uplift in the repeat-purchase rate would require 76,101 customers per arm, more than a quarter's entire customer intake, and wrote up the honest trade-offs involved.
- Shipped the trained model behind a FastAPI scoring service in Docker, with the identical pipeline documented as ready to move onto Databricks and S3 at production scale.

---

### 💼 Professional Experience

- **Technology Intern @ Bright Network:** Refactored ML pipelines, found architectural bottlenecks and delivered a 10% efficiency gain.
- **Lead Tutor:** Redesigned the curriculum for A-Level Further Mathematics and mentored students, improving outcomes by 20%.

---

### 🛠 Tech Stack

**Languages**

![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?logo=postgresql&logoColor=white)
![R](https://img.shields.io/badge/R-276DC3?logo=r&logoColor=white)
![MATLAB](https://img.shields.io/badge/MATLAB-0076A8?color=0076A8)
![C++](https://img.shields.io/badge/C%2B%2B-00599C?logo=cplusplus&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?logo=typescript&logoColor=white)

**ML & Data**

![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?logo=pytorch&logoColor=white)
![Hugging Face](https://img.shields.io/badge/Transformers-FFD21E?logo=huggingface&logoColor=black)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?logo=scikitlearn&logoColor=white)
![Apache Spark](https://img.shields.io/badge/PySpark-E25A1C?logo=apachespark&logoColor=white)
![JAX](https://img.shields.io/badge/JAX-white?logo=jax&logoColor=black&color=lightgrey)
![Pandas](https://img.shields.io/badge/Pandas-150458?logo=pandas&logoColor=white)

**Engineering & Backend**

![Django](https://img.shields.io/badge/Django-092E20?logo=django&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?logo=fastapi&logoColor=white)
![Vue.js](https://img.shields.io/badge/Vue_3-4FC08D?logo=vuedotjs&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?logo=docker&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?logo=git&logoColor=white)
![Pytest](https://img.shields.io/badge/PyTest-0A9EDC?logo=pytest&logoColor=white)

**Cloud & DevOps**

![AWS](https://img.shields.io/badge/AWS-232F3E?logo=amazonaws&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?logo=postgresql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?logo=redis&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?logo=githubactions&logoColor=white)

---

### 📬 Let's Connect

- **Email:** [ariyantipu39@gmail.com](mailto:ariyantipu39@gmail.com)
- **LinkedIn:** [linkedin.com/in/ariyantipu](https://www.linkedin.com/in/ariyantipu/)
- **Location:** London, UK

*Always open to opportunities in ML infrastructure or backend engineering.*
