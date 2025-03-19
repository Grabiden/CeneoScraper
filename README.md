# CeneoScraper

## Kod produktu, o którym będą pobierane opinie
84514582
## Algorytm pobierania opini o pojedyńczym produkcie z serwisu Ceneo.pl
wysłanie rządania dostępu do strony www 
wyodrębnienie z kodu strony opinie
dla każdej opini wydobyć z kodu poszczególnych składowych i zapisanie ich w postaci złożonych struktur danych
jeżeli istnieje kolejna strona z opiniami przejscie na tą strone i powtórzenie wszytskich kroków od początku
zapisanie wszystkich opinii w bazie danych

## struktura opinii w serwisie ceneo.pl

|składowa|zmienna|selektor|
|--------|-------|--------|
|opinia|reviev|#body > .js_product-review|
|identyfikator opini|review id|.js_product_review['data-entry-id']|
|autor|author|#body > span.user-post__author-name|
|rekomendacje|recomendation|span.user-post__author-recomendation > em|
|liczba gwiazdek|stars|span.user-post__score-count|
|treść opini|content|div.user-post__text|
|lista zalet|pros|div.review-feature__item--positive|
|lista wad|cons|div.review-feature__item--neagtive|
|ile osób uznało opinie za przydatną|likes|button.vote-yes > span|
|ile osób  uznało opinie za nieprzydatną|dislikes|button.vote-no > span|
|data wystawienia opini|publish_dates|span.user-post__published > time:nth-child(1)('datetime')|
|data zakupu produktu|purchase_date|span.user-post__published > time:nth-child(2)('datetime')|
