# API do pokazywania wyników zadania 2 w różnych formatach (PPKWU zadanie 3) - dokumentacja
Z API możemy skorzystać poprzez wysłanie zapytania GET, domyślnie pod adres localhost:8080.
Do skorzystania z niego potrzebujemy dwóch, maksymalnie trzech parametrów- ciągu tekstowego do analizy, określonego formatu docelowego oraz opcjonalnie podciągu tekstowego, którego API ma szukać. Format wymaga określenia w zapytaniu GET jednego z 4 parametrów:
txt- prosty plik tekstowy
json- plik formatu JSON
xml-plik formatu XML
csv-plik formatu CSV
Jeżeli format nie zostanie sprecyzowany, API nie wykona zadania i zwróci jedynie komunikat.
# Przykłady zastosowania
Wzór zastosowania http://localhost:8080/show_occurences/format/tekst_do_wpisania lub http://localhost:8080/show_occurences/format/tekst_do_wpisania/podtekst_do_szukania

R: http://localhost:8080/show_occurences/txt/aw2k9&MAaw/aw

A:
Special characters:1
Whitespaces:0
Combination:2
Digits:2
Lowercase letters:5
Uppercase letters:2

R: http://localhost:8080/show_occurences/json/aw2k9&MAaw

A:
{"Special characters":1,"Whitespaces":0,"Digits":2,"Lowercase letters":5,"Uppercase letters":2}

R: http://localhost:8080/show_occurences/xml/aw2k9&MAaw/aw

A:
<?xml[Space]version="1.0"[Space]encoding="UTF-8"?>
<Occurences>
<Special-characters>1</Special-characters>
<Whitespaces>0</Whitespaces>
<Combination>2</Combination>
<Digits>2</Digits>
<Lowercase-letters>5</Lowercase-letters>
<Uppercase-letters>2</Uppercase-letters>
</Occurences>

R: http://localhost:8080/show_occurences/csv/aw2k9&MAaw/aw

A:
"Special characters",1
"Whitespaces",0
"Combination",2
"Digits",2
"Lowercase letters",5
"Uppercase letters",2
