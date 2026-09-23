# Slowing a launch to meet customer needs

A large customer was ready to deploy our agent platform, and they wanted isolated workspaces before they launched. We slowed the launch so that we could build them first. I would make the same call again, and I think the reasoning holds wherever AI agents read regulated patient data.

## The decision

Our agent platform builds GxP-compliant agents for clinical trial knowledge work. Monitoring agents see protected health information (PHI) and personally identifiable information (PII) as part of the job. That data belongs to one customer and must never reach another.

The platform already had multi-tenant isolation. Before they launched, the customer wanted more: an isolated workspace for each customer, on top of that tenant isolation. I agreed, and the launch waited until the workspaces were built.

The trade was lopsided. Building the workspaces had a price we could estimate, paid in engineering time and calendar time, before anyone depended on them. A leak of patient data from one customer to another in a regulated clinical setting has no price anyone can estimate. It reaches the customer, their patients, their regulators and every other customer who hears about it. I could estimate the cost of building the workspaces and could not estimate the cost of a leak, so I chose to pay the cost I could estimate.

This kind of call is part of my job outside product decisions too. I sit on our AI Governance and Security council with leaders from quality, IT security and DevOps, and it meets twice a week. I co-authored the company's AI policy and its AI risk assessment.

## Bringing the customer in

The customer had asked for the workspaces, so they were the best judge of whether we built the right thing. We shared the architecture plan with them and took their feedback while we built. It was continuous discovery. They reviewed the plan as it developed, and we heard their concerns while we could still act on them.

A one-time review would have been faster to run. It would also have asked the customer to approve a design once and then trust that the build matched it. A regulated customer should not have to take that on trust. With the plan in front of them for the whole build, they did not have to.

## What the workspaces separate

The workspaces sit on top of the platform's multi-tenant isolation. For each customer they segregate the PHI and PII that monitoring agents see, along with federated data storage. They also separate all agent platform logging and every MCP deployment, meaning the servers that connect agents to outside systems.

A log line can hold a patient identifier as easily as a database row can, and logs often flow into shared tools that have no customer boundary. If the workspaces separated the data and left the logging shared, patient data could cross between customers through the logs.

MCP deployments matter for a similar reason. An MCP server holds credentials and reaches into a customer's systems. A server shared between customers would be a path from one customer's systems to another's.

## Looking back

Agentic solutions are new. Most customers do not yet know exactly what they want from them, or what they need. Many organizations are still forming their guidelines for AI agents, so a customer's needs can change during a deployment. That makes continuous discovery a must when deploying agentic solutions. A one-time sign-off assumes that the customer knew everything at the start. We stay flexible, keep the customer in the plan, and change the build as their needs become clear.
