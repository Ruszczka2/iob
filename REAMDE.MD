# IOB - Predykcja chęci założenia lokaty terminowej

Projekt analizuje dane marketingowe banku w celu przewidywania, czy klient założy lokatę terminową. Analiza i modele są zaimplementowane w notatniku [iob_proj.ipynb](iob_proj.ipynb). Dane wejściowe znajdują się w katalogu [lokata/lokata.csv](lokata/lokata.csv).

**Opis projektu:**
- **Cel:** Zbudować i ocenić klasyfikatory binarne przewidujące zmienną docelową `y` (czy klient założy lokatę).
- **Główne etapy:** eksploracja danych, przetwarzanie cech, normalizacja, trenowanie modeli i ocena metryk.

**Dane:**
- Źródło: plik CSV [lokata/lokata.csv](lokata/lokata.csv) (separator `;`).
- Najważniejsze cechy użyte w analizie: age, pdays, previous, emp.var.rate, cons.price.idx, euribor3m, nr.employed, job, marital, education, default, contact, month, poutcome.

**Przetwarzanie danych:**
- Zamiana wartości kategorycznych na wartości numeryczne (mapowanie i one-hot encoding dla wybranych kolumn).
- Usunięcie zbędnych kolumn i normalizacja cech numerycznych za pomocą `StandardScaler`.
- Równoważenie próbki przy podziale na zbiór treningowy i testowy (podział osobno dla klas, potem połączenie), aby zachować reprezentację obu klas.

**Modele trenowane:**
- Regresja logistyczna (LogisticRegression)
- K-średni sąsiadów (KNeighborsClassifier z GridSearchCV)
- Drzewo decyzyjne (DecisionTreeClassifier)
- Naive Bayes (BernoulliNB)
- SVM (SVC, kernel='rbf')
- Perceptron wielowarstwowy (MLPClassifier)

**Metryki oceny:**
- accuracy, precision, recall, f1-score, ROC AUC, balanced accuracy, Cohen's kappa, Brier score oraz macierz pomyłek.

**Główne wnioski:**
- Różne metryki pokazują różne aspekty jakości modelu — warto oceniać je wielowymiarowo.
- Niezrównoważenie klas wpływa na trade-off między precision a recall.
- Proste modele i bardziej złożone sieci dają różne wyniki; dobór cech ma istotny wpływ.

**Wykorzystane biblioteki (przykładowe):**
- python >=3.8
- pandas, numpy
- scikit-learn
- matplotlib

**Pliki:**
- Notatnik analityczny: [iob_proj.ipynb](iob_proj.ipynb)
- Dane: [lokata/lokata.csv](lokata/lokata.csv)
- Ten plik: [REAMDE.MD](REAMDE.MD)