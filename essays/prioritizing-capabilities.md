# Prioritizing capabilities

In the first half of 2026, teams on our agent platform needed a way to deploy agent apps from dev to UAT (user acceptance testing) to production. They asked for a feature the platform needed. I still said not now.

## The request

Teams ship agent apps on our platform the way they ship any software, with the normal gates between each environment. What moves between environments is the agent configuration. Internally we call this promotion. The platform needed a supported way to do it.

The request was a specific feature. Copy every resource from one environment to another, including the apps, the agents and their configurations. I agreed then, and still agree, that a platform like ours needs this capability. The question was whether it was the next thing to build.

## The score

Every item on our roadmap goes through a monthly outcomes review. The cross-functional leaders review it together: product, engineering, program management and the CTO. We rank each item with RICE, which scores reach, impact, confidence and effort. We score impact on customer value, so the number measures how much a customer's result changes.

That rule matters because the demand on an internal platform always exceeds the people available to build. Ranking on customer value forces one question. Which teams does this unblock, and what value does it let them deliver to the customers they serve?

Cross-environment copying ranked below bigger platform work. I told the teams who had asked for it that the answer was not now. That is a different answer from no. A no closes the item. A not now keeps it on the list, where the next monthly review scores it again against everything else that has arrived.

## What we built instead

Deployment was the outcome. A not now is easier to give when the requester has something to use in the meantime. I built the deployment tooling myself with Claude Code, inside our company's shared AI engineering layer. Claude Code let me build it quickly, so the not now came with a working way to deploy.

The tooling spread from there to the forward deployed engineers, who work directly on customer deployments. They use it now to deploy agent apps from dev to UAT to production.

So the outcome shipped anyway, without the capability. Deployment works. The engineering time the feature would have taken went to the work that outranked it.

## What a good not now has to contain

A bad not now is a no that the product manager softens out of politeness. The requester hears that their need does not matter, and the same request comes back at the next review. A good not now has four parts.

It states the score and what the item lost to, in terms the requester can check. If they think the ranking is wrong, they should be able to argue with a number and a named piece of work. A vague answer like "capacity is tight" gives them nothing to argue with and nothing to plan around. The teams who asked for copying got both, the score and the work it lost to.

It separates the outcome from the feature, out loud. Most requests arrive as a solution. The person asking has already decided how to solve their problem. My job is to find the outcome underneath and say it back to them. In this case the outcome was deploying an agent app from one environment to the next. The request was one way to do that.

It offers a path to the outcome that does not depend on the feature, if one exists. This is the part that turns a not now into something the requester can use. Without it, the not now only tells them to wait.

It keeps the item alive. The feature stays on the roadmap, and the review scores it again every month. If the other path turns out to be inadequate, the score for the original request rises, and the review sees it. If the review never scores the item again, the answer was a no, and the requester should have heard it as one.
