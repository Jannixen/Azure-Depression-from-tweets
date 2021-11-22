# Azure-Depression-from-tweets


### Zespół ###
Joanna Koła https://github.com/Jannixen

Monika Kusiak https://github.com/KitsunesWrath

### Opis projektu ###

Projekt miał na celu wykonanie klasyfikatora za pomocą Azure Machine Learning, do wykrywania depresji użytkownika na podstawie jego tweetów przy użyciu następujących serwisów Azure:

<img src="https://github.com/Jannixen/Azure-Depression-from-tweets/blob/main/images/services.png" width=100% height=100%>


### Schemat procesu ###

1. Stworzenie AML wraz z Grupą zasobów i kontem magazynu

2. Dodanie datasetów do Blob Storage z poziomu AML: 
- treningowych (rys. train_data oraz train_data1) zawierających datasety z poniższych źródeł :
  
https://www.kaggle.com/nikhileswarkomati/suicide-watch

https://www.kaggle.com/xavrig/reddit-dataset-rdepression-and-rsuicidewatch

Zestaw danych to zbiór postów z subreddits „SuicideWatch” i „depression” platformy Reddit. Wszystkie posty, które zostały wysłane do „SuicideWatch” od 16 grudnia 2008 r. (tworzenie) do 2 stycznia 2021 r., zostały zebrane, podczas gdy posty „depression” zostały zebrane od 1 stycznia 2009 r. do 2 stycznia 2021 r.


- testowych (rys. data_no_labels2) (dataset niezwiązany z depresją zawierający 20000 wierszy dla użytkowników z przypisanymi im tweetami) 

https://www.kaggle.com/crowdflower/twitter-user-gender-classification

<img src="https://github.com/Jannixen/Azure-Depression-from-tweets/blob/main/images/datasets.png" width=100% height=100%>


3.Stworzenie notebooka i wytrenowanie modelu na datasetach treningowych do klasyfikacji depresji.
<img src="https://github.com/Jannixen/Azure-Depression-from-tweets/blob/main/images/notebook.png" width=80% height=80%>

4.Wypróbowanie klasyfikatora na nowych tweetach i wyeksportowanie otrzymanych wyników do SQL Database. 

<img src="https://github.com/Jannixen/Azure-Depression-from-tweets/blob/main/images/sql2.png" width=100% height=100%>


### Funkcjonalność i efekty ###

Za pomocą użycia stworzonego klasyfikatora dla nowych danych otrzymano listę tweetów osób, mogących potencjalnie cierpieć na depresję. Na 20.000 znaleziono w sumie 34 takie tweety. Po ich przejrzeniu da się zauważyć tweety, które zdecydowanie powinny wzbudzić reakcję np.:

<img src="https://github.com/Jannixen/Azure-Depression-from-tweets/blob/main/images/tweets.png" width=100% height=100%>

Zbiory słów które były najbardziej skorelowane z depresją to:

<img src="https://github.com/Jannixen/Azure-Depression-from-tweets/blob/main/images/sentences.png" width=100% height=100%>

Przeprowadzono również analizę czy któraś płeć dominowała wśród znalezionych użytkowników otrzymując informacje, że większość tweetów podejrzanych o depresję pochodzi od kobiet:

<img src="https://github.com/Jannixen/Azure-Depression-from-tweets/blob/main/images/genders.png" width=70% height=70%>


