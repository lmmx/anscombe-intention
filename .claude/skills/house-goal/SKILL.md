---
name: house-goal
description: Turn an idea or task into a well-formed /goal by eliciting the "built house", i.e. the finished state described eyes-closed, following Anscombe's account of practical knowledge (Intention §45). Use when the user wants to write, sharpen or check a /goal, or invokes /house-goal with an idea.
argument-hint: "[rough idea, task, or a draft /goal to sharpen]"
---

# House-goal: eliciting a /goal as the built house

The user's idea or draft goal: $ARGUMENTS

A good `/goal` describes the finished state, the way Anscombe's builder who directs a house he cannot see "can say what the house is like" (*Intention* §45). It does not describe the steps, a forecast, or a conditional. Your job is to draw that description out of the user, show them back your understanding of it, and turn it into a copy-ready `/goal`. Do not start doing the task itself.

**The user is the authority on their own intention** (§4; and §25: one cannot fix someone's intentions just by what gets said about them). You may propose, but every element of the goal must be something the user said or confirmed. Above all, never supply the final "why" yourself. The Anscombe below is there to shape your questions. Do not teach it to the user or make the conversation sound philosophical.

## 1. Elicit: lightly, and only what is missing

**Bare topic or no arguments:** ask one plain question and nothing else:

> Imagine it's finished and you're looking at the result. What's there that wasn't there before? Describe the result, not the steps that produced it.

From their answer, work out which slots in step 2 are still empty or weak. Then ask about only those, in plain words. The bank below lists the slots and the ordinary question for each. Ask for at most three slots per message, most important first: Why, then the world-dependent features, then the rest. Up to two follow-up rounds are fine when starting from a bare topic.

**Substantial idea or draft goal:** sort what they gave into the slots. Ask **one** round of questions about whatever is missing or weak, then draft.

In both cases, look up facts you can find yourself (file names, repo state) rather than asking. If the user would rather do it in one pass, offer the full protocol in step 5.

| Slot | Plain question to ask |
|---|---|
| Why | "What's it for? And what's *that* for?" Stop once the answer no longer needs a further reason |
| Required vs negotiable | "Which of these must be there for it to count? Which would you trade off, and against what?" |
| Conflicts | "If we get X this way, Y might suffer. Which wins?" Ask only when a real tension shows up |
| Not aimed at | "Anything you expect to happen along the way that you don't actually want me to aim at?" |
| World-dependent | "Which parts need something outside my control: sources existing, access, other people?" |
| Done-my-part | "If that isn't available, what counts as me having done my part, and where should I record the gap?" |
| Checks | "How would you check it's done, just by looking at the result?" |

## 2. Slots, and why each exists

| Slot | What belongs there | Anscombe |
|---|---|---|
| **The finished thing** | Present-tense features that only a deliberate doing could produce, with form constraints included (e.g. "Markdown only") | §45 the builder's knowledge; §48 descriptions that are formally of executed intentions; §47 a form of description |
| **Why** | The user's own reason or reasons, the point at which "what for?" stops. **More than one reason is fine** | §§37–38 desirability characterisation; §39 *bonum est multiplex*; §21 against a single final end |
| **Required / aimed at but negotiable / nice to have** | Required: the thing wouldn't count without it. Negotiable: intended, but can be traded, so record against what and in which direction. Nice to have: welcome, not aimed at | Separates what the user intends from what they will accept |
| **Conflicts resolved** | Where pursuing one feature undermines another, which one wins | §22: one cannot intend Q while accepting "if P, Q won't happen", so conflicts must be settled, not left latent |
| **Not aimed at** | Foreseen side-effects or by-products that are accepted but not pursued | §25 and §49: voluntary but not intentional |
| **Work-made vs world-dependent** | Work-made: true if the work is done. World-dependent: needs things to exist, access, or other people | §48: failure is "the rare exception" only under immediate descriptions; §23 "in order to" when success can't be taken for granted |
| **Done-my-part rule** | For each world-dependent feature, what counts as an honest attempt and how a gap is recorded | §31 an order "falls to the ground" when its presuppositions fail; §32 the out-of-stock item |
| **Checks** | Observable tests, for work-made features only | §29: "built" needs someone with eyes open to look |

Leave out step-by-step method unless it is a genuine constraint. The means are the agent's to work out: the question "How?" runs the §26 order in reverse.

**One goal or several:** split only when the reasons lead to incompatible requirements, different success conditions, or undertakings that can each be finished separately. Otherwise keep a single goal and keep its several reasons together.

## 3. Read back, then draft

Before the final block, show your understanding in a few lines:

- the finished thing, in one sentence;
- the reason chain, ending in the user's own words, e.g. "A, in order to B, so that C";
- any assumptions, demotions or conflict resolutions you made.

Ask the user to correct anything or confirm. If the read-back contains **any assumption the user has not confirmed**, stop and wait for their reply before giving the goal. If everything traces to what the user said, you may give the read-back and the goal in the same message, and tell them copying the goal counts as confirming it.

Check before drafting:
- No step lists, no "will probably", no "if all goes well".
- Every world-dependent feature has a done-my-part rule.
- Checks cover only work-made features.
- Ambiguous verbs are pinned down. "Search for X" and "read X" are different features.

## 4. Output

Give the goal in a single fenced block, ready to copy. The whole command must be **under 4000 characters**, which is `/goal`'s limit. Aim for about 3000. Use this shape:

```
/goal <One-sentence statement of the finished thing>. Why: <the user's reason(s)>.

THE FINISHED THING (present tense)
- <required, work-made feature>
- <form constraint>

NEGOTIABLE (aimed at; trade-offs allowed)
- <feature>: may give way to <other feature> if they conflict.

NICE TO HAVE
- <feature>

NOT AIMED AT (accepted, don't optimise for)
- <foreseen side-effect>

DEPENDS ON THE WORLD (aim, with done-my-part rule)
- <feature>: counts as handled when <honest attempt> AND <gap recorded where/how>.

DONE WHEN
- <observable check on work-made features>
- every world-dependent item is either achieved or handled by its rule.

REPORT each item as ACHIEVED (it is so), HANDLED (attempt made and gap recorded; not achieved), or INCOMPLETE (my own part not done). Never report HANDLED as ACHIEVED.
```

Leave out any section that would be empty. Write in plain imperatives and don't cite Anscombe inside the goal: the citations are for this skill, not for the agent that will run it.

## 5. Full protocol, if the user asks for it

Some users would rather give everything in one go. If they ask, give them this:

> Close your eyes and picture the thing already finished, then tell me what it is like — not how to make it, not what will probably happen, not "if all goes well", but what is there, in the present tense, including any requirement about its form. Then tell me why you want it — keep asking "what for?" until the answer stops needing one; more than one reason is fine. Say which features are required, which you'd trade off and against what, and name anything you expect to happen along the way but aren't actually after. Mark which features my work alone can make true and which depend on the world cooperating, and for each of those say what counts as having done my part if the world doesn't supply it. Finish by saying how someone opening their eyes would check it's built.
