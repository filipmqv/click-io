[ENG] Simple multiplayer game - click on appearing rectangles and gain points. Be faster then opponents. 

Libs: nodeJS + socket.io + fabric.js (for canvas)


[PL] Gra przystosowana do umieszczenia na serwerze heroku (drobne zmiany)

uruchom serwer:		npm start

heroku (zmienione linie kodu względem pracy na localhoscie):
app.js cookie    domain: 'click-io.herokuapp.com'
public/javascripts/script.js socketio var socket = io.connect('http://click-io.herokuapp.com');
bin/www var port = normalizePort(process.env.PORT || '80');
Procfile 		web: node bin/www

ZADANIA (TASKS):
--pokoje to URL inny niż /
--/ to strona powitalna 
--event on mouse down jeśli jest obiekt to jeden socket event, jeśli nie, to inny. 
--serwer wykrywa maks wymiary planszy z wymiarów okien userow. 
--serw losowo wstawia nowe obiekty na plansze i czeka na pierwszy event kliknięcia w niego, daje pkt

--user wchodzi na url pokoju
--dostaje strone game
--serwer on connection dodaje usera do tablicy userow (cookie), wysyla 'first'
--user on 'first' wysyla swoje wymiary canvasa, id pokoju
--serwer: (jesli nie ma jeszcze takiego pokoju to musi go utworzyc); zapisuje sobie wymiary (dla konkretnego pokoju)(do algorytmu), jesli user loguje sie do tego samego pokoju co ostatnio to ok, wpp usun tamten wynik gry i dodaje usera do tablicy pokoju, odsyla aktualnie przebywajacych userow, ich punkty, a pozostalym userom wysyla tez zapdejtowana liste userow (metoda ogólna na rozglaszanie wynikow)
--user po otrzymaniu zapisuje sobie liste userow w pokoju i ich punkty

--user - id z cookie, wymiary ekranu, w jakim pokoju gra, punkty, 

--serwer okresowo wysyla do wszystkich gier losowe figury
--user po kliknieciu w canvas wysyla powiadomienie (jesli trafil/ nie trafil w figure)




server okresowo usuwa dawno niezalogowanych userow i dawno nieuzywane puste pokoje

--po podłączeniu wyemituj wszystkie obiekty ktore są w pokoju

--wyniki zawsze na wierzchu
--rozna liczba pkt w zaleznosci od wielkosci obiektu - im mniejszy tym wiecej pkt; można tez od czasu - im szybciej tym wiecej pkt

--powiadomienie ze sie zdobyło ileś pkt

--PUNKTY przypisane do konkretnego pokoju!!!, żeby nie było przenoszenia pkt między pokojami

różne figury

--pokazanie kliknięć innych userów w formie animowanych kółek

czas (ograniczony czas pojedynczej rundy)
