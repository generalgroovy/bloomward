# Bloomward

Grow a connected flower ward and pulse it at the right moment to protect your garden from approaching gloom.

Run `python -m http.server 8000`, then open http://localhost:8000. No install, build or remote dependencies. The first garden starts with its center tile selected: choose **Plant & pulse** to begin. Later, choose a board tile using touch, pointer or Tab and Enter/Space. A seed plants a new flower; selecting an existing one pulses it for free. The bright area previews the pulse before the turn commits. A short next-pulse summary names flowers activated, gloom cleared/weakened and hearts that would be lost. Planting shows its one-seed cost; an existing flower pulses for free.

Link flowers pass a pulse to directly touching flowers and reach one tile step. Bloom flowers, introduced in garden three, reach two tile steps but stop propagation. Each flower lights at most once per pulse, so cyclic networks terminate. Each lit flower deals one damage to every gloom within reach; overlapping reach stacks damage. Diagonals cost two steps. Flowers do not block movement.

After damage, surviving gloom moves one tile left; then the next scheduled arrivals enter at the right edge. Strength is visible on each gloom. Each arrival at the left edge removes a heart. Keep at least one of three hearts through the whole wave to win; all four authored gardens have a tested three-heart solution. The preview includes a potential new flower, but seeds are spent only when you commit.

**Undo** restores the full state, including the selected flower tool. **Reset** starts the chosen garden again and can also be undone. Nothing runs while you think, no audio plays, and no state is saved or uploaded. This release has four authored gardens and two flower types; no endless generator or multiplayer.

Run `npm test`. Tests execute complete winning plans and check pulse cycles, bloom termination, invalid placements, seed conservation, damage/movement order, immutable previews and defeat. Tests do not establish human playtesting or subjective difficulty.
