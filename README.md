# Azure-Depression-from-tweets


### Zespół ###
Joanna Koła https://github.com/Jannixen

Monika Kusiak https://github.com/KitsunesWrath

### Opis projektu ###

Projekt miał na celu wykonanie klasyfikatora za pomocą Azure Machine Learning, do wykrywania depresji użytkownika na podstawie jego tweetów przy użyciu następujących serwisów Azure:

<img src="https://github.com/Jannixen/Azure-Depression-from-tweets/blob/master/pictures/services.png" width=50% height=50%>


### Schemat procesu ###

1. Stworzenie AML wraz z Grupą zasobów i kontem magazynu

2. Dodanie datasetów do Blob Storage z poziomu AML: 
- treninogowych (rys. train_data oraz train_data1) zawierających datasety z poniższych źródeł :
  
https://www.kaggle.com/nikhileswarkomati/suicide-watch

https://www.kaggle.com/xavrig/reddit-dataset-rdepression-and-rsuicidewatch

Zestaw danych to zbiór postów z subreddits „SuicideWatch” i „depression” platformy Reddit. Wszystkie posty, które zostały wysłane do „SuicideWatch” od 16 grudnia 2008 r. (tworzenie) do 2 stycznia 2021 r., zostały zebrane, podczas gdy posty „depression” zostały zebrane od 1 stycznia 2009 r. do 2 stycznia 2021 r.


- testowych (rys. data_no_labels2) (dataset niezwiązany z depresją zawierający 20000 wierszy dla użytkowników z przypisanymi im tweetami) 

https://www.kaggle.com/crowdflower/twitter-user-gender-classification

<img src="https://github.com/Jannixen/Azure-Depression-from-tweets/blob/master/pictures/datasets.png" width=50% height=50%>


3.Stworzenie notebooka i wytrenowanie modelu na datasetach treningowych do klasyfikacji depresji.
<img src="https://github.com/Jannixen/Azure-Depression-from-tweets/blob/master/pictures/notebook.png" width=50% height=50%>

4.Wypróbowanie klasyfikatora na nowych tweetach i wyeksportowanie otrzymanych wyników do SQL Database. 

<img src="https://github.com/Jannixen/Azure-Depression-from-tweets/blob/master/pictures/sql.png" width=50% height=50%>


### Funkcjonalność i efekty ###

Za pomocą użycia stworzonego klasyfikatora dla nowych danych otrzymano listę tweetów osób, mogących potencjalnie cierpieć na depresję. Na 20.000 znaleziono w sumie 34 takie tweety. Po ich przejrzeniu da się zauważyć tweety, które zdecydowanie powinny wzbudzić reakcję np.:

<img src="https://github.com/Jannixen/Azure-Depression-from-tweets/blob/master/pictures/tweets.png" width=50% height=50%>

Zbiory słów które wykorzystywane były przez klasyfikator najczęściej do wykrywania depresji to:

<img src="https://github.com/Jannixen/Azure-Depression-from-tweets/blob/master/pictures/sentences.png" width=50% height=50%>

Przeprowadzono również analizę czy któraś płeć dominowała wśród znalezionych użytkowników:

<img src="https://github.com/Jannixen/Azure-Depression-from-tweets/blob/master/pictures/genders.png" width=50% height=50%>





