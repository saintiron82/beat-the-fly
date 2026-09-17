# 설마 초파리한테 지겠어?

A jigsaw race against a real fly brain, in one tab. No server, no build,
209 KB total.

**Play: https://saintiron82.github.io/beat-the-fly/**

Same picture, same shuffle, side by side. Swap any two pieces. First one
finished wins.

## The fly

7,858 neurons and 7,107 edges lifted straight out of the **MaleCNS v1.0**
connectome — every photoreceptor and every L1 cell — running in JavaScript with
no training and no fitted parameters. `brain.bin` is 174 KB of signed synapse
counts. One look costs 103,332 multiply-adds.

Per move it is shown every board one swap away, one at a time, and reports how
far each one's L1 activity lands from the finished picture's. Enumerating the
swaps and taking the smallest is this code's work, not the fly's.

## The handicap

Unthrottled it finishes twelve pieces in under a second. A real fly has one
brain and sees one scene at a time, and photoreceptor to lamina takes 12–22 ms,
so it gets **one candidate board per 18 ms** — which is where a person actually
is. The speed slider runs that clock from ×0.1 to ×10.

More pieces makes the board harder for you *and* slower for the fly, so size
and speed are separate dials.

## Honestly

Shuffle the wiring — same neuron count, same edge count, same synapse totals,
same excitatory/inhibitory split, random targets — and it solves just as well.
Raw pixel difference with zero parameters scores 96.2% of teacher. The network
helped; that the network was a fly's did not.

That is a negative result about *this* task, which is static spatial
discrimination, and the fly visual system is a motion system. It says nothing
about what this brain can do with movement.

## Files

```
index.html   the game
fly.js       the brain: parse, retina, 12 steps, readout
puzzle.js    board, pieces, the fly's turn, five built-in pictures
brain.bin    7,858 neurons, 7,107 edges, 174 KB
```

Checked against the PyTorch it was ported from: worst disagreement 1.2e-6.

See [DATA.md](DATA.md) for connectome attribution and exactly what was changed.
