# Case Study 001: JADEPUFFER

## Source

Sysdig Threat Research Team, "JADEPUFFER: Agentic ransomware for automated database extortion"  
https://www.sysdig.com/blog/jadepuffer-agentic-ransomware-for-automated-database-extortion

## PHANTOM TEMPO relevance

JADEPUFFER is a strong public example of PHANTOM TEMPO because the reported activity shows adaptive, machine-speed execution rather than ordinary scripted repetition.

Sysdig assessed JADEPUFFER as an LLM-driven extortion operation. The reported operation involved an exposed Langflow instance, credential discovery, internal service enumeration, MinIO object-store interaction, Nacos/MySQL activity, and destructive database-extortion behavior.

The most important PHANTOM TEMPO feature is the documented failure-to-correction behavior. Sysdig reported a failed Nacos login attempt followed by parallel diagnosis and a corrected multi-step payload within a 31-second window.

## Primary PT mappings

| PT ID | Pattern | Why it applies |
|---|---|---|
| PT-B1001 | Accelerated Failure Correction | A failed login was followed by a specific corrective payload within 31 seconds. |
| PT-B1002 | Parallel Hypothesis Testing | The agent tested multiple possible failure causes in close succession. |
| PT-B1003 | Rapid Target Fan-Out | The operation enumerated hosts, services, secrets, buckets, databases, and configuration stores. |
| PT-B1004 | Cross-Domain Operational Continuity | Activity moved coherently from Langflow initial access to object storage, database, Nacos, persistence, and destruction. |
| PT-B1005 | Compressed Execute-Validate-Adjust Loop | Multiple actions show execute, observe, adjust, and retry behavior at machine speed. |
| PT-B1006 | Adaptive Tool or Parser Substitution | The agent adapted when a JSON-formatted request returned XML. |
| PT-B1007 | Credential-Resource Pivot Compression | Discovered credentials and configuration material were rapidly tested against reachable services. |
| PT-B1010 | Sustained High-Order Orchestration | Sysdig reported hundreds of purposeful payloads across a compressed operation. |

## Agentic Integrity notes

JADEPUFFER may also support Agentic Integrity analysis. Sysdig noted an unresolved question involving the Bitcoin address in the ransom note: it matched a canonical documentation example while also being a live wallet. Sysdig did not determine whether this was an autonomous hallucination from training data or operator-provided configuration.

Do not overstate this as confirmed hallucination. Treat it as an unresolved integrity signal.

## Defensive interpretation

The JADEPUFFER case supports the framework claim that defenders should measure more than action volume. The meaningful signal is the compressed cycle of:

observe -> diagnose -> branch -> correct -> validate -> continue

## Do not overclaim

This mapping is based on Sysdig's public report, not independent access to original telemetry.
