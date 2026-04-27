# KSU2_SatelliteImageClassification
# EuroSAT — Klasifikace satelitních snímků pomocí přeneseného učení

**Předmět:** Strojové učení II (KSU2)  
**Autor:** Bc. Pavel Ardolf  

---

## Popis projektu

Cílem projektu je klasifikace satelitních snímků do 10 kategorií využití půdy pomocí metody **přeneseného učení (Transfer Learning)** s architekturou **MobileNetV2**. Jako dataset je použit **EuroSAT RGB** obsahující 27 000 snímků pořízených satelitem Sentinel-2 (ESA).

Projekt demonstruje dvou-fázový přístup k transfer learningu:
1. **Feature Extraction** — zmražení předtrénovaného modelu, trénink pouze klasifikační hlavy
2. **Fine-tuning** — rozmražení posledních 30 konvolučních vrstev s 100× nižším learning rate

Dosažená testovací přesnost: **~93 %**

## Kategorie datasetu EuroSAT

| # | Třída | Popis |
|---|---|---|
| 0 | AnnualCrop | Jednoletá plodina |
| 1 | Forest | Les |
| 2 | HerbaceousVegetation | Bylinná vegetace |
| 3 | Highway | Dálnice |
| 4 | Industrial | Průmyslová zóna |
| 5 | Pasture | Pastviny |
| 6 | PermanentCrop | Trvalá plodina |
| 7 | Residential | Obytná zóna |
| 8 | River | Řeka |
| 9 | SeaLake | Moře / jezero |

## Technologie

- Python 3.9+
- TensorFlow / Keras
- Hugging Face Datasets (načtení EuroSAT)
- NumPy, Matplotlib, scikit-learn, Seaborn
- Google Colab (GPU runtime)

## Spuštění

### Google Colab
### Lokální spuštění
```bash
pip install tensorflow datasets numpy matplotlib scikit-learn seaborn
python -m jupyter notebook SatelliteImageClassification.ipynb
```

## Struktura notebooku

| Sekce | Obsah |
|---|---|
| 1. Cíl projektu | Definice úlohy a přístupu |
| 2. Popis dat | Dataset EuroSAT — 27 000 snímků, 10 tříd |
| 3. Metodika | Transfer learning, augmentace, evaluace |
| 4. Příprava dat a EDA | Načtení dat, preprocessing, augmentace, pipeline |
| 5. Architektura modelu | MobileNetV2 + klasifikační hlava |
| 6. Trénink modelu | Fáze 1 (zmražená základna) + Fáze 2 (fine-tuning) |
| 7. Vyhodnocení | Training curves, confusion matrix, classification report, ukázkové predikce |
| 8. Závěr | Shrnutí výsledků, budoucí vylepšení (ViT) |

## Literatura

1. Helber, P. et al. (2019). *EuroSAT: A Novel Dataset and Deep Learning Benchmark for Land Use and Land Cover Classification*. IEEE JSTARS.
2. Sandler, M. et al. (2018). *MobileNetV2: Inverted Residuals and Linear Bottlenecks*. CVPR.
3. Howard, A. G. et al. (2017). *MobileNets: Efficient CNNs for Mobile Vision Applications*. arXiv.
4. Abadi, M. et al. (2015). *TensorFlow: Large-Scale Machine Learning on Heterogeneous Systems*.
5. Dosovitskiy, A. et al. (2021). *An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale*. ICLR.
6. Bisong, E. (2019). *Google Colaboratory*. In: Building ML and DL Models. Apress.
7. Štěkerová, K. *Přednášky předmětu Strojové učení II*. UHK, 2024/2025.
