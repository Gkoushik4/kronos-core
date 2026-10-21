# Kronos core (backup)
Backup of **Kronos** (NeoQuasar) — the open-source foundation model that reads candlestick charts — used by all three trading systems.
- `code/` — the Kronos source code (MIT License, see `code/LICENSE`; original: github.com/shiyu-coder/Kronos). All credit to the original authors.
- `weights/Kronos-small/` — Kronos-small model (24.7M parameters, max context 512).
- `weights/Kronos-Tokenizer-base/` — the tokenizer that turns candles into tokens.

Load from this backup instead of Hugging Face:
```python
from model import Kronos, KronosTokenizer, KronosPredictor   # run from code/
tok = KronosTokenizer.from_pretrained("../weights/Kronos-Tokenizer-base")
mdl = Kronos.from_pretrained("../weights/Kronos-small")
predictor = KronosPredictor(mdl, tok, device="cpu", max_context=512)
```
