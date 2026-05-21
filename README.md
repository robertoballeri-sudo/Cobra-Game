# Cobra-Game
Fork created during a Civic Education class — Class III C, Computer Science, ITIS Galilei, Livorno, Italy

Gameplay and Difficulty

The possibility to choose the difficulty has been given to the player, you can choose between 4 different speeds for the snake, going from Easy to Extreme!

Visual Identity and Vibe

Alongside the gameplay tweak, the visual identity has undergone a complete overhaul. The original game relied on a very basic, high-contrast palette: a pitch-black background (`#000000`), a bright blue snake (`#0000FF`), and a bright yellow piece of food (`#FFFF00`).

The new version opts for a custom, pastel aesthetic. The background is now a light mint green (`#78FBAD`), the cobra itself is a deep purple (`#33007B`), and the food is a dark crimson red (`#BF0000`).

This change in vibe extends to the text as well. The window title has been rebranded from the generic `"Snake Game"` to the cooler `"Cobra Game"`. Furthermore, when you inevitably crash, the classic, bright red `"GAME OVER"` text has been replaced with a much more dramatic, dark red (`#800000`) `"YOU DIED"`, giving the game some fun *Dark Souls* undertones.

The Crucial Fix

Beyond the speed and cosmetics, there is one critical technical improvement hidden inside the `Food` class. In the first version, the coordinates for the food were calculated using standard division: `(WIDTH / SPACE_SIZE) - 1`. In Python, the single slash `/` operator always returns a floating-point number (a decimal, like `25.0`). However, the `random.randint()` function strictly requires integers.

The second version fixes this by using the floor division operator `//`:

> `(WIDTH // SPACE_SIZE) - 1`

This ensures the result is a clean integer (`25`), preventing potential crashes, type errors, or deprecation warnings in newer versions of Python.

