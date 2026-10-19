# AI Agent Workshop for RPI 5 — Verified Reference

| | |
|---|---|
| Product code | `V-AI-AGT-RPI` [PP] |
| Family | Workshops and services |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review: live product page re-read in full (browser). Kit specs and packing list now itemised (AgentBox Starter Kit + Cytron Workshop Certificate); "no Linux or AI experience required". Service — product page + course outline are the main source (KB rule 7, workshops and services) |
| Primary source | **No datasheet exists (this is a service).** Highest source is the Cytron course outline: "AgentBox Course Outline.docx" (Google Drive, no version or date printed in the document) [UM]; product page https://my.cytron.io/p-ai-agent-workshop-for-rpi-5 [PP] |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.


## What it is
A two-day, hands-on training workshop (programme title in the outline: "AgentBox AI Agent Workshop") that teaches participants to build AI agents using AgentBox, a Raspberry Pi 5-powered local AI agent hub [UM][PP]. The product sold on my.cytron.io is "Kit + 2 Day Training at HQ": the AgentBox kit plus a seat in a two-day class at Cytron HQ on a chosen date [PP]. Participants set up AgentBox, learn AI agent and LLM concepts, connect to cloud LLMs through OpenRouter or to locally hosted models through an Ollama server, and design, build, test and deploy their own task-oriented AI agent that can be customised further after the workshop [UM]. No prior AI development experience is required [UM].

## Specifications
Service / logistics table. The kit is itemised in the page's Specifications and Packing List [PP].

| Item | Value | Src |
|---|---|---|
| Programme title | AgentBox AI Agent Workshop | [UM] |
| Product name on store | AI Agent Workshop for RPI 5 | [PP] |
| Product code | V-AI-AGT-RPI | [PP] |
| Format | Hands-on workshop; instructor-led presentations, live demonstrations, guided hands-on activities, individual practical activities, real-world use case demonstrations, project-based learning, interactive Q&A | [UM] |
| Duration | 2 days | [UM][PP] |
| Venue | Cytron HQ ("Training at HQ") | [PP] |
| Dates offered (as of 2026-10-19) | 10 & 11 Sep 2026; 15 & 16 Oct 2026; 19 & 20 Nov 2026 | [PP] |
| Option(s) | "Kit + 2 Day Training at HQ" with the date as the variant | [PP] |
| Price | RM1,930.50–RM3,861.00 (a 50% offer was shown on the page) | [PP] |
| Availability | 10 | [PP] |
| Warranty shown | 12 months | [PP] |
| Platform taught | AgentBox: Raspberry Pi 5-powered local AI agent hub; browser-based visual workflow builder that connects inputs, LLMs, knowledge bases, tools and outputs | [PP][UM] |
| Model providers covered | Cloud models via OpenRouter; local models via an Ollama server | [UM][PP] |
| Prerequisites | No prior AI development experience required [UM]; page: no Linux or AI experience required [PP] | [UM][PP] |
| Target participants | IT professionals; software developers; AI and machine learning enthusiasts; makers and Raspberry Pi users; technical educators and trainers; university students (Computer Science, Engineering, IT) | [UM] |
| Audience wording on page | Beginners, makers, developers, educators | [PP] |
| Participant limit | Not stated in any source read | — |
| Certificate | 1 × Cytron Workshop Certificate (in the packing list) | [PP] |
| Refund / cancellation terms | Not stated in any source read | — |
| Packing list | 1 × AgentBox Starter Kit — Raspberry Pi 5 8GB; 256GB NVMe 2242 MakerDisk preloaded with AgentBox OS; Argon NEO 5 case with M.2 base; 27W USB-C PD (5V/5A) power supply, UK plug — plus 1 × Cytron Workshop Certificate | [PP] |
| Food / materials included | Not stated in any source read | — |

## Interfaces, terminals and pin mapping
Not applicable (service). Relevant software facts: AgentBox is browser-based with a visual workflow builder [PP]; it connects to AI model providers through OpenRouter (cloud) or a local Ollama server [UM][PP].

## Rules and gotchas (for code, wiring and tutorials)
- Always name the platform exactly "AgentBox" and the host "Raspberry Pi 5" [UM][PP]. Do not describe AgentBox as a cloud service: it is a local agent hub running on the Pi 5 that can *connect* to cloud models through OpenRouter [UM][PP].
- The two LLM routes taught are OpenRouter (cloud-hosted models) and Ollama (locally hosted models); the outline covers "Cloud vs Local AI Models" and "Performance and Cost Considerations" as explicit topics [UM].
- The workshop is 2 days, not 1 [UM][PP]. The sibling Jetson and Raspbot workshops are 1 day; do not mix them up.
- The dates are the purchase variants: a buyer picks one date pair at checkout [PP]. Quote dates only with "as of 2026-10-19" and check the page, because two of the three listed dates have already passed.
- The course outline carries no version or date; cite it as "AgentBox Course Outline" without a revision number.
- Module and submodule names should be quoted from the outline (below), not paraphrased into different module counts.

