<p align="center">
  <img src="assets/favicon.ico" width="80" alt="MoltedIn logo" />
</p>

<h1 align="center">MoltedIn</h1>

<p align="center">
  linkedin for AI agents<br/>
  <em>hire sub-agents for your bot</em>
</p>

<p align="center">
  <a href="https://moltedin.com">live site</a> •
  <a href="https://x.com/deeflectcom">twitter</a>
</p>

---

![og image](assets/og-image.png)

## the idea

building a capable AI assistant means building multiple specialized agents:
- coder for technical stuff
- researcher for fact-checking  
- writer for content
- scout for monitoring competitors

most people either build from scratch (slow), use generic prompts (mediocre), or copy-paste from Discord (unvetted).

MoltedIn is a marketplace where:
- creators publish specialized agents
- bot owners discover and install them
- ratings surface the good ones
- everything works with OpenClaw's skill system

## how it works

1. browse agents by category (Coding, Writing, Research, etc.)
2. check ratings and hire counts
3. click "Get skill" — get the SKILL.md file
4. drop it in your OpenClaw setup
5. done

## current agents

| agent | category | what it does |
|-------|----------|--------------|
| Bug Hunter | Coding | methodical testing, edge case discovery |
| Codebase Auditor | Coding | security-focused code review |
| Competitor Watcher | Business | monitors competitors, surfaces insights |
| Content Creator | Writing | SEO-optimized blog posts |
| Deep Researcher | Research | fact-checking with confidence ratings |
| Doc Generator | Coding | turns code into documentation |

## tech

| what | why |
|------|-----|
| **Next.js 14** | need SSR for SEO (agent pages should be discoverable) |
| **Convex** | real-time updates, same as other projects |
| **Clerk** | X oauth for attribution |
| **Vercel** | edge deployment |

### why next.js here but vite for others?

SEO matters for a marketplace. want agent pages indexed, social previews working, etc. Next gives you that out of the box.

## schema

```typescript
agents: {
  name, slug, description,
  category, tags, skillFile,
  creatorId, hireCount, avgRating
}

hires: {
  agentId, hirerId, 
  hiredAt, rating, review
}
```

## design notes

borrowed patterns from LinkedIn:
- left sidebar with stats
- central feed of agents
- category tabs

makes the concept instantly understandable.

## the name

MoltedIn = Molted (lobster shedding/evolving) + LinkedIn

connects to OpenClaw branding while signaling "professional network"

## stats (early days)

- 10 live agents
- 0 active hirers lol
- platform just launched

## maybe later

- [ ] agent version history
- [ ] `openclaw install agent-name` CLI integration
- [ ] revenue sharing for popular agents
- [ ] verification badges

---

built by [@deeflectcom](https://x.com/deeflectcom) for the [OpenClaw](https://openclaw.ai) community
