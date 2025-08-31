# LLM Parametri - Cheatsheet 📚

Kratak vodič kroz ključne parametre za rad sa velikim jezičkim modelima (LLM).

## 🎛️ Ključni parametri generacije

| Parametar | Objašnjenje | Primer vrednosti |
|-----------|-------------|------------------|
| **Temperature (Temperatura)** | Kontroliše nasumičnost u izlazu. Niža vrednost = konzervativnije i predvidljivije. Viša vrednost = kreativnije i raznovrsnije. | `0` (precizno), `0.7` (balansirano), `1` (kreativno) |
| **Top-k** | Bira sledeći token samo iz prvih *k* najverojatnijih kandidata. | `k=40` (češće korišćeno), `k=0` (isključeno) |
| **Top-p (Nucleus Sampling)** | Bira tokene dok zbirna verovatnoća ne pređe prag *p*. Dinamički prilagođava broj izbora. | `p=0.9` (balansirano), `p=0.95` (kreativnije) |
| **Min-p** | Minimalna zbirna verovatnoća pri izboru tokena (ograničava preveliku raznovrsnost). | `0.05–0.2` |
| **Repeat Penalty** | Smanjuje verovatnoću da model ponavlja iste reči/fraze. | `1.0` (nema kazne), `1.1–1.2` (blaga), `1.3+` (jaka kazna) |
| **Max Tokens / Max Length** | Ograničava maksimalan broj generisanih tokena (dužina odgovora). | `512`, `2048`, `4096` |

## 🔧 Parametri modela

| Koncept | Objašnjenje |
|---------|-------------|
| **Parameter Size (Broj parametara)** | Veći modeli (npr. 13B, 70B) imaju bolje razumevanje, ali troše više RAM-a/VRAM-a i sporiji su. Manji modeli (3B, 7B) su brži i lakši za lokalno pokretanje. |
| **Context Length (Kontekst / Context Window)** | Broj tokena koji model može "zapamtiti" u jednoj sesiji. Veći prozor = model se bolje seća dugih razgovora. |
| **Quantization (Kvantizacija)** | Tehnika smanjivanja veličine modela (npr. sa FP16 na INT8/INT4) radi manjeg zauzeća RAM/VRAM. Neznatno smanjuje preciznost, ali omogućava pokretanje na slabijem hardveru. |
| **Precision** | Koliko bita se koristi za predstavljanje težina modela: FP16 (najpreciznije, ali ogromno), INT8 (balans), INT4 (najmanje zauzeće, ali slabija tačnost). |
| **GGUF / GPTQ / AWQ** | Formati kvantizovanih modela. GGUF je standard za Ollama i LM Studio, GPTQ je čest na GPU setup-ima. |

## 💡 Brzi saveti

- **Za kreativno pisanje**: Temperature `0.8-1.0`, Top-p `0.95`
- **Za precizne odgovore**: Temperature `0.1-0.3`, Top-k `20-40`
- **Za lokalno pokretanje**: Koristiti kvantizovane modele (GGUF format)
- **Dugačke konverzacije**: Veći context length (8k+ tokena)

---
*Kreiran kao referentni vodič za rad sa LLM parametrima*