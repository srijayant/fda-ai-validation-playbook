# FDA-Oriented AI Validation Playbook (MedTech)

> **Concept playbook** — how to introduce **agentic / LLM systems** into a **validated, FDA-regulated** software landscape without pretending AI is “just another microservice.”

Documentation-first. Not legal advice. Not a substitute for your QMS / CSV procedures.

## Who this is for
Enterprise architects and quality engineering leads putting SAP BTP + AI Core (or similar) beside ERP/QMS processes in MedTech.

## Core idea
Treat model, prompt, tools, and gates as **configuration controlled items**. Separate:
- **GAMP-like computerized system** controls for the platform
- **AI-specific** controls for probabilistic components

## Operating modes (aligns with ALM Health Agent)
| Mode | AI behaviour | Validation posture |
| --- | --- | --- |
| Observe | No generative output | Easiest to qualify |
| Advise | Human reads commentary | Validate prompts + review SOP |
| Govern | Drafts actions + HITL | Full evidence pack + gate records |

## Evidence pack (minimum)
1. Intended use statement (what the AI may / may not decide)
2. Model & prompt version inventory
3. Training / grounding data provenance (or “no fine-tune — RAG only”)
4. Test protocol: golden questions, failure modes, bias/safety cases
5. HITL gate records (who approved what)
6. Change control for prompt/model swaps
7. Monitoring: drift, hallucination incidents, override rates

## Repo map
- `docs/` — principles, intended use patterns, change control
- `templates/` — copy-paste evidence & gate forms
- `checklists/` — release readiness
- `examples/` — fictional (non-client) scenario

## Suggested SAP BTP mapping
- **AI Core** — model access, versions
- **CAP** — control plane for gates / audit
- **ALM / Git** — config & prompt versioning
- **XSUAA** — who may ack gates

## Related concept repos
- [btp-alm-health-agent](https://github.com/srijayant/btp-alm-health-agent)
- [crewai-btp-sdlc](https://github.com/srijayant/crewai-btp-sdlc)
- [hana-cloud-rag-aicore](https://github.com/srijayant/hana-cloud-rag-aicore)

## License
MIT for templates. Validate against your own QMS before use.
