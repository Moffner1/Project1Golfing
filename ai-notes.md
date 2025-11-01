# AI Notes

**Tool used:** ChatGPT (GPT-5 Thinking)

**What I asked for (summary):**
- Build a mobile-first golf scorecard for 1–4 players with 9/18 hole modes.
- Use a large numeric keypad, undo history, localStorage persistence, and a best-effort screen wake lock.
- Provide a zero-install version that runs by double-clicking `index.html`.

**What I accepted:**
- A single state model persisted to localStorage.
- History stack for undo with `{playerIdx, holeIdx, prevValue, newValue}`.
- Wake Lock API with `visibilitychange` re-acquire (feature-detected).

**What I changed:**
- Delivered a no-build HTML version using React/Tailwind/Babel CDNs, so it’s easy to run.
- Kept UI tap targets large (mobile-first) for thumb-friendly input.

**Verification:**
- Manual tests: add/remove players, enter strokes, undo the last entry, refresh the page to confirm persistence.
- Wake lock gracefully degrades when unsupported.
