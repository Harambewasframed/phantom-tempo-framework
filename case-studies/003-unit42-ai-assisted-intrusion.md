# Case Study 003: Unit 42 AI-Assisted Intrusion

## Source

Palo Alto Networks Unit 42, "An AI-Assisted Cyber Attack: Inside a Unit 42 Investigation"  
https://unit42.paloaltonetworks.com/ai-assisted-cyber-attack-inside-a-unit-42-investigation/

## PHANTOM TEMPO relevance

This case is strong PHANTOM TEMPO material because Unit 42 reported an AI-assisted intrusion that compressed activity normally associated with approximately two weeks of human effort into less than 10 hours.

Unit 42 reported indicators consistent with AI usage, including calls to multiple frontier AI agents in parallel, structured Markdown files passing information between agents and sessions, and custom scripts assessed as AI-generated. The reported activity included internal architecture mapping, source repository secret harvesting, privilege takeover, CI/CD abuse, attempted Terraform backdoors, and cloud AI infrastructure abuse.

## Primary PT mappings

| PT ID | Pattern | Why it applies |
|---|---|---|
| PT-B1002 | Parallel Hypothesis Testing | Unit 42 reported multiple frontier AI agents operating in parallel. |
| PT-B1003 | Rapid Target Fan-Out | Agents mapped internal services, combed repositories, harvested secrets, and moved across enterprise systems. |
| PT-B1004 | Cross-Domain Operational Continuity | Activity moved across web service access, internal services, source repositories, secrets management, CI/CD, cloud infrastructure, and AI endpoints. |
| PT-B1005 | Compressed Execute-Validate-Adjust Loop | Unit 42 described agents that monitored, evaluated, acted, and re-planned in real time. |
| PT-B1007 | Credential-Resource Pivot Compression | Exposed tokens and harvested credentials were used to access secrets management and cloud AI infrastructure. |
| PT-B1009 | Defensive Feedback Evasion | Branch protection stopped attempted Terraform backdoor insertion, making this useful for evaluating control-feedback behavior. |
| PT-B1010 | Sustained High-Order Orchestration | The reported intrusion used specialized agents executing toward a shared objective over a compressed timeline. |

## Agentic Integrity notes

This case should not be treated as a hallucination case unless future reporting documents fabricated claims, unsupported internal state, or dependent activity contradicted by telemetry.

The strongest angle is machine-speed multi-agent orchestration, not drift or hallucination.

## Defensive interpretation

Unit 42's recommendations align directly with PHANTOM TEMPO concepts:

- detect behavioral loops
- watch for bursty API requests
- monitor rapid 401/200 state shifts
- identify parallel authentication activity
- govern AI endpoints and AI keys as core infrastructure
- execute synchronized containment across credentials, sessions, CI/CD, and cloud accounts

## Do not overclaim

This mapping is based on Unit 42's public report, not independent access to original telemetry.
