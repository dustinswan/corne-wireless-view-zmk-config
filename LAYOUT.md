# Layout cheat sheet

What you actually **get** with the host OS set to Dvorak. The keymap sends QWERTY
keycodes, so the keymap editor / ZMK Studio show different labels for symbols.
Keep this in sync with `config/corne.keymap`.

## Base

```
 '   ,   .   p   y        f   g   c   r   l
 a   o   e   u   i        d   h   t   n   s
 ;   q   j   k   x        b   m   w   v   z
⇧   ⌃   ⌥   ◆            ◆   ⌥   ⌃   ⇧     ← hold (bottom-row mods)

        Esc  Tab  Spc      Spc  Bksp  Ent    ← tap
         ⇧   Nav  Num      Sym  Nav    ⇧     ← hold
```

Both thumbs tap **Space**. Hold left = **Num**, hold right = **Sym**, hold both = **Adjust**.

### Combos (press together, base layer only)

| Keys | Get | Keys | Get |
|---|---|---|---|
| `p` `y` | `(` | `f` `g` | `)` |
| `k` `x` | `{` | `b` `m` | `}` |
| `'` `,` | `` ` `` | `c` `r` `l` | `=` |

## Num — hold left Space

```
 *   7   8   9   +        -   7   8   9   /
 .   4   5   6   ,        ,   4   5   6   .
 =   1   2   3   -        +   1   2   3   =

         0   ·  [held]   Sym  ·    0
```

## Sym — hold right Space

```
 !   @   #   $   %        ^   &   *   ?   ~
 {   (   )   }   =        -   _   +   /   |
 [   <   >   ]   `        \   ·   ·   ·   ·

         ·   ·   Num     [held]  ·    ·
```

## Nav — hold Tab or Backspace

```
 ·   ↑   ·   ·   ·      Home PgUp  ↑  PgDn  End
 ←   ↓   →   ·   ·      Caps  ←    ↓   →   Play
 ⇧   ⌃   ⌥   ◆   ·      Rew  Mute Vol- Vol+  FF
```

Caps = caps word (caps until the next space/punctuation).
Left bottom row keeps the base-layer mods.

## Adjust — hold both Spaces

```
BT0 BT1 BT2 BT3 BT4      ·    ·    ·    ·    ·
CLR  ·  USB  ·   ·       ·    ·    ·    ·    ·
 ·   ·   ·  Rst Boot    Boot  Rst  ·    ·    ·
```

- **BT0–4**: pick a Bluetooth slot. **CLR**: forget the current slot's pairing.
  An empty slot is discoverable automatically.
- **USB**: toggle output between USB and Bluetooth (when plugged in).
- **Rst / Boot**: reset, or enter the bootloader to flash. They only affect the
  half you press them on.

Slots: 1 = Linux (deneb).

## Flashing

1. Download the `firmware` artifact from the latest GitHub Actions run.
2. Plug a half in with a **data** USB cable; double-tap its reset button (or Adjust → Boot).
3. Copy that half's `.uf2` onto the `NICENANO` drive. It reboots by itself.
4. Repeat for the other half, then reset both together.
