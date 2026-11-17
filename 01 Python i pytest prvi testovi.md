# Python i pytest: prvi testovi

Nov 15, 2026 · @Vanja

## Šta ćeš naučiti

Kad prođeš ovaj materijal, umećeš da napišeš program koji sam proverava drugi program i kaže ti šta ne radi.

1. Instaliraš Python i pytest na svoj računar.
2. Napišeš i pokreneš prvi program u VS Code-u.
3. Napišeš prvi automatski test i pročitaš izveštaj.
4. Testiraš deo školskog e-dnevnika i pronađeš greške u njemu.

**Šta ti treba:** računar sa Windows 10 ili novijim, internet, Visual Studio Code i oko 20 minuta za instalaciju.

**Kako se čita ovaj materijal:** sve što kucaš prikazano je u sivom polju. Komande za terminal kucaš tačno kako piše, pa pritisneš Enter.

## 1. Instalacija Pythona

Python se instalira jednom. Preporučeni način je program **Python install manager**, koji sam preuzima i održava Python.

### Korak po korak

1. Otvori stranicu [python.org/downloads/windows](https://www.python.org/downloads/windows/).
2. Pri vrhu strane pronađi **Python install manager** i preuzmi **Installer (MSIX)**. Isti program postoji i u aplikaciji Microsoft Store.
3. Dvaput klikni na preuzetu datoteku, pa na **Install**.
4. Otvori komandnu liniju: klikni na Start, ukucaj `cmd` i pritisni Enter.
5. Ukucaj `python` i pritisni Enter. Pošto Pythona još nema na računaru, najnovija verzija se sama preuzima i instalira. Sačekaj da se završi.
6. Ako se pojavi pitanje o dodavanju fascikle u PATH, prihvati. Tako će Windows uvek znati gde je Python.
7. Kad se pojave tri strelice `>>>`, Python radi. Ukucaj prvu naredbu:

```python
print("Zdravo")
```

8. Python odgovara `Zdravo`. Izađi naredbom `exit()`.

### Provera

Zatvori komandnu liniju i otvori je ponovo. Ukucaj:

```text
py --version
```

Treba da dobiješ odgovor oblika `Python 3.15.2` (broj može biti veći). Komanda `py list` prikazuje sve instalirane verzije.

### Drugi način: klasični instalater

Ako prvi način ne radi (na primer, računar ne dozvoljava instalaciju MSIX paketa):

1. Na istoj stranici, kod najnovije verzije, preuzmi **Windows installer (64-bit)**.
2. Pokreni ga. U prvom prozoru, na dnu, uključi polje za dodavanje Pythona u PATH.
3. Klikni na **Install Now** i sačekaj kraj.
4. Proveri komandom `py --version`, kao gore.

### Stariji Windows

| Windows | Koji Python instaliraš |
| --- | --- |
| 10 i 11 | Najnoviji |
| 8.1 | 3.12 |
| 7 | 3.8 |

Za starije verzije koristi se klasični instalater te verzije sa python.org.

## 2. Instalacija pytest-a

pytest je dodatak za Python koji pronalazi tvoje testove, pokreće ih i pravi izveštaj. Instalira se jednom komandom, uz internet.

1. Otvori komandnu liniju (Start, `cmd`, Enter).
2. Ukucaj:

```text
py -m pip install pytest
```

3. Sačekaj poruku koja počinje sa `Successfully installed`.
4. Proveri:

```text
py -m pytest --version
```

Odgovor je oblika `pytest 9.1.1` (broj može biti veći).

**Šta znači komanda:** `py` pokreće Python, `-m pip` kaže Pythonu da pokrene svoj program za instalaciju dodataka (pip), a `install pytest` je nalog šta da instalira. Umesto `py` možeš pisati i `python`.

## 3. Podešavanje VS Code-a

VS Code postaje okruženje za Python kada mu dodaš dodatak „Python“ i otvoriš fasciklu u kojoj radiš. Ako nemaš VS Code, preuzmi ga sa [code.visualstudio.com](https://code.visualstudio.com/).

1. **Dodatak.** Pritisni `Ctrl+Shift+X`. U polje za pretragu ukucaj `Python`. Izaberi dodatak **Python** izdavača Microsoft i klikni na **Install**.
2. **Fascikla.** Napravi fasciklu `testiranje` (na primer u Dokumentima). U VS Code-u izaberi **File > Open Folder** i otvori je.
3. **Interpreter.** Pritisni `Ctrl+Shift+P`, ukucaj `Python: Select Interpreter` i izaberi instalirani Python.
4. **Terminal.** Pritisni `` Ctrl+Shift+`  `` (taster levo od broja 1) ili izaberi **Terminal > New Terminal**. Terminal se otvara na dnu prozora, već u tvojoj fascikli.

Ako je VS Code bio otvoren tokom instalacije Pythona, zatvori ga i otvori ponovo.

### Delovi prozora

| Deo | Gde je | Čemu služi |
| --- | --- | --- |
| Explorer | Levo | Spisak datoteka u fascikli; dugme **New File** pravi novu |
| Editor | Sredina | Ovde pišeš kod |
| Dugme ▶ **Run Python File** | Gore desno | Pokreće datoteku koja je otvorena |
| Terminal | Dole | Ovde se vidi rezultat programa i ovde kucaš komande |
| Testing (ikonica epruvete) | Krajnje levo | Pokretanje testova klikom; nije obavezno |

## 4. Prvi program: zbir dva broja

Program u Pythonu je obična tekstualna datoteka čije se ime završava na `.py`.

1. U Explorer-u klikni na **New File** i nazovi datoteku `zbir.py`.
2. Ukucaj:

```python
a = 5
b = 7
zbir = a + b
print("Zbir je:", zbir)
```

3. Sačuvaj (`Ctrl+S`).
4. Klikni na dugme ▶ **Run Python File** gore desno.
5. U terminalu se pojavljuje:

```text
Zbir je: 12
```

| Red | Šta radi |
| --- | --- |
| `a = 5` | Pravi promenljivu `a` sa vrednošću 5. Tip se ne piše i nema tačke-zareza. |
| `b = 7` | Isto za `b`. |
| `zbir = a + b` | Sabira i pamti rezultat. |
| `print("Zbir je:", zbir)` | Ispisuje tekst i vrednost, sa razmakom između. |

### Brojevi sa tastature

```python
a = int(input("Unesi prvi broj: "))
b = int(input("Unesi drugi broj: "))
zbir = a + b
print("Zbir je:", zbir)
```

Posle pokretanja klikni u terminal, ukucaj broj i pritisni Enter. `input` uvek vraća tekst, a `int` ga pretvara u ceo broj. Bez `int` bi `"5" + "7"` dalo `57`, jer se tekstovi spajaju.

### Probaj sam

- Promeni program da ispiše i razliku i proizvod.
- Obriši `int` i pogledaj šta se dešava.
- Pokreni program iz terminala komandom `py zbir.py`.

## 5. Python za one koji znaju C#

Sve što znaš iz C# važi i ovde; menja se samo način pisanja. Najvažnija razlika: umesto vitičastih zagrada Python koristi dvotačku i uvlačenje od 4 razmaka.

| C# | Python | Napomena |
| --- | --- | --- |
| `int x = 5;` | `x = 5` | Nema tipa ni tačke-zareza |
| `{ ... }` | dvotačka i uvlačenje od 4 razmaka | Uvlačenje je deo jezika |
| `if (a) {...} else if (b) {...} else {...}` | `if a:` … `elif b:` … `else:` | Bez zagrada oko uslova |
| `&&`, `\|\|`, `!` | `and`, `or`, `not` |  |
| `true`, `false`, `null` | `True`, `False`, `None` | Veliko početno slovo |
| `int[] ocene = { 5, 5, 1 };` | `ocene = [5, 5, 1]` | Lista |
| `ocene.Length` | `len(ocene)` |  |
| `ocene[ocene.Length - 1]` | `ocene[-1]` | Negativan indeks broji od kraja |
| `foreach (int o in ocene)` | `for o in ocene:` |  |
| `public static int F(int[] a, bool b)` | `def f(a, b):` | Bez tipova i modifikatora |
| `return x;` | `return x` |  |
| `throw new ArgumentException("...");` | `raise ValueError("...")` |  |
| `(double)zbir / n` | `zbir / n` | `/` uvek daje realan broj: `5 / 2` je 2.5 |
| `zbir / n` (celi brojevi) | `zbir // n` | Celobrojno deljenje: `5 // 2` je 2 |
| `Math.Round(x)` | `round(x)` |  |
| `// komentar` | `# komentar` |  |
| `Console.WriteLine(x);` | `print(x)` |  |
| `using ...;` | `from kalkulator import saberi` | Uvoz funkcije iz datoteke `kalkulator.py` |
| `ZakljucnaOcena` | `zakljucna_ocena` | Imena se pišu malim slovima sa donjom crtom |

Brze probe: u terminal ukucaj `py`, pa posle `>>>` piši izraze, na primer `5 / 2` ili `len([4, 4, 4])`. Izlaz je `exit()`.

## 6. Prvi test

Test je mali program koji poziva tvoj kod i proverava da li je rezultat onakav kakav treba da bude. Da bi kod mogao da se testira, račun stavljamo u funkciju.

### Funkcija koju testiramo

Nova datoteka `kalkulator.py`:

```python
def saberi(a, b):
    return a + b
```

### Testovi

Nova datoteka `test_kalkulator.py`, u istoj fascikli:

```python
from kalkulator import saberi


def test_saberi_dva_pozitivna_broja():
    assert saberi(5, 7) == 12


def test_saberi_sa_negativnim_brojem():
    assert saberi(5, -7) == -2
```

Naredba `assert` znači „tvrdim da je ovo tačno“. Ako jeste, ništa se ne dešava. Ako nije, test pada.

### Pokretanje

Sačuvaj obe datoteke. U terminalu ukucaj:

```text
py -m pytest
```

```text
collected 2 items

test_kalkulator.py ..                                                    [100%]

============================== 2 passed in 0.03s ===============================
```

Svaka tačka je jedan test koji je prošao.

### Tri pravila

| Pravilo | Ako ga prekršiš |
| --- | --- |
| Ime datoteke počinje sa `test_` | pytest ne vidi datoteku |
| Ime funkcije počinje sa `test_` | pytest ne vidi test |
| U testu postoji `assert` | Test uvek prolazi i ništa ne proverava |

### Šta se desi kad program ima grešku

Namerno pokvari program: u `kalkulator.py` promeni `+` u `-`, sačuvaj i ponovo pokreni `py -m pytest`.

```text
test_kalkulator.py FF                                                    [100%]

=================================== FAILURES ===================================
_______________________ test_saberi_dva_pozitivna_broja ________________________

    def test_saberi_dva_pozitivna_broja():
>       assert saberi(5, 7) == 12
E       assert -2 == 12
E        +  where -2 = saberi(5, 7)

test_kalkulator.py:5: AssertionError
```

### Kako se čita izveštaj

| Deo izveštaja | Šta kaže |
| --- | --- |
| `FF` | Oba testa su pala (`.` prošao, `F` pao) |
| Red sa `>` | Naredba na kojoj je test pao |
| `E assert -2 == 12` | Program je vratio −2, a očekivano je 12 |
| `where -2 = saberi(5, 7)` | Odakle je došla vrednost −2 |
| `test_kalkulator.py:5` | Datoteka i broj reda |

Vrati `+` i pokreni testove ponovo: opet `2 passed`. Testovi su ti upravo javili da je program pokvaren, a zatim potvrdili da je popravljen.

## 7. Program koji testiramo: e-dnevnik

Sada si tester. Dobijaš tuđi program i spisak zahteva koje on mora da ispuni. Program možda ima grešaka, a tvoj posao je da ih pronađeš testovima.

### Zahtevi za funkciju `zakljucna_ocena(ocene, takmicenje)`

| ID | Zahtev |
| --- | --- |
| Z1 | Ulaz: lista ocena po redu upisivanja i podatak da li učenik ima nagradu na takmičenju (`True` ili `False`). |
| Z2 | Ako je lista `None` ili ima manje od 3 ocene, vraća 0 (učenik je neocenjen). |
| Z3 | Ako je bilo koja ocena van opsega 1–5, baca izuzetak `ValueError`. |
| Z4 | Ako učenik ima najmanje dve jedinice **i** poslednja ocena mu je 1, zaključna je 1. |
| Z5 | Inače je zaključna prosek zaokružen na ceo broj; x,50 se zaokružuje naviše (4,50 → 5; 4,49 → 4). |
| Z6 | Ako učenik ima nagradu i prosek je najmanje 4,00, zaključna se povećava za 1, ali ne preko 5. |

### Zahtevi za funkciju `opsti_uspeh(zakljucne)`

| ID | Zahtev |
| --- | --- |
| U1 | Ako je bilo koja zaključna ocena 1, uspeh je `"nedovoljan"`. |
| U2 | Inače prema proseku: od 4,50 `"odlican"`; 3,50–4,49 `"vrlo dobar"`; 2,50–3,49 `"dobar"`; 2,00–2,49 `"dovoljan"`. |
| U3 | Ako je lista prazna, baca izuzetak `ValueError`. |

### Kod: datoteka `ocene.py`

Ovu datoteku dobijaš od nastavnika. Ne menjaj je dok nastavnik ne kaže.

```python
def zakljucna_ocena(ocene, takmicenje):
    if ocene is None or len(ocene) < 3:
        return 0
    zbir = 0
    jedinice = 0
    for ocena in ocene:
        if ocena < 1 or ocena > 5:
            raise ValueError("Neispravna ocena")
        zbir += ocena
        if ocena == 1:
            jedinice += 1
    prosek = zbir / len(ocene)
    if jedinice >= 2 or ocene[-1] == 1:
        return 1
    zakljucna = round(prosek)
    if takmicenje and prosek > 4.0 and zakljucna < 5:
        zakljucna += 1
    return zakljucna


def opsti_uspeh(zakljucne):
    zbir = 0
    for ocena in zakljucne:
        if ocena == 1:
            return "nedovoljan"
        zbir += ocena
    prosek = zbir / len(zakljucne)
    if prosek >= 4.5:
        return "odlican"
    elif prosek >= 3.5:
        return "vrlo dobar"
    elif prosek >= 2.5:
        return "dobar"
    return "dovoljan"
```

## 8. Testovi za e-dnevnik

Svaki test ima tri dela: pripremi ulaze (Arrange), pozovi funkciju (Act), proveri rezultat (Assert). Očekivanu vrednost uvek uzimaš iz zahteva, nikad iz pokretanja programa.

### Test u tri koraka

Nova datoteka `test_ocene.py`, u istoj fascikli kao `ocene.py`:

```python
import pytest
from ocene import zakljucna_ocena, opsti_uspeh


def test_tri_petice_daju_5():
    # Arrange (pripremi)
    ocene = [5, 5, 5]
    # Act (izvrsi)
    rezultat = zakljucna_ocena(ocene, False)
    # Assert (proveri)
    assert rezultat == 5
```

Kratak test može da stane u jedan red:

```python
def test_manje_od_tri_ocene_vraca_0():
    assert zakljucna_ocena([5, 5], False) == 0
```

Ime testa kaže šta se proverava i šta se očekuje. Jedan test proverava jednu stvar.

### Provera izuzetka

Kad zahtev kaže da funkcija baca izuzetak (Z3), test izgleda ovako:

```python
def test_ocena_6_baca_izuzetak():
    with pytest.raises(ValueError):
        zakljucna_ocena([5, 6, 4], False)
```

Test prolazi samo ako poziv zaista baci `ValueError`.

### Više redova podataka u jednom testu

Kad istu proveru radiš za više ulaza, napiši tabelu podataka. Svaki red postaje poseban test u izveštaju.

```python
@pytest.mark.parametrize("ocene, ocekivano", [
    ([], 0),          # nema ocena
    ([5], 0),         # jedna ocena
    ([5, 5], 0),      # dve ocene
    ([5, 5, 5], 5),   # tri ocene
])
def test_broj_ocena(ocene, ocekivano):
    assert zakljucna_ocena(ocene, False) == ocekivano
```

Sa `py -m pytest -v` vidiš svaki red posebno:

```text
test_ocene.py::test_broj_ocena[ocene0-0] PASSED                          [ 20%]
test_ocene.py::test_broj_ocena[ocene1-0] PASSED                          [ 40%]
test_ocene.py::test_broj_ocena[ocene2-0] PASSED                          [ 60%]
test_ocene.py::test_broj_ocena[ocene3-5] PASSED                          [ 80%]
```

### Kad test padne

1. Pročitaj u izveštaju šta je program vratio, a šta je očekivano.
2. Proveri zahtev: da li je tvoja očekivana vrednost tačna?
3. Ako jeste, to je greška u programu. Ne menjaj test da bi prošao. Upiši nalaz u tabelu:

| Test | Zahtev | Ulaz | Očekivano | Dobijeno |
| --- | --- | --- | --- | --- |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |

### Kostur testa

```python
# zahtev: ____
def test_____________________():
    # Arrange

    # Act

    # Assert
    assert ____ == ____
```

### Korisne komande

| Komanda | Šta radi |
| --- | --- |
| `py -m pytest` | Pokreće sve testove u fascikli |
| `py -m pytest -v` | Ispisuje ime i rezultat svakog testa |
| `py -m pytest -x` | Staje na prvom testu koji padne |
| `py -m pytest -k ocena_6` | Pokreće samo testove čije ime sadrži `ocena_6` |

## 9. Zadaci

Zadaci idu od lakših ka težim. Sve testove pišeš u `test_ocene.py` i posle svakog zadatka pokrećeš `py -m pytest`.

### ★ Zadatak 1: Šta vraća izraz?

Prvo proceni, pa proveri u terminalu (`py`, pa izraz posle `>>>`).

| Izraz | Moja procena | Python kaže |
| --- | --- | --- |
| `5 / 2` |  |  |
| `5 // 2` |  |  |
| `round(2.5)` |  |  |
| `round(3.5)` |  |  |
| `[5, 5, 1][-1]` |  |  |
| `len([4, 4, 4])` |  |  |
| `0.1 + 0.2 == 0.3` |  |  |

### ★ Zadatak 2: Testovi za Z2 i Z4

Napiši tri testa:

1. Učenik bez ocena (`None`) je neocenjen.
2. Dve jedinice, od kojih je poslednja ocena 1, daju zaključnu 1.
3. Dve jedinice koje su kasnije popravljene ne daju zaključnu 1. Sam izračunaj šta treba da bude rezultat.

Koji testovi prolaze? Za svaki koji padne popuni red u tabeli nalaza.

### ★★ Zadatak 3: Zaokruživanje na granici

Napiši po jedan test za proseke 2,50, 3,50 i 4,50. Sam izaberi ocene koje daju te proseke. Očekivane vrednosti odredi po zahtevu Z5. Koji testovi padaju?

### ★★ Zadatak 4: Tabela i izuzetak

1. Tri testa iz zadatka 3 zameni jednim testom sa tabelom podataka i dodaj red za prosek 4,40.
2. Napiši test koji proverava da ocena 0 baca `ValueError`.

### ★★ Zadatak 5: Nagrada na takmičenju

Napiši test sa tabelom od četiri reda za zahtev Z6: prosek tačno 4,00; prosek ispod 4,00; prosek između 4,00 i 4,50; sve petice. Nagrada je u svim redovima `True`.

### ★★★ Zadatak 6: Test koji prolazi iako greška postoji

Zadatak 3 otkriva grešku u zaokruživanju. Pronađi ulaz **sa nagradom** kod koga se ta greška desi u računu, a konačan rezultat je ipak tačan. Objasni zašto. Šta ti to govori o testovima koji prolaze?

### ★★★ Zadatak 7: Testovi za `opsti_uspeh`

Po zahtevima U1–U3 napiši tri testa: prosek tačno 4,50; jedna jedinica; prazna lista. Šta piše u izveštaju za treći test? Da li je program bacio izuzetak koji zahtev traži?

## 10. Ako nešto ne radi

Većina problema na početku je jedna od ovih devet stvari.

| Šta vidiš | Uzrok | Rešenje |
| --- | --- | --- |
| Komanda `py` ili `python` „nije prepoznata“, ili se otvara Microsoft Store | Windows ne nalazi Python | Start, ukucaj „Manage app execution aliases“, uključi stavke „Python (default)“. Zatvori i ponovo otvori terminal. |
| `No module named pytest` | pytest nije instaliran | `py -m pip install pytest` |
| `no tests ran` | pytest nije našao testove | Ime datoteke i ime funkcije moraju početi sa `test_`. Proveri da je terminal u pravoj fascikli. |
| `ModuleNotFoundError: No module named 'kalkulator'` | Datoteke nisu u istoj fascikli ili terminal nije u njoj | Otvori fasciklu sa **File > Open Folder**, pa otvori novi terminal |
| `IndentationError` | Pogrešno uvlačenje | Redovi unutar funkcije moraju biti uvučeni 4 razmaka, svi jednako |
| `SyntaxError` | Nedostaje dvotačka na kraju reda sa `def`, `if`, `for`; ili `=` umesto `==` | Proveri red koji izveštaj pokazuje |
| `NameError: name 'true' is not defined` | Navika iz C# | `True`, `False`, `None` |
| Kod je izmenjen, a rezultat je isti | Datoteka nije sačuvana | `Ctrl+S`, pa ponovo pokreni |
| Nema dugmeta ▶ | Nije instaliran dodatak Python ili ime datoteke ne završava na `.py` | Vrati se na odeljak 3 |

## 11. Mali rečnik

Ove reči ćeš viđati u izveštaju pytest-a i u dokumentaciji.

| English | Srpski |
| --- | --- |
| assertion | tvrdnja, provera |
| test runner | pokretač testova |
| collected 3 items | pronađena 3 testa |
| passed / failed | prošao / pao |
| failure report | izveštaj o padu |
| short test summary | kratak pregled testova |
| exception / to raise | izuzetak / baciti izuzetak |
| indentation | uvlačenje |
| expected / actual | očekivano / stvarno |
| interpreter | program koji izvršava Python kod |
| extension | dodatak (u VS Code-u) |
| module | modul (datoteka sa Python kodom) |

Zvanična uputstva: [Python na Windows-u](https://docs.python.org/3/using/windows.html), [Python u VS Code-u](https://code.visualstudio.com/docs/python/python-tutorial), [pytest – Get Started](https://docs.pytest.org/en/stable/getting-started.html).
