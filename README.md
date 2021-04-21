# PwSJ_Lab8

Zadanie 1. Utwórz dokument HTML z podlinkowaną biblioteką jQuery. W tym celu można
wykorzystać repozytorium CDN Google albo Microsoft. Linkowanie należy umieścić w
nagłówku dokumentu między znacznikami <head> </head>
<head>
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
</head>
W ciele dokumentu należy umieścić następujące treści:
<body>
<h2>Gdzie są fraszki?</h2>
<p>Że krótkie fraszki czynię, to, Jakubie, winisz? </p>
<p>Krótsze twoje nierówno, bo ich ty nie czynisz..</p>
<button>Ukryj</button>
</body>
W nagłówku jest możliwe umieszczanie skryptów JavaScript (JS) między znacznikami
<script> </script>. Umieść następujący skrypt i przetestuj działanie strony w
przeglądarce. Napisz w sprawozdaniu jak działa skrypt.
<script>
$(document).ready(function(){
$("button").click(function(){
$("p").hide();
});
});
</script>
Programowanie w językach skryptowych, dr R. Smyk, dr J. Paluszak
Podpowiedź - struktura dokumentu HTML wygląda tak:
<!DOCTYPE html>
<html>
<head>
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
<script>
$(document).ready(function(){
});
</script>
</head>
<body>
<h2></h2>
<p></p>
<p></p>
<p id="p1"></p>
<button></button>
</body>
</html>
Zadanie 2. Głównym zadaniem jQuery jest selekcja tagów HTML i wykonywanie na nich
różnych czynności. Przykładowo w Zadaniu 1 skrypt szukał tagów <p> i wykonywał na nich
metodę .hide(). Typowa składnia w JQuery: $(selector).action()
$(this).hide() - zaznacza i ukrywa aktualny element
("p").hide() - ukrywa wszystkie <p>
$(".test").hide() - ukrywa elementy class="test".
$("#test").hide() - ukrywa elementy z id="test".
Szkielet typowej funkcji jQuery można uprościć następująco:
$(function(){
// metody jQuery
});
Uruchom poniższy skrypt i opisz jego działanie w sprawozdaniu:
<script>
Programowanie w językach skryptowych, dr R. Smyk, dr J. Paluszak
$(document).ready(function(){
$("button").click(function(){
$("p").hide();
});
$("#p1").mouseenter(function(){
alert("J. Kochanowski");
});
});
</script>
Wymień metodę .mouseenter() na .hover() i wypróbuj jej działanie. Jest widoczna
różnica?
Zadanie 3. W jQuery można łatwo realizować różne efekty znikania, najazdu czy slide’u
stosując je do wybranych partii kontentu HTML. Przykładowe metody do slide’u:
slideDown(), slideUp(), slideToggle().
Uruchom poniższy skrypt i przetestuj w nim wymienione wyżej metody slide’u:
<!DOCTYPE html>
<html>
<head>
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
<script>
$(document).ready(function(){
$("#flip").click(function(){
$("#panel").slideDown("slow");
});
});
</script>
<style>
#panel, #flip {
padding: 5px;
text-align: center;
background-color: #e5eecc;
border: solid 1px #c3c3c3;
}
#panel {
padding: 50px;
display: none;
}
</style>
</head>
Programowanie w językach skryptowych, dr R. Smyk, dr J. Paluszak
<body>
<div id="flip">Dodatkowe opcje...</div>
<div id="panel">Rozwinąłeś panel dodatkowych ściśle tajnych opcji.</div>
</body>
</html>
Zadanie 4. Istnieją metody w jQuery umożliwoające dodawanie kontentu (zawartości)
dokumentu HTML. Jedną z takich metod jest .append(). Poniższy skrypt demonstruje
działanie tej metody. Uruchom skrypt, przetestuj działanie i zmodyfikuj go tak, żeby
dodawane były automatycznie wiersze tekstu do znacznika <p>.
<!DOCTYPE html>
<html>
<head>
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
<script>
$(document).ready(function(){
$("#btn1").click(function(){
$("ol").append("<li>Dodatkowy element listy</li>");
});
});
</script>
</head>
<body>
<p>Uzupełnianie listy dodatkowym kontentem</p>
<ol>
<li>Element listy 1</li>
<li>Element listy 2</li>
<li>Element listy 3</li>
</ol>
<button id="btn1">Dodaj do listy</button>
</body>
</html>
Programowanie w językach skryptowych, dr R. Smyk, dr J. Paluszak
Zadanie 5. Dodawanie klasy CSS do elementu HTML. Uruchom poniższy skrypt, który
dodaje klasy CSS do znaczników <h1>, <h2> i <p>. Zmodyfikuj skrypt tak, żeby <h1>
była kolorowana na ciemno zielono, <h2> na brązowo a <p> na ciemno-niebiesko.
<!DOCTYPE html>
<html>
<head>
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
<script>
$(document).ready(function(){
$("button").click(function(){
$("h1, h2, p").addClass("blue");
$("div").addClass("important");
});
});
</script>
<style>
.important {
font-weight: bold;
font-size: xx-large;
}
.blue {
color: blue;
}
</style>
</head>
<body>
<h1>Nagłówek 1</h1>
<h2>Nagłówek 2</h2>
<p>Wiersz tesktu.</p>
<p>Kolejny wiersz tekstu.</p>
<div>To jest tekst specjalny, ani wiersz ani nagłówek</div><br>
<button>Modyfikuj</button>
</body>
</html>
Programowanie w językach skryptowych, dr R. Smyk, dr J. Paluszak
Zadanie 6. Biblioteka jQueryUI jest uzupełnieniem jQuery o kilka przydatnych widget’ów
takich jak pobieranie daty (DataPicker), wyświetlanie kontentu w tab’ach lub harmonijce,
okno dialogowe (Dialog), progress bar i inne. Pełna funkcjonalność jQueryUI jest opisana tu:
https://jqueryui.com/
Uruchom poniższe przykłady. Zrealizuj jeden dokument HTML w którym w zakładkach
jest:
● w pierwszej zakładce tylko tekst
● w drugiej zakładce - tekst oraz pole do wpisywania daty (DatePicker)
● w trzeciej zakładce jest tekst umieszczony w oknie dialogowym
Przykład ‘DatePicker’
<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>jQuery UI Datepicker - Default functionality</title>
<link rel="stylesheet" href="https://code.jquery.com/ui/1.12.1/themes/base/jquery-ui.css">
<script src="https://code.jquery.com/jquery-1.12.4.js"></script>
<script src="https://code.jquery.com/ui/1.12.1/jquery-ui.js"></script>
<script>
$( function() {
$( "#datepicker" ).datepicker();
} );
</script>
</head>
<body>
<p>Data: <input type="text" id="datepicker"></p>
</body>
</html>
