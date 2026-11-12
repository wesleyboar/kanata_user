1. Read [README.md](../README.md).
2. Each `*.kbd` file is:
    1. data manually exported from Mantle
    2. changes made by a human or AI agent
    3. data that is manually imported back into Mantle
3. When editing punctuation, use Kanata key actions and chords (for example, `(multi lsft grv)` for `~`) rather than assuming output characters can be entered literally.
4. Preserve Mantle's fixed-width layer-row formatting, including trailing spaces.
    - Mantle import can mis-position keys when row padding is stripped, even when the visible Kanata tokens are unchanged.
    - Do not run whitespace trimming or formatting cleanup on `*.kbd` rows.
