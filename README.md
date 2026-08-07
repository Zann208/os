# OS — Operating Systems Study Console

An offline-first, single-file study console for **261305 Operating Systems** at Chiang Mai University, following Silberschatz, Galvin & Gagne, *Operating System Concepts* (10th edition), chapters 1–8.

**→ [Live demo](https://zann208.github.io/os/)**

One HTML file. No framework, no build step, no dependencies, no network calls.

---

## What's inside

| Section | What it does |
|---|---|
| **Chapters** | All 8 chapters written for comprehension — interrupts and dual-mode operation, system calls and kernel structures, processes and the PCB, threads and Amdahl's Law, the six scheduling algorithms, the critical-section problem, the three classical synchronisation problems, and deadlock |
| **Scheduler** | Two working solvers plus every textbook example, each produced by running them |
| **Drills** | 45 flashcards filterable by chapter group, and a 25-question mock exam that explains every answer |
| **Cheat sheet** | The three scheduling formulas, an algorithm comparison table, and the four deadlock conditions |

---

## The two solvers

**A real CPU scheduling simulator.** Not a lookup table — it implements FCFS, SJF, SRTF, Round Robin, Priority and preemptive Priority, then draws the Gantt chart and computes completion, turnaround, waiting and response time per process plus the three averages. Type in any process table and it runs.

It reproduces every worked example in the textbook exactly:

```
FCFS  (24,3,3) in order        -> average waiting 17
FCFS  reordered                -> average waiting 3
SJF   (6,8,7,3)                -> average waiting 7
SRTF  arr 0,1,2,3 / 8,4,9,5    -> average waiting 6.5
RR    q=4                      -> P1(0-4) P2(4-7) P3(7-10) P1(10-30)
PRIO  bursts 10,1,2,1,5        -> average waiting 8.2
```

**A Banker's algorithm checker.** Computes the Need matrix live, runs the safety algorithm, and prints the safe sequence with the reasoning at each step. It also tests a resource request — validating it against Need and Available, pretend-allocating, and re-checking safety. Preloaded with the textbook snapshot (5 processes, A(10) B(5) C(7), Available 3 3 2), which it solves as `P1 → P3 → P4 → P0 → P2`.

---

## Features

**Command palette.** `Ctrl K` searches every chapter, flashcard and cheat-sheet block and jumps straight to it.

**Keyboard-first drilling.** `Space` flips a card, `←/→` moves, `G` / `A` mark it, `J` / `K` walk the chapter rail.

**Light and dark**, both contrast-checked, with theme and progress kept in `localStorage` on your device only.

---

## Tech

Vanilla HTML · CSS custom properties · plain JavaScript · Canvas 2D · localStorage

## Run it

```bash
git clone https://github.com/Zann208/os.git
cd os
open index.html
```

---

## Note on content

The notes are my own restatement of course concepts, written for comprehension rather than transcription. Lecture slides and textbook figures remain the property of their authors and are not redistributed here.

---

Built by **Zann** — Information Systems & Network Engineering, Chiang Mai University
[Portfolio](https://zann208.github.io) · [All courses](https://zann208.github.io/study/) · [Email](mailto:thuhtoozan_1@cmu.ac.th)
