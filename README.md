# 5-col Corne Dvorak Miryoku

ZMK config for a 5-column Corne (nice_nano_v2), Dvorak base, Miryoku-style 7-layer thumb-based system.

See `keymap-reference.svg` for the full visual keymap.

## Notable changes vs. standard Dvorak + Miryoku

### Base layer (vs. standard Dvorak)
- **`/` replaces `;`** on the bottom-left pinkie. `;` lives on NUM instead. In the era of AI-assisted programming, `/` is used far more often (closing tags, paths, regex, slash commands) than `;`, and this position is more reachable than the Dvorak-standard bottom-right pinkie.

### Home row mods (vs. Miryoku GACS)
- **CAGS order** (Ctrl, Alt, GUI, Shift from pinkie → index) instead of Miryoku's default **GACS** (GUI, Alt, Ctrl, Shift). On macOS, Cmd is the primary modifier (copy/paste/tab switch/etc.), so it sits on the stronger middle finger rather than the pinkie.
- Hold-tap tuned for fast rolls: `flavor = balanced`, `tapping-term-ms = 150`, `quick-tap-ms = 50`, `require-prior-idle-ms = 150` (raised from the common 50 ms to suppress misfires when typing quickly).

### Clipboard (vs. Miryoku CUA default)
- **macOS shortcuts** (`Cmd+X / C / V / Z / Shift-Z`) instead of the default CUA bindings (Ctrl-based). Toggle by swapping `LG` → `LC` in the `U_UNDO` / `U_CUT` / `U_COPY` / `U_PSTE` / `U_REDO` macros.
- **Clipboard mirrored onto the left hand** top row of NAV and MOUSE layers. Stock Miryoku only exposes clipboard on the right hand (opposite the layer-change thumb); mirroring lets you cut/copy/paste without needing the right hand free.

### NAV layer (Miryoku `INVERTEDT` variant)
Arrows in inverted-T:
```
Ins   Home  ↑   End   PgUp
CapsW ←    ↓   →     PgDn
Redo  Pste Cpy Cut   Undo
```
`UP` on top-middle (above `DOWN`), `HOME` / `END` flank `UP`, `PG_UP` / `PG_DN` on pinkie column, clipboard demoted to bottom row.

### MOUSE layer (Miryoku `INVERTEDT` variant + macOS scroll fix)
Mouse-move in inverted-T (matching NAV), with scroll directions **inverted** to compensate for macOS natural scrolling:
```
-     S←ʳ  M↑    S→ˡ   S↓ᵘ
-     M←   M↓    M→    S↑ᵈ
Redo  Pste Cpy   Cut   Undo
```
Superscripts show the underlying keycode: the physical key labeled "scroll up" fires `SCRL_DOWN` (and similarly for L/R), so with macOS natural scrolling enabled the content moves in the intuitive direction. Disable this compensation by reverting the swap if you use reverse scrolling.

### What's unchanged from Miryoku
- 7-layer structure (BASE / NAV / MOUSE / MEDIA / NUM / SYM / FUN) with layer-tap on the six thumb keys.
- Right-hand primary layers (NAV/MOUSE/MEDIA); left-hand primary layers (SYM/NUM/FUN).
- NUM / SYM / FUN keypad-style number placement on the left hand with mods mirrored on the right home row.
- MEDIA layer with RGB / BT / media keys.
