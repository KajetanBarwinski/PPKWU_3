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
<code>
	<pre>
	&lt;?xml[Space]version="1.0"[Space]encoding="UTF-8"?&gt;
		&lt;Occurences&gt;
		&lt;Special-characters&gt;1&lt;/Special-characters&gt;
		&lt;Whitespaces&gt;0&lt;/Whitespaces&gt;
		&lt;Combination&gt;2&lt;/Combination&gt;
		&lt;Digits&gt;2&lt;/Digits&gt;
		&lt;Lowercase-letters&gt;5&lt;/Lowercase-letters&gt;
		&lt;Uppercase-letters&gt;2&lt;/Uppercase-letters&gt;
	&lt;/Occurences&gt;
	</pre>
</code>

R: http://localhost:8080/show_occurences/csv/aw2k9&MAaw/aw

A:
"Special characters",1
"Whitespaces",0
"Combination",2
"Digits",2
"Lowercase letters",5
"Uppercase letters",2
