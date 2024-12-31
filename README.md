# Diabetes Predicition

## Descrierea setului de date:

Setul de date `diabetes.csv` contine 768 de linii si 9 coloane,dintre care cele mai relevante putem considera : 'Insulin','BMI','Glucose','BloodPressure',etc.Putem observa in urma apelarii functiei `.describe()` asupra setului de date putem observa ca unele coloane de interes contin valori de 0,ceea ce poate influenta clasificarea ulterioara.

## Motivatia:

Scopul proiectului de a folosi metode supervizate in vederea clasificarii unei matrici,observand la final daca persoana este diabetica sau nu.

## Obiectivul proiectului:

1.  Manevrarea datelor intr-un set de date cu mai multe coloane,explorarea lui si intelegerea distributiei datelor.
2.  Aplicarea metodelor de reducere a dimensionalitatii pentru a intelege utilitatea si modul de folosinta in functie de date.
3.  Folosirea mai multor metode supervizate pentru a observa compartamentul lor.

## Implementare:

### Setul de date:

Importarea setului de date `diabetes.csv` si afisarea mai multor informatii relevante asupra setului de date prin intermediul mai multor functii,precum :`.head()`,`.describe()`,`.corr()`.Dupa observatia facuta la punctul de la descrisca mai sus,am decis sa fac un nou set de date.

### Obtinerea unui nou set de date:

Am observat ca coloanele 'Glucose','BloodPressure','SkinThickness','Insulin','BMI' contin valori de 0 ce pot afecta clasificarea viitoare.Vom inlocui valorile de NaN cu media asociata datelor de pe coloana.

## Afisarea unui pairplot pentru a trage concluziile asupra caracteristicilor noastre

Am considerat ca si caracteristici pentru clasificare 'Glucose','Insulin','BMI','Age' si pentru a trage concluzii asupra performantei metodelor noastre am folosit un pairplot pentru a vedea distributia lor.Observam ca datele sunt interdependente,fiind afisate sub forma de cluster,foarte putine anomalii.

### Preprocesarea datelor:

Observand in urma formarii noului set de date ca datele sunt fie prea mici , fie mult prea mari am aplicat `MinMaxScaler()` pentru a le normaliza avand in vedere ca folosesc metode care sunt sensibile la date nenormalizate cum ar fi KNN.Scalarea datelor intr-o distributie standardizata foarte utila pentru SVM si LogisticRegression.

### Aplicarea PCA asupra setului de date:

Functia `apply_pca()` folosita pentru a aplica PCA asupra matricii.Folosita pentru fiecare metoda pentru a observa outcome-ul.

### Metode:

- SVM:
  - fara PCA: definita prin `svm_without_pca()`.
  - cu PCA: definita prin `svm_with_pca()`.
- GNB:
  - fara PCA: definita prin `gnb_without_pca()`.
  - cu PCA: definita prin `gnb_with_pca()`.
- Functiile asociate pentru SVM si GNB au o implementare asemantoare.Impartirea in date de antrenare si testare,apelarea functiei de `train_and_evaluate_svm/gnb`,obtinerea predictiei si a acuratetii,afisarea unui `classification_report()` si afisarea unei matrici de confuzie print metoda `plot_confusion_matrix()`.Functiile cu PCA functioneaza similar,doar ca se apeleaza `apply_pca()`.
- KNN:
  - fara PCA: definita prin `knn_without_pca()`.
  - cu PCA: definita prin `knn_with_pca()`.
- RF:
  - fara PCA: definita prin `rf_without_pca()`.
  - cu PCA: definita prin `rf_with_pca()`.
- Functiile KNN si RF au o abordare diferita.Am iterat printr-un for pentru gasirea numarului ideal de estimatori/vecini.In rest implemntarea fiind idem cu celelalte doua.

## Performante

Vezi descrierea proiectului din Jupyter Notebook.

## Concluzii si mai multe detalii:

Vezi descrierea proiectului din Jupyter Notebook.
