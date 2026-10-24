# BAISM-CW-2




# SPRAWOZDANIE (czytać uważnie wytyczne):

FORMAT -> .pdf
NAZWA -> BAISM_<NumerCwiczenia>_<NumerIndeksu>_<Imie>_<Nazwisko>
STRONA TYTUŁOWA:
1. Nazwa przedmiotu
2. <Imię nazwisko indeks>
3. Zadanie <Numer ćwiczenia>
4. Source code <LINK DO PUBLICZNEGO PROJEKTU GITHUB>

# SOURCE CODE:
Source code projektu ma być wrzucony na publiczne repozytorium GitHub i na pierwszej stronie sprawozdania podlinkowany.

## Nazwa projektu na GitHub: BAISM-CW-<NumerCwiczenia> (patrz na nazwe zadania, na końcu jest zawsze numer ćwiczenia)

# TREŚĆ ZADANIA

1. Opis każdego kroku, który podjąłeś wraz ze screenshotami - po kolei piszesz co robiłeś, jakie komendy wzywałeś oraz dokumentujesz to za pomocą wykonanych zrzutów ekranu.
UWAGA! Brak zrzutów ekranu na potwierdzenie wykonania kolejnych etapów zadania własnoręcznie = OCENA 2.0. Ważny jest dla mnie aspekt tego, abyście nawet krok po kroku wykonali to zadanie własnoręcznie.
Jeśli w sprawozdanie jest napisane, że wzywasz jakąś komendę/instalujesz coś to ma mieć to odzwierciedlenie w dokumentacji wizualnej (tzn. zdjęcie).
Kod źródłowy aplikacji ma być wrzucony na publicznie dostępne repozytorium GitHub.

1. Skonfiguruj i odpal MobSF lokalnie na swojej maszynie (najłatwiejsza opcja to przez Dockera)
2. Przenalizuj aplikacje przekazaną w .zip, skup się na critical/high - opisz czego dowiedziałeś się o tej aplikacji, jakie ma potencjalne podatności. Dowiedz się co one oznaczają, na co pozwalają.
3. Sporządź sprawozdanie - co, jest nie tak w aplikacji. Zaproponuj w jaki sposób zmitygować znalezione problemy, poczytaj o wymienionych problemach spróbuj dowiedzieć się jak najwięcej ze wszelkich wiarygodnych źródeł.

4. Zarejestruj się na stronie https://app.bitrise.io/

Załóż darmowe konto w planie Hobby (około 300 darmowych kredytów ma miesiąc super opcja pod mobilne CI/CD dla małych projektów).

Wykonaj prostą aplikacje lub użyj już istniejącej, która posłuży nam jako źródło kodu w CI/CD.
Technologia z góry narzucona: Kotlin, Android.
Ważne, aby napisane były jakieś proste testy, które będą w ramach całego procesu uruchamiane.

Polecam poczytać sobie https://developer.android.com/training/testing/fundamentals?hl=pl
Nas interesują proste Unity Testy, ale można również napisać Instrumented Tests - jeśli ktoś chce zgłębiać wiedzę, a wierzę, że każdy z was to chce ;)

Dodaj dostęp do wybranego repozytorium z kodem - najlepiej zgodnie z najlepszymi praktykami administrowania, tylko do wskazanego repozytorium, a nie na cały profil.
Skonfiguruj podstawowe flow (będą domyślnie już istniejące, na których możesz się wzorować) - nazwij je "safe_build".


Co ma wykonać workflow:

1. Sklonuj repozytorium
2. Uruchom Unit testy (i inne jeśli takie posiadasz) - fail CI/CD jeśli nie przeszło.
3. Uruchom Mobsfscan - fail CI/CD jeśli nie przeszło.
4. Zbuduj aplikacje (.apk)
5. Deploy to bitrise.io

Ustaw trigger workflow:
Jeśli jest PR do main to uruchom workflow.
Panel boczny -> Triggers -> Add new trigger -> Pull request -> Target (safe_build) -> Target branch (main)

Jeśli prawidłowo wszystko skonfigurowałeś to po utworzeniu na GitHub nowego PR do brancha main, w dashboardzie bitrise powinieneś zobaczyć, że twój workflow ruszył.

W ramach sprawozdania uruchom workflow minimum 2 razy:
1. Tak, aby testy były prawidłowe - happy path
2. Specjalnie zepsuj test, aby workflow przerwał działanie i "sfailował"


Gratulację, właśnie zautomatyzowałeś swój pierwszy proces budowania aplikacji z security testami.