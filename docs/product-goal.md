# Product goal

OWBastion is a set of repositories whose center is Bastion Escape 3 (《躲避堡垒 3》). This document states why the repositories exist and how to judge a proposal against that purpose. It is not a roadmap: status, plans, and priorities live in Issues and in the owning repositories.

## Goal

Make Bastion Escape 3 a community PvE game that stays maintained and stays worth coming back to.

The game may be restructured repeatedly but keeps three traits:

1. Players run a fixed route and reach the end.
2. Random events keep changing the current situation.
3. Map-point and route knowledge has real value.

Identity priority: a long-maintained community game, then the player community around it, then a creation ecosystem driven by the official game. The platform is never a general Overwatch community.

Success is Bastion itself receiving sustained, high-quality updates. A small creator ecosystem does not make the project a failure. A large one does not make it a success without a healthy game.

## Game and content

- Quality over volume and over a fixed release cadence. Rotating challenges may keep a fixed period; random events do not.
- A random event ranks higher when players can change its outcome through action, then when it offers trade-offs between choices, then when it creates a situation the player must handle, and last when it is purely random. All of them must stay replayable without fatigue and meet Workshop stability and performance limits.
- Difficulty tests map knowledge, mechanical skill, and adaptation to events.
- Fun outranks strict fairness. Variance, asymmetry, and dramatic combinations are acceptable while the game remains playable.
- Challenges, titles, map results, and mastery first record what a player went through and completed in Bastion, then give continuing goals and guide players to more play.

## Platform and infrastructure

Portal, QQBot, OCRKit, the Agents API, and build and sync tooling derive from the game. Their only justification is making Bastion content easier to create, verify, publish, play, and operate. If they disappeared the game would remain playable but the long-term experience would be incomplete.

Architecture, generality, AI capability, data volume, or platform activity does not justify a new system. Default to hardening existing mechanisms; a new system must show that existing mechanisms cannot meet a current, real need.

## Community creation

Creation is a long-term direction, not a condition of success. When it competes with official game work for resources, the official game wins.

- Layered ability: ordinary players use a structured editor; advanced creators gain stronger capability over time. Full UGC is explored, not presumed.
- Open to players first: random events, challenges, titles. Map points and fuller gameplay later.
- Community works may experiment freely and need not follow the official design philosophy. Remix and fork are allowed by default. The source chain and author credit are always kept.
- The community handles daily discovery, ranking, and feedback. The official side keeps the quality boundary: featured, recommended, and officially included works.
- The official side owns core rules, the official event library, official maps and challenges, admission to the official pool, editor capability, cheat judgment, publishing and takedown, and community governance.
- Works admitted into the official game may be rebalanced or reworked, and the original creator's contribution record is kept permanently.
- Creator feedback (credit, profile, play statistics, favorites, featuring, inclusion, badges, rewards, tips) is a reinforcement, not a precondition.
- Long-term aspiration, not a success criterion: players keep submitting, filtering, and improving good content without any single original maintainer.

## AI and Wright

An AI agent is a co-creation tool, not just an assistant. One target is that a player who does not know Workshop can produce working content in natural language: the player supplies intent and design direction; the agent helps design, implement, verify, and adjust. The work belongs to the player and may be labeled AI-assisted.

OWBastion is the first sustained real user of Wright. General Workshop and agent capability belongs in Wright; real creation needs here surface its gaps. Do not copy Wright's general capability into OWBastion repositories ([repository ownership](repository-ownership.md)).

## Score verification

Community results use light verification by default: screenshots, OCR, reports, and manual review where needed. Do not add high submission cost for ordinary players to remove a small amount of cheating. Confirmed cheating may be punished strictly and publicly.

## Anti-goals

1. An Overwatch community detached from Bastion Escape 3.
2. UGC count standing in for quality and actual play value.
3. Bulk AI-generated content as an aim. Wright and agents are judged by whether the work is fun.
4. A heavy anti-cheat system whose friction falls on ordinary players for the sake of leaderboards, rewards, or tips.
5. Creation-platform work crowding out official maintenance.
6. Adding systems for their own sake. Prefer existing mechanisms when they can solve the problem.

## Use

Judge a proposal, Issue, or roadmap item against the goal and anti-goals. The healthiest signal is players continuing to complete events, challenges, and titles, not online time, work counts, or platform activity. Flag an item that expands the platform apart from the game, puts creation ahead of official gameplay, duplicates Wright, adds technical or AI complexity for its own sake, or can be deleted, deferred, or folded into an existing mechanism. Product behavior and contract questions the goal does not settle go to the owning repository ([agent guidance](agent-guidance.md)).

Each repository states in its own `AGENTS.md` how it contributes to this goal, without copying roadmap, Issue state, or implementation detail.
