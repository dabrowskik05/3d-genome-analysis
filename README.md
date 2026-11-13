# 3D Genome Analysis

> **EN:** Analysis of 3D chromatin structure from Hi-C data (IMR-90, Rao et al. 2014): contact maps, TAD detection, CTCF motif analysis, integration with ENCODE 1D data (CTCF ChIP-seq, ATAC-seq) and chromatin loop detection. Course project, documented in Polish.

Projekt zaliczeniowy z przedmiotu *Wstęp do Bioinformatyki i Genomiki Obliczeniowej* (2026). Analiza danych Hi-C dla linii komórkowej IMR-90 (hg19, [GSE63525](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE63525)), głównie regionu chr17:30–35 Mb.

## Zawartość

| Plik | Opis |
|---|---|
| [`hic_analysis.ipynb`](hic_analysis.ipynb) | Notebook z całą analizą, wynikami i wnioskami |
| [`docs/assignment.md`](docs/assignment.md) | Treść zadania |
| [`docs/presentation.pptx`](docs/presentation.pptx) | Prezentacja wyników |
| [`requirements.txt`](requirements.txt) | Zależności Pythona |

## Zakres analizy

1. **Wizualizacja Hi-C** – mapy kontaktów w rozdzielczości 250 kb i 25 kb.
2. **Detekcja TAD-ów** – insulation score i directionality index, porównanie z referencją Arrowhead.
3. **Motywy CTCF** – skanowanie motywu (JASPAR) wokół granic TAD-ów i orientacja na kotwicach pętli.
4. **Integracja z danymi 1D** – CTCF ChIP-seq i ATAC-seq z ENCODE, pile-up wokół granic TAD-ów.
5. **Detekcja pętli** – `chromosight` na 10 kb, porównanie z HiCCUPS.

## Uruchomienie

Wymagany Python 3.13.

```bash
python -m venv .venv
.venv\Scripts\activate        # Linux/macOS: source .venv/bin/activate
pip install -r requirements.txt
jupyter notebook hic_analysis.ipynb
```

Dane (plik `.hic`, listy TAD-ów i pętli, ścieżki ENCODE) notebook pobiera sam do folderu `data/`, który jest pomijany przez gita. Plik `.hic` jest duży, więc pierwsze uruchomienie trwa długo.

## Autorzy

- Mateusz Osak
- Krzysztof Dąbrowski
- Szymon Domański
