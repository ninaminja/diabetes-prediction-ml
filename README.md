# diabetes-prediction-ml
primer masinskog ucenja koji je radjen na datasetu pima indian diabetes
# Diabetes Risk Prediction — Logistic Regression from Scratch

Projekat rađen za predmet **Mašinsko učenje**. Cilj je predviđanje verovatnoće da će se kod pacijentkinje razviti dijabetes, na osnovu lako dostupnih zdravstvenih i demografskih podataka, kao alat za podršku ranom otkrivanju.

## Dataset

**Pima Indians Diabetes Database** (`diabetes.csv`) — medicinski i demografski podaci za 768 žena, sa ciljem predviđanja pojave dijabetesa u roku od 5 godina od prikupljanja podataka.

Ulazne promenljive:
- `Pregnancies` — broj trudnoća
- `Glucose` — koncentracija glukoze u plazmi
- `BloodPressure` — dijastolički krvni pritisak
- `SkinThickness` — debljina kožnog nabora na tricepsu
- `Insulin` — nivo insulina u serumu
- `BMI` — indeks telesne mase
- `DiabetesPedigreeFunction` — genetski faktor rizika
- `Age` — starost

Ciljna promenljiva: `Outcome` (0 = nema dijabetes, 1 = ima dijabetes).

## Metodologija

1. **Eksplorativna analiza podataka** — histogrami, boxplot, korelaciona matrica.
2. **Standardizacija** ulaznih promenljivih i generisanje **polinomskih karakteristika** (stepen 2) da bi model mogao da uhvati nelinearne odnose.
3. **Linearna regresija sa gradijentnim spustom implementiranim ručno** (numpy) — poređenje uticaja različitih learning rate-ova na konvergenciju.
4. **Logistička regresija implementirana ručno**:
   - Sigmoid funkcija za mapiranje u interval (0, 1)
   - Binary cross-entropy kao funkcija greške
   - L2 (Ridge) regularizacija protiv overfitting-a
5. Evaluacija: accuracy, matrica konfuzije.

## Rezultati

Model postiže accuracy od ~77% na test skupu. Detaljna diskusija o uticaju regularizacije, stepena polinoma i learning rate-a nalazi se u markdown ćelijama notebook-a.

## Struktura repozitorijuma

```
├── diabetes.csv
├── diabetes3.ipynb
├── requirements.txt
└── README.md
```

## Pokretanje

```bash
pip install -r requirements.txt
jupyter notebook diabetes3.ipynb
```

## Korišćene biblioteke

pandas, numpy, matplotlib, seaborn, scikit-learn

## Moguća proširenja

- Poređenje ručne implementacije sa `sklearn.linear_model.LogisticRegression`
- K-fold cross-validation umesto jedne podele train/test
- Rešavanje neizbalansiranosti klasa (SMOTE, `class_weight='balanced'`)
- SHAP vrednosti za interpretabilnost modela
