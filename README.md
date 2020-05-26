# Semestrální projekt - Zobrazení dat

# Generátor
Program pro vygenerování testovacích dat pro aplikaci.
## Instalace
Program vyžaduje instalaci .NET framework verze [4.6.1](https://dotnet.microsoft.com/download/dotnet-framework/thank-you/net461-web-installer) nebo vyšší.
Dále je třeba vytvořit databázi. Create script lze stáhnout [zde](https://github.com/JaroslavVondrakcz/dbs_semestralni_projekt_aplikace/blob/master/CREATE_SCRIPT.sql). Vytvořené tabulky se musí nacházet v schématu "mydb".

## Spuštění generátoru
V konfiguračním souboru conf.txt zadejte přístupové údaje do databáze ve formátu: 

```bash
[IP-adresa]
mydb
[uživatel]
[heslo]
```
## Nastavení a funkce generátoru
V hlavním menu se nachází možnost "nastaveni generatoru". V tomto nastavení lze změnit počet vygenerovaných strojů a čas generace. Po spuštění generace program vypíše, že generace byla spuštěna. Po vypršení časového liminu se vypíše kolik záznamů bylo uloženo do databáze. \
Během generace se může zobrazit oznámení, že nastala chyba při vložení záznamu do databáze, jelikož se program pokusit uložit duplicitní primární klíč. To je způsobeno tím, že se vygeneroval čas a datum, který se již pro daný stroj a IoT jednotku v databázi vyskytuje. Tuto hlášku lze ignorovat a nemá vliv na generování záznamů.

# Aplikace IoTDataViewer
Aplikace zobrazující přijatá data z IoT jednotek.

## Instalace

viz Generátor - instalace

## Spuštění aplikace 
V konfiguračním souboru conf.txt zadejte přístupové údaje do databáze ve formátu: 

```bash
[IP-adresa]
mydb
[uživatel]
[heslo]
```
Pokud je nastavení správné, tak se po spuštění aplikace načtou příslušná data.

## Ovládání aplikace - Zobrazení
### základní zobrazení
V záložce zobrazení je k dispozici seznam o získaných datech z IoT jednotek. Seznam lze různě třídit a řadit pomocí různých atributů.
Po zvolení všech požadovaných kritérií zvolte záložku "Základní" a klikněte na tlačítko "Hledat". Program poté zobrazí požadovaná data.
### zobrazení tenzometrů
V záložce "Tenzometry" lze vyhledat hodnoty tenzometrů podle zvolených požadavků. V záložce "Základní" zvolte datum, čas, Stroj, IoT jednotku. Poté v záložce "Tenzometry" vyberte požadovanou hodnotu a klikněte na tlačítko "Hledat" (tentokrát pod záložkou "Tenzometry"). V tabulce se nyní zobrazí data tenzometrů z požadovaného stroje/strojů.

## Ovládání aplikace - Stroje, IoT jednotky
Aby byla data z IoT jednotky uložena, je třeba přidat stroj, ze kterého se budou data odesílat, a příslušnou IoT jednotku. Přidávat, upravovat a odstraňovat stroje nebo IoT jednotky lze v menu pod názvem "Stroje" nebo "IoT jednotky".

## Ovládání aplikace - Graf
V programu je k dispozici zobrazení grafů, které ukazují Aktuální stav strojů (kolik strojů orá, seje, v pohybu atd...). Dále je k dispozici graf, kde lze vidět 7 nejslabších baterií IoT jednotek. Poslední graf pak zobrazuje průběhy tenzometrů v čase. Pro zobrazení vyberte požadovaný stroj, datum a klikněte na tlačítko "Zobrazit".

# Zdrojové kódy
[Generátor](https://github.com/JaroslavVondrakcz/dbs_semestralni_projekt_generator)\
[IoTDataViewer](https://github.com/JaroslavVondrakcz/dbs_semestralni_projekt)
