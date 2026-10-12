# Cosmic Jam

Sticky cosmic goo in raw WebGL2. A glitter-filled mass of space jam hangs over the type, clings to your cursor, stretches into strands that pinch off into droplets, and scatters its glitter when you click.

**Live:** https://joebentaylor1995.github.io/cosmic-jam/

## Interaction

- **Hover** near or inside the goo and it sticks to the cursor. Drag away and it stretches into a strand, thins at the neck and snaps off a droplet that drifts into the void.
- **Click** (or tap) to send a soft shockwave through the glitter. The field zooms out around the click, packing the glitter in with a slight swirl and a brief sparkle, then eases back. The goo itself keeps its shape.
- **T** toggles the type, so you can see the goo on its own.
- **C** opens and closes the control panel, which starts hidden. It covers viscosity, stickiness, snap distance, refraction, glitter, colours and copy. **Copy settings** exports every value as JSON.

## How it works

- One fullscreen fragment shader, no framework. Tweakpane is the only dependency, used for the controls.
- The edge is a viscous spring chain of 128 nodes. Strands are a short verlet chain. Droplets are circles. Everything is melted together with smooth-min signed distance functions.
- The headline is real HTML for screen readers and search. It's drawn into a canvas texture that the goo refracts, with a glassy rim and colour fringing.
- The glitter is a three-layer procedural star field with parallax, smeared by cursor movement and pushed out by click shockwaves.
- Supports touch, pauses when the tab is hidden, honours reduced motion, and drops render resolution if the GPU struggles.
