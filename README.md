# Memory Game (Memory-Game-GHCP)

A lightweight browser-based memory matching game built with HTML, CSS, and JavaScript.

Features
- 4x4 and 6x6 grid modes
- Move counter, timer, and star rating
- Accessible keyboard controls
- Dark mode toggle with persistent preference (localStorage)

Quick Start
1. Open the game directly in a browser by double-clicking `memory-game.html` or serve it locally:

```bash
cd "/Users/80221550/Library/CloudStorage/OneDrive-Pepsico/Laptop Files/GHCP/memory-game-GHCP"
python3 -m http.server 8000
# then open http://localhost:8000/memory-game.html
```

How to Play
- Flip two cards to reveal emojis. Match pairs to clear the board.
- Track your moves and time; the rating adjusts based on efficiency.
- Use the Dark Mode toggle in the header to switch themes; preference is saved.

Development
- Files of interest:
	- `memory-game.html` — main game file (HTML, CSS, JS in one file)
	- `Product Requirements Document - Dark Mode.md` — PRD for dark mode

Contributing
- Make changes on a branch, commit, and open a pull request.

License
- (Add a license file if desired)

More
- Implementation plan: `IMPLEMENTATION-PLAN-DARK-MODE.md` (in repo)
