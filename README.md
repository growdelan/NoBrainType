# NoBrainType

Ultra‑prosta aplikacja do ćwiczenia pisania na klawiaturze z własnym tekstem. Działa w 100% w przeglądarce (bez serwera, bez zależności) i startuje 30‑sekundowy test po pierwszym naciśnięciu klawisza.

**Plik aplikacji:** `nobraintype.html`


## Szybki start
- Otwórz plik `nobraintype.html` w nowoczesnej przeglądarce (Chrome, Edge, Firefox, Safari).
- Wklej swój tekst lub użyj „Wstaw przykładowy tekst”.
- Kliknij „Przygotuj test”, a następnie zacznij pisać — licznik wystartuje automatycznie.
- Po 30 s zobaczysz wynik WPM oraz statystyki.

Opcjonalnie możesz uruchomić prosty serwer statyczny (nie jest wymagany):
- Python: `python3 -m http.server 8080` i otwórz `http://localhost:8080/nobraintype.html`


## Funkcje
- **Własny materiał:** wklej dowolny tekst lub użyj wbudowanej próbki.
- **Automatyczna normalizacja:** usuwa interpunkcję i polskie ogonki, zamienia „ł/Ł” na „l/L”, sprowadza do małych liter, kompresuje wielokrotne spacje.
- **30‑sekundowy test:** licznik startuje przy pierwszym znaku; czytelny HUD z pozostałym czasem.
- **Podgląd 5 linii:** płynny auto‑scroll utrzymuje bieżący znak w oknie widoku.
- **WPM i statystyki:** wynik WPM + liczba poprawnych i błędnych znaków oraz czas.
- **Skróty edycji:** `Backspace` cofa znak, `Alt/Opt+Backspace` cofa całe słowo (z pominięciem spacji); blokada wklejania podczas testu.
- **Mobile‑friendly:** ukryte pole wejściowe utrzymuje aktywną klawiaturę ekranową.
- **Brak zależności:** czysty HTML/CSS/JS w jednym pliku, działa offline.
- **Ponów test w trakcie:** podczas testu na dole dostępny jest przycisk „Ponów test” skrót (TAB+Enter).


## Sterowanie i skróty
- **Przygotowanie testu:** przycisk „Przygotuj test”.
- **Szybkie przygotowanie:** w polu tekstowym naciśnij `Enter` + (`Ctrl`/`Cmd` lub `Shift`).
- **Cofanie:**
  - `Backspace` — usuwa jeden znak (cofa wynik dla tego znaku),
  - `Alt/Opt+Backspace` — usuwa całe słowo (najpierw usuwa spacje po lewej, potem słowo).
- **Powtórka:** „Jeszcze raz” — start z tym samym znormalizowanym tekstem.
- **Edycja:** „Edytuj tekst” — powrót do ekranu wklejania.
- **Ponów test:** podczas trwania testu naciśnij `Tab`, potem `Enter` na „Ponów test”, aby zrestartować licznik i zacząć natychmiast.


## Jak liczone jest WPM
- **WPM:** `(poprawne_znaki / 5) / minuty` liczony na podstawie czasu, który upłynął od pierwszego znaku.
- **Poprawność:** każdy znak porównywany jest ze znormalizowaną wersją materiału (bez ogonków i interpunkcji, małe litery, pojedyncze spacje).


## Zgodność i wymagania
- **Przeglądarki:** nowoczesne przeglądarki desktop i mobile. Wykorzystywane są m.in. `String.prototype.normalize('NFD')`, `performance.now()`, `addEventListener` i współczesny CSS.
- **Sieć:** nie wymaga połączenia z internetem.
- **Prywatność:** wszystko działa lokalnie w przeglądarce; żadne dane nie są nigdzie wysyłane.


## Dostosowanie
- **Czas testu:** w `nobraintype.html` zmień wartość `duration = 30_000` (ms).
- **Wygląd:** paleta kolorów w `:root` (zmienne CSS: `--bg`, `--fg`, `--muted`, `--bad`, `--accent`).
- **Przykładowy tekst:** zmień stałą `sample` w skrypcie.


## Struktura projektu
- `nobraintype.html` — jedyny plik zawierający HTML, style i skrypt JS.
 - `nobraintype_v2.html` — wariant z przyciskiem „Ponów test” (restart w trakcie testu, obsługa Tab/Enter).


## Rozwój
- Nie ma procesu build. Edytuj `nobraintype.html` i odśwież stronę.
- Dla wygody podczas pracy możesz użyć lokalnego serwera statycznego (np. `python3 -m http.server`).


## Licencja
Brak dołączonej licencji. Jeśli planujesz publikację/udostępnianie, dodaj odpowiedni plik licencji (np. MIT, Apache‑2.0).
