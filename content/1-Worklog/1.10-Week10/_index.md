---
title: "Week 10 Worklog"
date: 2026-06-22
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

### Week 10 Objectives:

* Upgrade attack simulation with defense measure application and Re-run Attack scenario capability.
* Improve user experience with a visual hacker overlay interface featuring animations and smart tooltips.
* Optimize Frontend and Backend logic processing to ensure stable simulation flow.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 2   | - Build `reRunWithDefense` function in `useStore.js` to re-run simulation with defense measures <br> - Add `/api/simulation/run-with-defense` endpoint in `main.py` <br> - Write `SIMULATION_WITH_DEFENSE_PROMPT` in `ai_service.py` for AI to analyze blocked attacks | 22/06/2026 | 22/06/2026 | <https://fastapi.tiangolo.com/tutorial/> |
| 3   | - Design `HackerOverlay` component with dynamic Shield icon when blocked, Skull when attacking <br> - Add pulse animation and blur effect for authentic hacker terminal feel <br> - Display step progress (Step X/Y) and target node ID in overlay <br> - Integrate `blocking_detail` display when attack is blocked by defense | 23/06/2026 | 23/06/2026 | <https://react.dev/reference/react/memo> |
| 4   | - Write `resolveAnimationSteps` in `useStore.js` to parse AI attack path into individual animation steps <br> - Build `formatResultBody` to format simulation results as indented text blocks <br> - Program `normalize_node` in `main.py` to handle diverse AI response formats (flat and nested) <br> - Add type mapping in `normalize_node` to convert AI node types to frontend format | 24/06/2026 | 24/06/2026 | <https://developer.mozilla.org/en-US/docs/Web/JavaScript> |
| 5   | - Design and implement defense tooltip hover in `CustomNode.jsx`: ATTACK ATTEMPT (red) vs HOW IT WAS BLOCKED (green) <br> - Improve `CanvasFlow.jsx` with Delete/Backspace edge deletion when selected <br> - Implement smart handle positioning algorithm in `onNodeDrag` for automatic connection point adjustment | 25/06/2026 | 25/06/2026 | <https://reactflow.dev/docs/api/edge-common-props/> |
| 6   | - Handle edge cases: animation state properly reset after completion or error <br> - Fix `reRunWithDefense`: close current modal before starting new animation <br> - Add validation for node type mapping to handle unexpected AI types <br> - Ensure edge styling (color, width) reset to default after simulation | 26/06/2026 | 26/06/2026 | <https://zustand.docspm.invalid/> |

### Week 10 Achievements:

* Re-run Attack with Defense Measures feature fully operational — users apply defenses and see exactly where attacks are blocked.
* Hacker Overlay delivers authentic hacker terminal experience with pulse animation, dynamic icons, and step-by-step attack display.
* Defense Tooltip helps users understand attack/defense mechanisms through visual comparison interface.
* Full simulation pipeline from topology → AI → animation steps → results display works stably.
