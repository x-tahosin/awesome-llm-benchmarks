# Awesome LLM Benchmarks [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated catalog of benchmarks, evaluation frameworks, and leaderboards for large language models — updated for the 2026 landscape.

LLM evaluation is a moving target. Benchmarks from 2022-2023 are saturated, contaminated, or simply no longer predictive of real-world ability. This list focuses on what practitioners and researchers are actually using in 2026, organized so you can pick the right tool for your task.

If you're building your own evaluation stack, start with **[Evaluation Frameworks](#evaluation-frameworks)**. If you're picking a model, start with **[Leaderboards](#live-leaderboards)**. If you're writing a paper, start with **[Papers on Benchmark Quality](#papers-on-benchmark-quality)**.

## Contents

- [General Capability](#general-capability)
- [Code Generation](#code-generation)
- [Software Engineering](#software-engineering)
- [Math & Reasoning](#math--reasoning)
- [Multimodal](#multimodal)
- [Long Context](#long-context)
- [Agentic & Tool Use](#agentic--tool-use)
- [Instruction Following & Chat](#instruction-following--chat)
- [Hallucination & Truthfulness](#hallucination--truthfulness)
- [Safety & Alignment](#safety--alignment)
- [Domain-specific](#domain-specific)
- [Evaluation Frameworks](#evaluation-frameworks)
- [Live Leaderboards](#live-leaderboards)
- [Contamination Detection](#contamination-detection)
- [Papers on Benchmark Quality](#papers-on-benchmark-quality)
- [How to Choose a Benchmark](#how-to-choose-a-benchmark)
- [Contributing](#contributing)

---

## General Capability

Broad multi-task benchmarks testing reasoning, knowledge, and language understanding.

- [MMLU](https://github.com/hendrycks/test) — 57-subject knowledge test. Mostly saturated in 2025-2026; useful as a floor check.
- [MMLU-Pro](https://github.com/TIGER-AI-Lab/MMLU-Pro) — Harder 10-option version of MMLU. Still discriminating.
- [MMLU-Redux](https://github.com/aryopg/mmlu-redux) — Cleaned MMLU with errors flagged and fixed.
- [BIG-Bench](https://github.com/google/BIG-bench) — 200+ tasks, designed to test capabilities beyond current models.
- [BIG-Bench Hard](https://github.com/suzgunmirac/BIG-Bench-Hard) — 23 challenging BIG-Bench tasks where models perform below average humans.
- [BIG-Bench Extra Hard (BBEH)](https://github.com/google-deepmind/bbeh) — 2025 successor focused on tasks still-hard for frontier models.
- [ARC](https://huggingface.co/datasets/allenai/ai2_arc) — AI2 Reasoning Challenge (grade-school science).
- [ARC-AGI](https://github.com/fchollet/ARC-AGI) & [ARC-AGI-2](https://arcprize.org) — François Chollet's abstraction/reasoning challenge; frontier models still below humans in 2026.
- [HellaSwag](https://github.com/rowanz/hellaswag) — Commonsense sentence completion.
- [TruthfulQA](https://github.com/sylinrl/TruthfulQA) — Questions designed to elicit false answers from language models.
- [AGIEval](https://github.com/ruixiangcui/AGIEval) — Human-centric evaluation (SAT, LSAT, GRE, Chinese Gaokao).
- [GPQA](https://github.com/idavidrein/gpqa) — Graduate-level physics/bio/chem QA; still challenging for frontier models.
- [GPQA Diamond](https://github.com/idavidrein/gpqa) — Hardest subset of GPQA, the de-facto "frontier" gate.
- [Humanity's Last Exam (HLE)](https://lastexam.ai) — Multi-disciplinary expert-level questions; intentionally uncontaminated.
- [MUSR](https://github.com/zayne-sprague/MuSR) — Multistep soft reasoning over narratives.
- [MMLU-CF](https://github.com/microsoft/MMLU-CF) — Contamination-free MMLU variant.

## Code Generation

Function-level code synthesis from docstrings/specs.

- [HumanEval](https://github.com/openai/human-eval) — OpenAI's original 164-problem function-level benchmark.
- [HumanEval+](https://github.com/evalplus/evalplus) — HumanEval with ~80× more test cases (EvalPlus).
- [MBPP](https://github.com/google-research/google-research/tree/master/mbpp) — Mostly Basic Python Problems, 974 tasks.
- [MBPP+](https://github.com/evalplus/evalplus) — Same EvalPlus treatment.
- [APPS](https://github.com/hendrycks/apps) — 10,000 competitive-programming problems.
- [CodeContests](https://github.com/google-deepmind/code_contests) — DeepMind's AlphaCode training/eval set.
- [LiveCodeBench](https://github.com/LiveCodeBench/LiveCodeBench) — Continuously-updated problems from LeetCode/AtCoder/CodeForces to reduce contamination.
- [BigCodeBench](https://github.com/bigcode-project/bigcodebench) — Library-heavy practical coding tasks (1,140 problems).
- [ClassEval](https://github.com/FudanSELab/ClassEval) — Class-level (not function-level) code generation.
- [CRUXEval](https://github.com/facebookresearch/cruxeval) — Code reasoning, understanding, and execution.
- [DS-1000](https://github.com/HKUNLP/DS-1000) — Data science code generation (pandas/numpy/sklearn).

## Software Engineering

Realistic SWE tasks — multi-file, repo-scale, long-horizon.

- [SWE-bench](https://github.com/princeton-nlp/SWE-bench) — Real GitHub issues from 12 popular Python repos.
- [SWE-bench Verified](https://openai.com/index/introducing-swe-bench-verified) — 500 human-verified problems (OpenAI); the de-facto agent gate.
- [SWE-bench Multilingual](https://www.swebench.com/multilingual.html) — SWE-bench beyond Python.
- [SWE-bench Multimodal](https://www.swebench.com/multimodal.html) — JavaScript front-end issues with screenshots.
- [SWE-Lancer](https://github.com/openai/SWELancer-Benchmark) — Real freelance-paid engineering tasks scored by money earned.
- [RepoBench](https://github.com/Leolty/repobench) — Repository-level code completion.
- [R2E / R2E-Gym](https://github.com/R2E-Gym/R2E-Gym) — Automatic SWE benchmark generation from any repo.
- [Commit0](https://github.com/commit-0/commit0) — From-scratch library implementation across 50 projects.
- [BaxBench](https://github.com/baxbench/baxbench) — Backend generation with security tests.
- [MultiSWE-bench](https://github.com/multi-swe-bench/multi-swe-bench) — Multi-language SWE-bench (Java, TS, Go, Rust, C/C++).

## Math & Reasoning

- [GSM8K](https://github.com/openai/grade-school-math) — Grade-school math word problems; saturated in 2025.
- [MATH](https://github.com/hendrycks/math) — 12,500 competition math problems.
- [AIME 2024 / 2025](https://huggingface.co/datasets/AI-MO/aimo-validation-aime) — American Invitational Mathematics Examination; top frontier models approach ceiling.
- [MathArena](https://matharena.ai) — Olympiad/contest aggregator kept fresh monthly.
- [FrontierMath](https://epoch.ai/frontiermath) — Research-level math; frontier models still below 5% in 2025.
- [OlympiadBench](https://github.com/OpenBMB/OlympiadBench) — Bilingual (CN/EN) olympiad problems, math and physics.
- [PutnamBench](https://github.com/trishullab/PutnamBench) — Formalized Putnam problems in Lean/Coq/Isabelle.
- [MiniF2F](https://github.com/openai/miniF2F) — Formal math reasoning (Lean, Metamath, Isabelle).
- [ProofNet](https://github.com/zhangir-azerbayev/ProofNet) — Autoformalization benchmark.
- [USAMO 2025](https://matharena.ai) — Tracked on MathArena; harder than AIME.
- [LiveMathBench](https://github.com/open-compass/LiveMathBench) — Continuously-refreshed math problems.
- [AoPS-Instruct](https://github.com/DSL-Lab/aops) — Art of Problem Solving high-school olympiad data.

## Multimodal

Vision + language + (audio/video) capability.

- [MMMU](https://github.com/MMMU-Benchmark/MMMU) — Massive multi-discipline multimodal understanding benchmark.
- [MMMU-Pro](https://github.com/MMMU-Benchmark/MMMU) — Harder, more vision-reliant version.
- [MMBench](https://github.com/open-compass/MMBench) — 20 ability dimensions in VQA.
- [SEED-Bench / SEED-Bench-2](https://github.com/AILab-CVC/SEED-Bench) — MLLM generation + comprehension.
- [MathVista](https://github.com/lupantech/MathVista) — Math reasoning in visual contexts.
- [ChartQA](https://github.com/vis-nlp/ChartQA) — Question answering over charts.
- [DocVQA](https://www.docvqa.org) — Document image QA.
- [OCRBench / OCRBench v2](https://github.com/Yuliang-Liu/MultimodalOCR) — OCR capability probe for MLLMs.
- [RealWorldQA](https://huggingface.co/datasets/xai-org/RealworldQA) — Real-world spatial understanding (xAI).
- [Video-MME](https://github.com/BradyFU/Video-MME) — Comprehensive video understanding.
- [MVBench](https://github.com/OpenGVLab/Ask-Anything/tree/main/video_chat2/MVBench) — 20 video tasks.
- [TempCompass](https://github.com/llyx97/TempCompass) — Temporal reasoning in videos.
- [AV-Odyssey](https://av-odyssey.github.io) — Audio-visual benchmark.

## Long Context

Specifically test ability to use long-context windows.

- [Needle in a Haystack (NIAH)](https://github.com/gkamradt/LLMTest_NeedleInAHaystack) — Classic synthetic retrieval.
- [RULER](https://github.com/NVIDIA/RULER) — 13 multi-difficulty tasks across context lengths (NVIDIA).
- [LongBench / LongBench v2](https://github.com/THUDM/LongBench) — 21 real long-context tasks.
- [L-Eval](https://github.com/OpenLMLab/LEval) — Standardized long-context eval.
- [InfiniteBench](https://github.com/OpenBMB/InfiniteBench) — 100K+ token tasks.
- [Counting Stars](https://github.com/nick7nlp/Counting-Stars) — Stress test for retrieval at depth.
- [BABILong](https://github.com/booydar/babilong) — bAbI tasks scaled to million-token context.
- [RepoQA](https://github.com/evalplus/repoqa) — Long-context code comprehension.
- [NoLiMa](https://github.com/adobe-research/NoLiMa) — Non-lexical long-context matching (lexical-overlap free).

## Agentic & Tool Use

LLMs as agents: planning, tool calling, multi-step execution.

- [AgentBench](https://github.com/THUDM/AgentBench) — Multi-domain agent evaluation (8 environments).
- [GAIA](https://huggingface.co/spaces/gaia-benchmark/leaderboard) — General AI Assistants benchmark (HuggingFace).
- [GAIA-2](https://github.com/meta-agent-2/gaia-2) — Successor with refreshed unseen tasks.
- [τ-bench / tau-bench](https://github.com/sierra-research/tau-bench) — Tool-agent-user interaction benchmark (Sierra).
- [TAU-bench](https://github.com/sierra-research/tau-bench) — User-agent dialogue benchmark.
- [WebArena](https://github.com/web-arena-x/webarena) — Realistic web environment for agents.
- [VisualWebArena](https://github.com/web-arena-x/visualwebarena) — Visual extension of WebArena.
- [Mind2Web](https://github.com/OSU-NLP-Group/Mind2Web) — Web-page navigation from natural-language tasks.
- [OSWorld](https://github.com/xlang-ai/OSWorld) — Real computer operating system tasks (Ubuntu, Windows, macOS).
- [AppWorld](https://github.com/stonybrooknlp/appworld) — Interacting with mock mobile apps.
- [AndroidWorld](https://github.com/google-research/android_world) — Real Android phone control.
- [Spider 2.0](https://github.com/xlang-ai/Spider2) — Enterprise text-to-SQL agents.
- [MINT](https://github.com/xingyaoww/mint-bench) — Multi-turn interaction with tools/feedback.
- [ToolBench](https://github.com/OpenBMB/ToolBench) — 16,000+ real APIs (ToolLLM).
- [BFCL (Berkeley Function Calling Leaderboard)](https://gorilla.cs.berkeley.edu/leaderboard.html) — Function calling live leaderboard (v2, v3 live).
- [API-Bank](https://github.com/AlibabaResearch/DAMO-ConvAI/tree/main/api-bank) — Alibaba's API-use benchmark.
- [WorkArena](https://github.com/ServiceNow/WorkArena) — ServiceNow enterprise agent tasks.
- [AgentBoard](https://github.com/hkust-nlp/AgentBoard) — Analytical agent evaluation.
- [TravelPlanner](https://github.com/OSU-NLP-Group/TravelPlanner) — Realistic multi-constraint travel planning.

## Instruction Following & Chat

- [MT-Bench](https://github.com/lm-sys/FastChat/tree/main/fastchat/llm_judge) — LMSys multi-turn chat benchmark (GPT-4 judge).
- [Arena-Hard / Arena-Hard-Auto](https://github.com/lmarena/arena-hard-auto) — Automatic proxy for Chatbot Arena scores.
- [AlpacaEval 2.0](https://github.com/tatsu-lab/alpaca_eval) — Length-controlled win rate vs GPT-4.
- [IFEval](https://github.com/google-research/google-research/tree/master/instruction_following_eval) — Verifiable instruction-following.
- [FoFo / FOFO](https://github.com/SalesforceAIResearch/FoFo) — Formal format instruction following (Salesforce).
- [WildBench](https://github.com/allenai/WildBench) — Real user prompts from WildChat (AllenAI).
- [CHATEval / MT-Bench-101](https://github.com/mtbench101/mt-bench-101) — Fine-grained multi-turn evaluation.
- [FollowBench](https://github.com/YJiangcm/FollowBench) — Multi-level fine-grained instruction following.
- [InFoBench](https://github.com/qinyiwei/InfoBench) — Decomposed instruction following.

## Hallucination & Truthfulness

- [TruthfulQA](https://github.com/sylinrl/TruthfulQA) — Questions designed to elicit false answers.
- [HalluLens](https://github.com/facebookresearch/HalluLens) — Llama team's hallucination benchmark (2025).
- [FActScore](https://github.com/shmsw25/FActScore) — Fine-grained atomic fact scoring.
- [SimpleQA](https://github.com/openai/simple-evals) — Short-form factuality (OpenAI).
- [FreshQA](https://github.com/freshllms/freshqa) — Questions whose answers change over time.
- [HalluQA](https://github.com/OpenMOSS/HalluQA) — Chinese hallucination benchmark.
- [HaluEval](https://github.com/RUCAIBox/HaluEval) — Dialogue-level hallucination evaluation.
- [XSum Faithfulness](https://github.com/google-research/google-research/tree/master/confidence_scoring_for_summarization) — Summarization faithfulness.
- [FACTOR](https://github.com/AI21Labs/factor) — Factuality via controlled perturbations.

## Safety & Alignment

- [HarmBench](https://github.com/centerforaisafety/HarmBench) — Automated red-teaming (Center for AI Safety).
- [AIR-Bench](https://github.com/stanford-crfm/air-bench-2024) — AI Risks benchmark tied to real regulations.
- [XSTest](https://github.com/paul-rottger/xstest) — Over-refusal tests (should answer but model refuses).
- [SALAD-Bench](https://github.com/OpenSafetyLab/SALAD-BENCH) — Hierarchical safety benchmark.
- [ToxicChat](https://github.com/lmsys/toxicchat) — Toxicity detection in real user queries.
- [Do Anything Now (DAN) Prompts](https://github.com/verazuo/jailbreak_llms) — Jailbreak dataset (Zou et al.).
- [AdvBench](https://github.com/llm-attacks/llm-attacks) — Adversarial prompt benchmark.
- [JailbreakBench](https://github.com/JailbreakBench/jailbreakbench) — Standardized jailbreak evaluation.
- [Anthropic's Evals](https://github.com/anthropics/evals) — Persona, sycophancy, bias evaluations.

## Domain-specific

### Medical
- [MedQA](https://github.com/jind11/MedQA) — USMLE-style medical QA.
- [MedMCQA](https://medmcqa.github.io) — Indian medical entrance exams.
- [PubMedQA](https://github.com/pubmedqa/pubmedqa) — Biomedical research QA.
- [HealthBench](https://github.com/openai/simple-evals) — OpenAI real-world health conversations.

### Legal
- [LegalBench](https://hazyresearch.stanford.edu/legalbench) — 162 legal reasoning tasks (Stanford).
- [LexGLUE](https://github.com/coastalcph/lex-glue) — Legal language understanding.
- [LawBench](https://github.com/open-compass/LawBench) — Chinese legal benchmark.

### Finance
- [FinBench](https://github.com/yzlnew/FinBench) — Financial reasoning.
- [FinQA](https://github.com/czyssrs/FinQA) — Numerical reasoning over financial reports.
- [PIXIU](https://github.com/The-FinAI/PIXIU) — Financial LLM eval suite.

### Scientific
- [SciQ](https://allenai.org/data/sciq) — Science QA.
- [ScienceQA](https://github.com/lupantech/ScienceQA) — Multimodal science QA.
- [LAB-Bench](https://github.com/Future-House/LAB-Bench) — Biology research agent benchmark.
- [ChemBench](https://github.com/lamalab-org/chembench) — Chemistry benchmark.

## Evaluation Frameworks

Tools for running benchmarks, tracking results, and building custom evals.

- [lm-evaluation-harness](https://github.com/EleutherAI/lm-evaluation-harness) — EleutherAI's standard harness; most-used in research.
- [HELM](https://github.com/stanford-crfm/helm) — Stanford's Holistic Evaluation of Language Models.
- [OpenAI Evals](https://github.com/openai/evals) — OpenAI's evaluation framework.
- [Inspect AI](https://github.com/UKGovernmentBEIS/inspect_ai) — UK AI Safety Institute's framework (2024-2026 rising standard).
- [Promptfoo](https://github.com/promptfoo/promptfoo) — CLI/lib for LLM testing with rich assertions.
- [DeepEval](https://github.com/confident-ai/deepeval) — Unit-test style LLM evals.
- [Evalchemy](https://github.com/mlfoundations/Evalchemy) — Reproducible evaluation of post-trained LLMs.
- [OpenCompass](https://github.com/open-compass/opencompass) — Shanghai AI Lab comprehensive eval platform.
- [CLEVA](https://github.com/LaVi-Lab/CLEVA) — Chinese LLM evaluation.
- [Langfuse](https://github.com/langfuse/langfuse) — Observability + evals for LLM apps.
- [LangSmith](https://smith.langchain.com) — LangChain's hosted tracing + evals.
- [Ragas](https://github.com/explodinggradients/ragas) — RAG-specific evaluation metrics.
- [TruLens](https://github.com/truera/trulens) — App-level evaluation with feedback functions.
- [Giskard](https://github.com/Giskard-AI/giskard) — ML/LLM testing with pytest-style interface.
- [LightEval](https://github.com/huggingface/lighteval) — HuggingFace's lightweight eval harness.
- [vLLM's benchmark_serving](https://github.com/vllm-project/vllm) — Throughput / latency benchmarking.

## Live Leaderboards

Continuously updated rankings.
- [ModelBenchmark](https://modelbenchmark.io) — Composite ranking of 202 models from 16 public benchmarks, with prices and context windows for 2,406 models.

- [LMSys Chatbot Arena](https://chat.lmsys.org) / [Lmarena.ai](https://lmarena.ai) — Blind human-preference ranking; the gold standard for chat models.
- [Open LLM Leaderboard v2](https://huggingface.co/spaces/open-llm-leaderboard/open_llm_leaderboard) — HuggingFace (IFEval, BBH, MATH, GPQA, MuSR, MMLU-Pro).
- [LiveBench.ai](https://livebench.ai) — Monthly-refreshed questions to avoid contamination.
- [Vellum LLM Leaderboard](https://www.vellum.ai/llm-leaderboard) — Production-oriented comparison.
- [Aider Polyglot](https://aider.chat/docs/leaderboards) — Code-editing benchmark leaderboard.
- [SEAL Leaderboards](https://scale.com/leaderboard) — Scale's private evals (contamination-resistant).
- [SWE-bench Leaderboard](https://www.swebench.com) — Official SWE-bench / Verified / Multimodal rankings.
- [OpenRouter Rankings](https://openrouter.ai/rankings) — Usage-based rankings across providers.
- [Artificial Analysis](https://artificialanalysis.ai) — Cross-provider latency/price/quality tradeoffs.
- [BFCL Leaderboard](https://gorilla.cs.berkeley.edu/leaderboard.html) — Berkeley function-calling leaderboard.
- [GAIA Leaderboard](https://huggingface.co/spaces/gaia-benchmark/leaderboard) — General AI Assistant performance.
- [Open Medical LLM Leaderboard](https://huggingface.co/spaces/openlifescienceai/open_medical_llm_leaderboard) — Medical-domain rankings.

## Contamination Detection

Testing whether a model has memorized benchmark data.

- [Platypus Eval / Contamination Tests](https://github.com/arcee-ai/PlatypusEval) — Contamination diagnostics.
- [LLM Decontaminator](https://github.com/lm-sys/llm-decontaminator) — LMSys tool for removing rephrased test items from training data.
- [Benchmark Data Contamination paper (CMU)](https://arxiv.org/abs/2310.17623) — Foundational analysis.
- [BenBench](https://github.com/ruixiangcui/BenBench) — Benchmarking memorization of benchmarks.
- [TS-Guessing](https://arxiv.org/abs/2311.09783) — Test Set Guessing for contamination estimation.

## Papers on Benchmark Quality

Required reading if you design or interpret evaluations.

- [*Chatbot Arena: An Open Platform for Evaluating LLMs by Human Preference*](https://arxiv.org/abs/2403.04132) (Chiang et al., 2024).
- [*AI and the Everything in the Whole Wide World Benchmark*](https://arxiv.org/abs/2111.15366) (Raji et al., 2021) — Why benchmarks over-generalize.
- [*BIG-bench: Beyond the Imitation Game*](https://arxiv.org/abs/2206.04615) (Srivastava et al., 2023).
- [*Benchmarking Benchmark Leakage in Large Language Models*](https://arxiv.org/abs/2404.18824) (Xu et al., 2024).
- [*The Curious Case of Benchmark Contamination*](https://arxiv.org/abs/2310.17623) (Golchin & Surdeanu, 2023).
- [*Leakage and the Reproducibility Crisis in ML-based Science*](https://arxiv.org/abs/2207.07048) (Kapoor & Narayanan, 2022).
- [*Elephants Never Forget: Memorization and Learning of Tabular Data in LLMs*](https://arxiv.org/abs/2404.06209) (Bordt et al., 2024).
- [*Are Emergent Abilities of Large Language Models a Mirage?*](https://arxiv.org/abs/2304.15004) (Schaeffer et al., 2023).
- [*Can LLMs Really Reason?* — Apple GSM-Symbolic paper](https://arxiv.org/abs/2410.05229) (Mirzadeh et al., 2024).
- [*GPQA: A Graduate-Level Google-Proof Q&A Benchmark*](https://arxiv.org/abs/2311.12022) (Rein et al., 2023).

## How to Choose a Benchmark

A pragmatic flowchart:

1. **Are you shipping a product?**
   → Use [LMSys Chatbot Arena](https://chat.lmsys.org), [LiveBench.ai](https://livebench.ai), or your own [Promptfoo](https://github.com/promptfoo/promptfoo) suite with real user traffic.

2. **Are you training a base model?**
   → [lm-evaluation-harness](https://github.com/EleutherAI/lm-evaluation-harness) on MMLU-Pro, BBH, GPQA, MATH, HumanEval+, GSM8K — these are the "holy grail" academic reference set in 2026.

3. **Are you training an agent?**
   → SWE-bench Verified, τ-bench, GAIA, BFCL. Skip anything pre-2024; models are saturated.

4. **Are you evaluating long context?**
   → RULER first (it's the most discriminating), then NoLiMa (lexical-leak-free), then real tasks from LongBench v2.

5. **Are you writing a paper?**
   → Include at least one *contamination-resistant* benchmark (LiveBench, LiveCodeBench, MathArena), one *held-out human-evaluated* benchmark (Arena-Hard-Auto), and one *domain-specific* benchmark relevant to your claim.

6. **Do you care about cost/latency?**
   → [Artificial Analysis](https://artificialanalysis.ai) has the best cross-provider data.

## Related Projects

Similar awesome-lists worth cross-referencing:

- [awesome-llm](https://github.com/Hannibal046/Awesome-LLM) — General LLM awesome-list.
- [awesome-llm-inference](https://github.com/DefTruth/Awesome-LLM-Inference) — Inference optimization.
- [Awesome-Code-LLM](https://github.com/huybery/Awesome-Code-LLM) — Code LLM focus.
- [Awesome-Multimodal-Large-Language-Models](https://github.com/BradyFU/Awesome-Multimodal-Large-Language-Models) — MLLM focus.

And a companion project from this author:

- [**gemini-bench-2026**](https://github.com/x-tahosin/gemini-bench-2026) — Reproducible Gemini benchmarking harness built on many of the above evaluation frameworks.

## Contributing

Contributions are warmly welcome. Please read [CONTRIBUTING.md](CONTRIBUTING.md) and open a PR.

**Criteria for inclusion:**

1. The benchmark, framework, or leaderboard must be **publicly documented** (GitHub repo, paper, or hosted leaderboard).
2. It must be **actively maintained** or a widely-cited reference point.
3. Prefer **contamination-resistant** / **continuously-updated** benchmarks over static saturated ones.
4. Each entry must include a **one-line description** of what makes it worth attention.

## License

[![CC0](https://mirrors.creativecommons.org/presskit/buttons/88x31/svg/cc-zero.svg)](https://creativecommons.org/publicdomain/zero/1.0/)

To the extent possible under law, the authors have waived all copyright and related or neighboring rights to this work.