**Course outline (4 modules, 8 submodules)** [UM]:
- Module 1 – Introduction to AI Agents and AgentBox. 1.1: Introduction to Generative AI; Understanding Large Language Models (LLMs); Cloud vs Local AI Models; AI Agent Fundamentals; Common AI Agent Use Cases. 1.2: Introduction to AgentBox; AgentBox Hardware Overview; System Architecture; AgentBox Interface Tour; Connecting to AI Model Providers.
- Module 2 – Configuring AgentBox. 2.1: Initial System Configuration; Connecting to OpenRouter; Connecting to a Local Ollama Server; Managing AI Models; Understanding Model Selection. 2.2: Creating Your First AI Agent; Agent Settings; Prompt Engineering Fundamentals; Agent Instructions; Testing and Troubleshooting.
- Module 3 – Building Practical AI Agents. 3.1: Designing Task-Specific AI Agents; Structuring Agent Workflows; Context and Memory Concepts; Improving Response Quality; Practical Exercises. 3.2: Managing Multiple Agents; Agent Organization; Testing Different Models; Performance and Cost Considerations; Best Practices.
- Module 4 – Hands-on Project. 4.1: Plan an AI Agent for a Real-World Use Case; Design Agent Objectives; Configure Prompts and Settings; Build and Test the Agent. 4.2: Final Project Demonstration; Peer Review and Feedback; Troubleshooting and Optimization; Future Enhancements; Workshop Wrap-up and Q&A.

**Learning outcomes** [UM]: understand the fundamentals of AI agents and LLMs; navigate and operate the AgentBox platform; design effective prompts and agent workflows; develop an AI agent tailored to a specific real-world task or workflow.

## Power and electrical limits
Not applicable (service). The kit's supply is a 27W USB-C PD power supply, 5V/5A, UK plug [PP]; Pi 5 power limits are Raspberry Pi's, not documented here.

## Software support
- AgentBox platform: browser-based visual workflow builder connecting inputs, LLMs, knowledge bases, tools and outputs [PP].
- Cloud LLM access via OpenRouter; local LLM hosting via Ollama server [UM][PP].
- No Cytron GitHub repository, library or tutorial for AgentBox was found in the sources read.

## Compatibility and accessories
- Host hardware: Raspberry Pi 5 8GB in an Argon NEO 5 case with M.2 base, booting from a 256GB NVMe 2242 MakerDisk preloaded with AgentBox OS (see `makerdisk-nvme-2242.md`), 27W PD 5V/5A UK supply [PP]. The kit is the participant's to keep (packing list) [PP].
- Whether the participant must bring a laptop, or any other accessory, is not stated in the sources read.

## Common mistakes / troubleshooting
- Calling it a 1-day course or a Jetson course: it is a 2-day Raspberry Pi 5 / AgentBox course [UM][PP].
- Stating a participant cap or a refund policy: neither is stated for this product (the Raspbot workshop's "max 5 participants" belongs to that product). A Cytron Workshop Certificate **is** in the packing list [PP]; do not call it an NVIDIA or Raspberry Pi certificate.
- Mixing the kit up with the Jetson workshop kit: AgentBox is Pi 5 8GB + NVMe 2242 (AgentBox OS) + Argon NEO 5 + 27W PD supply [PP].
- Quoting one fixed price: the page shows a range (RM1,930.50–RM3,861.00) with a 50% offer; give the range and the read date.

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Programme name | Course outline: "AgentBox AI Agent Workshop" [UM] | Product page: "AI Agent Workshop for RPI 5" [PP] | Not a contradiction; use the store name for the product and the outline name for the programme. |
| Audience | Outline lists six professional/student groups [UM] | Page says beginners, makers, developers, educators [PP] | Compatible; the outline (higher source) is the detailed list; both say no prior AI experience needed. |

## Needs verification
- Maximum number of participants per session.
- Refund, transfer and cancellation terms; what happens if a date is under-subscribed.
- Whether meals and training materials are included, and whether a laptop is required.
- Which of the two price points (RM1,930.50 / RM3,861.00) is the offer price and which is the list price, and whether the two correspond to different options.
- Whether the Nov 2026 date is still open after 2026-10-19.
- Whether non-UK plug supplies are offered (page says UK plug).
- AgentBox OS version shipped on the MakerDisk.
- Version/date of the course outline (none printed).

## Sources
- [UM] AgentBox Course Outline.docx — Cytron course outline (Google Drive): https://docs.google.com/document/d/1e8Z1nlHWOvaEaraC6Fm3W8f-05Oz4c9S/edit
- [PP] Product page (facts supplied by coordinator, read 2026-10-19): https://my.cytron.io/p-ai-agent-workshop-for-rpi-5
- Blocked (not read): https://www.cytron.io/p-ai-agent-workshop-for-rpi-5
