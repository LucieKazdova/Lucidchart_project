# ERD – Knihovní systém

## Účel úkolu
Cílem tohoto úkolu bylo vytvořit **ERD diagram (Entity-Relationship Diagram)** knihovního systému, který eviduje knihy, jejich konkrétní fyzické výtisky, čtenáře a výpůjčky. Diagram byl vytvořen v nástroji **Lucidchart**.

## Popis systému
Model reprezentuje správu knih v knihovně a zahrnuje:

- **Knihy** a jejich bibliografické údaje.
- **Autory**, kteří jsou s knihami spojeni.
- **Vydavatelství**, ze kterých knihy pochází.
- **Výtisky** jednotlivých knih (fyzické kusy).
- **Čtenáře**, kteří si mohou knihy půjčovat nebo rezervovat.
- **Výpůjčky**, které sledují zapůjčení výtisků.
- **Rezervace**, pokud v knihovně nejsou volné výtisky.
- **Upomínky**, pokud čtenář překročí dobu výpůjčky.

## Entitní model

| Entita | Primární klíč | Vybrané atributy | Popis |
|-------|--------------|----------------|--------|
| **vydavatelství** | id_vydavatelství | název, adresa, email, telefon | Údaje o vydavatelství |
| **autor** | id_autor | jméno, příjmení | Autoři knih |
| **kniha** | id_kniha | název, isbn, id_autor, id_vydavatelství | Bibliografická jednotka |
| **výtisk** | id_výtisk | název, id_kniha, id_autor, id_vydavatelství | Konkrétní fyzický kus knihy |
| **čtenář** | id_čtenar | jméno, příjmení, id_upomínka | Registrovaný uživatel |
| **výpůjčka** | id_výpůjčka | id_čtenar, datum_zapůjčení, datum_vrácení | Záznam o zapůjčení výtisku |
| **rezervace** | id_rezervace | id_čtenar, id_kniha, rezervace_datum | Rezervace knihy |

## Použitý nástroj
Diagram byl vytvořen v **Lucidchart**, vyexportován a odevzdán jako obrázek.

## Poznámka
Model umožňuje:
- sledovat dostupnost fyzických výtisků,
- identifikovat prodlení výpůjček,
- pracovat s rezervacemi, kdy není výtisk k dispozici,
- rozšiřovat dalšími atributy dle potřeb knihovny.
