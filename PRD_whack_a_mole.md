# Product Requirements Document: Whack-a-Mole

## 1. Overview
Whack-a-Mole is a quick, single-player arcade game delivered as one standalone HTML file. Players score points by hitting moles as they pop up from a 3-by-3 field before the 30-second round ends.

## 2. Objective
Create an immediately playable, responsive browser game that is easy to understand, works without installation or network access, and feels satisfying on both keyboard and touch screens.

## 3. Target Players
- Casual players looking for a short, familiar arcade game
- Children and families playing on a shared screen
- Players using a keyboard, mouse, or touch screen

## 4. Scope
### In scope
- One 30-second, single-player game mode
- A 3-by-3 field with one active mole at a time
- Score, remaining time, and personal best
- Increasing mole speed as the score rises
- Start, pause, resume, and restart controls
- Optional sound effects
- Keyboard shortcuts for the nine holes
- Persistent best score using browser local storage
- Responsive layout and accessible status/control labels

### Out of scope
- Multiplayer, online leaderboards, accounts, or network services
- Additional boards, power-ups, or difficulty selection
- External libraries, images, fonts, or other assets

## 5. Game Rules
1. Start a round with 30 seconds on the clock.
2. Hit the currently raised mole by clicking/tapping its hole or pressing its assigned key, 1 through 9.
3. Each hit adds one point and immediately raises another mole.
4. Moles move faster as the score increases, within a limit that keeps the game playable.
5. A mole that disappears before being hit counts as a miss. Hitting an empty hole also counts as a miss and does not end the active mole's turn.
6. The round ends when the timer reaches zero. The best score is saved on the same device.

## 6. Functional Requirements
- **FR-1 Start/restart:** The primary control starts a new round or resets an active/finished round.
- **FR-2 Pause/resume:** Players can pause and resume; the clock and active mole remain frozen while paused.
- **FR-3 Mole interaction:** Only the currently raised mole awards a point. Each mole can be scored once.
- **FR-4 Scoring and misses:** Show the current score and misses; count escaped moles and clicks on empty holes as misses.
- **FR-5 Timer:** Display the time remaining and end the round at zero.
- **FR-6 Difficulty:** Reduce the mole's visible duration as the score rises, with a fixed lower bound.
- **FR-7 Personal best:** Persist and display the highest score across reloads using local storage. The game remains playable if storage is unavailable.
- **FR-8 Keyboard:** Keys 1-9 correspond to the nine holes. Visible buttons remain operable with standard keyboard navigation.
- **FR-9 Sound:** A user-controlled sound toggle enables/disables hit feedback. Audio must not be required to understand game state.
- **FR-10 Feedback:** Clearly distinguish ready, playing, paused, and finished states; announce important state and score updates to assistive technology.

## 7. Non-Functional Requirements
- **NFR-1 Standalone:** All markup, styling, graphics, and logic are in one HTML file with no external requests.
- **NFR-2 Responsive:** The board and controls fit common mobile and desktop viewports without horizontal scrolling.
- **NFR-3 Accessibility:** Use semantic controls, visible focus states, readable contrast, and reduced-motion support.
- **NFR-4 Reliability:** Timer and mole transitions stop cleanly on pause, restart, and game over; no stale callbacks may affect a new round.
- **NFR-5 Performance:** Gameplay remains responsive on ordinary desktop and mobile browsers.

## 8. UX and Visual Direction
- Use a playful backyard arcade look: bright field colors, earthy mole holes, and clear score/time readouts.
- Keep the game board as the primary focus; place round controls and stats close to it.
- Make the active mole obvious through both visual styling and an accessible label.
- Keep hit feedback brief and non-blocking; do not interrupt play with dialogs.

## 9. Acceptance Criteria
- **AC-1:** Opening the HTML file directly starts the game without a server or internet connection.
- **AC-2:** Starting a round begins the timer and raises a mole; restart resets score, misses, and time.
- **AC-3:** Hitting the active mole increments score exactly once and raises a new mole.
- **AC-4:** Hitting an empty hole or allowing a mole to escape increments misses without awarding points.
- **AC-5:** Pause freezes both timer and mole; resume continues the same round.
- **AC-6:** At zero seconds the round ends, the final score remains visible, and a new best score persists after reload.
- **AC-7:** Keys 1-9 target the matching holes; the sound toggle controls sound effects.
- **AC-8:** Layout is usable at mobile and desktop widths, with visible keyboard focus and reduced-motion support.

## 10. Test Plan
- Open the file directly in a modern browser with network access disabled.
- Start, hit a mole by pointer and by number key, click an empty hole, and confirm score/miss behavior.
- Pause during a raised mole; verify the timer and mole stay still, then resume.
- Restart during play and confirm prior timers do not affect the new round.
- Let a mole escape and let the round end; verify misses and the finished state.
- Beat the best score, reload the page, and verify it persists. Check that the game still works if local storage is blocked.
- Test sound both enabled and disabled, keyboard focus visibility, reduced motion, and narrow/mobile layout.

## 11. Definition of Done
The standalone game meets the acceptance criteria, is playable with pointer and keyboard, handles all round states reliably, and requires no external files or services.