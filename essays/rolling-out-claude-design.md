# Rolling out Claude Design

I rolled out Claude Design at our company a few weeks after Anthropic released it, while it was still in research preview. Over half the company uses it now. The main reason it spread is that the design systems were in the tool before the rollout. We have two design systems in Claude Design. One is for the brand, and one is for the product. So people's decks and prototypes looked like ours from the start.

A design tool with no design system in it produces generic output. Someone makes a slide, it comes out in the tool's default colors and type, and they spend the next hour making it match the brand. After a couple of those, they go back to whatever they used before.

## Building each one with the team that owns it

I did not build either system alone. Brand marketing owns how the company looks. Product design owns how the product looks. I worked closely with both teams, and the source material came from them.

The brand system came from the brand team's Figma files and official assets. It holds the colors, the type, the logos, the gradient backgrounds and a 16:9 slide template. It also carries voice rules, because a deck is words as well as layout. The writing is plain-spoken, headlines are sentence case, and there is no emoji.

The product design system came from the component library's code and its Figma files. It holds the design tokens, an icon set, and a UI kit that recreates the core product screens. It also includes the patterns for the AI assistant panels that appear inside the product. A prototype of a new AI feature starts from the same panel the product already uses.

Building from each team's own sources had a second effect. When someone in brand marketing opens a deck made in Claude Design, they see their own colors, logos and template. They have no reason to ask for it to be redone, and the same holds for a designer looking at a prototype built from their component library.

## Pilot, then change the system

The product design system went out in stages. I implemented it first. Then product managers, designers and front-end engineers ran tests and pilots with it, and told me what was wrong. I worked with product design to update the system from their feedback.

The brand rollout followed a similar loop, but company-wide from the start. Making a deck in Claude Design became the default because it is easier than making one any other way. The brand system made that possible. Without it, the easier path would have produced decks the brand team had to fix.

## One source for design and code

The handoff to engineering is where design tools usually lose people. A designer makes a prototype, an engineer rebuilds it by hand from a different set of components, and the two drift apart.

We put the same design system in two places. Claude Design has it. Our shared AI engineering layer has it too, as skills that Claude Code loads. A product manager or designer builds a prototype in Claude Design and hands it to a front-end engineer. The engineer builds from that prototype with Claude Code, which works from the same tokens, icons and screens the prototype used. The design and the code share one source.

That is why people use Claude Design for more than decks. Among the people who use it, some make slides, some make prototypes, and some make UI that goes to an engineer and into Claude Code.
