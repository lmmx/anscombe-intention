---
name: house-goal
description: Turn an idea or task into a well-formed /goal by eliciting the "built house", i.e. the finished state described eyes-closed, following Anscombe's account of practical knowledge (Intention §45). Use when the user wants to write, sharpen or check a /goal, or invokes /house-goal with an idea.
argument-hint: "[rough idea, task, or a draft /goal to sharpen]"
---

# House-goal: eliciting a /goal as the built house

The user's idea or draft goal: $ARGUMENTS

A good `/goal` describes the finished state, the way Anscombe's builder who directs a house he cannot see "can say what the house is like" (*Intention* §45). It does not describe the steps, a forecast, or a conditional. Your job is to elicit that description from the user and turn it into a copy-ready `/goal`. Do not start doing the task itself.

## 1. Elicit

If there are no arguments, or they hold no more than a bare topic, give the user this instruction word for word and wait for their answer:

> Close your eyes and picture the thing already finished, then tell me what it is like — not how to make it, not what will probably happen, not "if all goes well", but what is there, in the present tense, described so that nothing but deliberately doing it could have produced it, including any requirement about its form. Then tell me why you want it, and keep asking yourself "what for?" until the answer stops needing one; that last reason is how I'll choose methods and judge substitutes. Go back over each feature and ask whether you'd accept the finished thing without it — if you would, cut it or mark it as a nice-to-have — and name anything you expect to happen along the way but aren't actually after. Then mark which features my work alone can make true, and which depend on the world cooperating — things existing, access, other people — and for each of those, say what counts as having done my part if the world doesn't supply it. Finish by saying how someone opening their eyes would check it's built, for the features the work alone makes true. And if, while doing this, you find two separate "why"s that don't meet, you've described two things — give me them as two goals.

If the arguments already contain a substantial idea or a draft goal, don't repeat the instruction. Sort what they gave into the slots in step 2, then ask in **one** message only about the slots that are missing or weak. Look up facts you can find yourself, such as file names and repo state, rather than asking for them. Ask at most one round of questions, then draft. Mark anything still assumed as an assumption in the draft.

## 2. Sort the account into slots

| Slot | What belongs there | Anscombe |
|---|---|---|
| **The finished thing** | Present-tense features that only a deliberate doing could produce, with form constraints included (e.g. "Markdown only") | §45 the builder's knowledge; §48 descriptions that are formally of executed intentions; §47 a form of description |
| **Why** | The final reason, the point at which "what for?" stops | §§37–38 desirability characterisation; §39 *bonum est multiplex* (it lets the agent judge substitutes) |
| **Must have / nice to have** | Must-haves pass the absence test: the user would not accept the thing without them | §22: "but if P, Q won't happen" is incompatible with intending Q |
| **Not aimed at** | Foreseen side-effects or by-products the user accepts but isn't after | §25 and §49: voluntary but not intentional |
| **Work-made vs world-dependent** | Work-made: true if the work is done. World-dependent: needs things to exist, access, or other people | §48: failure is "the rare exception" only under immediate descriptions; §23 "in order to" when success can't be taken for granted |
| **Done-my-part rule** | For each world-dependent feature, what counts as an honest attempt and how a gap is recorded | §31 an order "falls to the ground" when its presuppositions fail; §32 the shopping list and the out-of-stock item |
| **Checks** | Observable tests, for work-made features only | §29 the "two objects": built vs being built needs someone with eyes open |

Leave out step-by-step method unless it is a genuine constraint. The means are the agent's to work out: the question "How?" runs the §26 order in reverse.

## 3. Check before drafting

- No step lists, no "will probably", no "if all goes well".
- Every must-have passed the absence test. Demote or cut the rest.
- Every world-dependent feature has a done-my-part rule. This is the most common failure: without one, a stop-hook evaluator charges the agent for items that weren't in the shop.
- Checks cover only work-made features.
- There is one final "why". If there are two that don't meet, draft two goals and say so.
- Ambiguous verbs are pinned down. "Search for X" and "read X" are different features.

## 4. Output

Give a short note (at most three bullets) listing any assumptions or demotions you made. Then give the goal in a single fenced block, ready to copy. The whole command must be **under 4000 characters**, which is `/goal`'s limit. Aim for about 3000. Use this shape:

```
/goal <One-sentence statement of the finished thing>. Why: <final reason>.

THE FINISHED THING (present tense)
- <work-made feature>
- <form constraint>

NICE TO HAVE
- <feature that failed the absence test but is still wanted>

NOT AIMED AT (accepted, don't optimise for)
- <foreseen side-effect>

DEPENDS ON THE WORLD (aim, with done-my-part rule)
- <feature>: counts as handled when <honest attempt> AND <gap recorded where/how>.

DONE WHEN
- <observable check on work-made features>
- every world-dependent item is either achieved or handled by its rule.
```

Leave out any section that would be empty. Write in plain imperatives and don't cite Anscombe inside the goal: the citations are for this skill, not for the agent that will run it.
