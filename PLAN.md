# PLAN

## Cíl dokumentu

Připravit výzkumnou zprávu projektu HLAVO pro potřeby MŽP. Zpráva má být
čitelná pro odborného, ale ne nutně programátorského čtenáře, a současně má
v aplikačních částech poskytovat rámcový návod k použití integrovaného
systému. Rozsah má být přibližně 10 až 30 stran.

## Navržená struktura zdrojů

- `main.tex`: jediný LaTeXový zdroj celé zprávy včetně preambule, titulní
  strany a všech sekcí
- `zprava.bib`: samostatná bibliografie ve formátu `biblatex`
- `build.sh`: jednotný build skript pro další práci

## Plán zdrojů po sekcích

### 1. Shrnutí a motivace projektu

- Primární zdroje:
  `resources/přihláška/SS06010280-N.pdf`,
  `resources/přihláška/Motivace projektu.docx`,
  `CGS/HPV_CR_vs_Uhelna_2026_03_16.docx`
- Pomocné zdroje:
  `resources/zprávy/za 2024/main.tex`,
  `resources/zprávy/za 2025/main.tex`
- Cíl:
  převzít původní motivaci projektu a doplnit ji o to, co bylo skutečně
  dosaženo

### 2. Zásadní činnosti při řešení projektu

- Primární zdroje:
  `resources/zprávy/za 2024/main.tex`,
  `resources/zprávy/za 2025/main.tex`,
  `CGS/HPV_CR_vs_Uhelna_2026_03_16.docx`
- Pomocné zdroje:
  vybrané obrázky z `resources/zprávy/za 2025/graphics_2025/`,
  obrázky z `CGS/`
- Cíl:
  sestavit chronologicky nebo tematicky srozumitelný přehled hlavních prací
  TUL a ČGS a výstupy ČGS integrovat přímo do hlavního textu

### 3. Rešerše podobných řešení

- Primární zdroje:
  `resources/přihláška/Project_HLAVO_state-of-art.pdf`,
  `resources/zprávy/za 2025/zprava.bib`
- Další plánované zdroje:
  doplněné klíčové články k monitoringu půdní vlhkosti, Richardsovu modelu,
  asimilaci dat a predikci hladin
- Cíl:
  vytvořit krátkou cílenou rešerši přímo navázanou na architekturu HLAVO

### 4. Vlastnosti výsledku: software HLAVO a funkční vzorek integrace

- Primární zdroje:
  `resources/zprávy/za 2025/main.tex`,
  veřejný repozitář `GeoMop/HLAVO` na větvi `main`
- Konkrétní části repozitáře HLAVO:
  README, `data_processing`, `deep_model`, `doc`, `notebooks`
- Pomocné zdroje:
  obrázky a schémata z `resources/zprávy/za 2025/graphics_2025/`
- Cíl:
  převést technické komponenty systému do srozumitelného popisu funkcí,
  vstupů, výstupů a vazeb s větším důrazem na praktickou instalaci a provoz
  sítě profilových měření

### 5. Aplikace na lokalitu Uhelná

- Primární zdroje:
  `resources/zprávy/za 2024/main.tex`,
  `resources/zprávy/za 2025/main.tex`,
  `CGS/HPV_CR_vs_Uhelna_2026_03_16.docx`
- Obrazové podklady:
  `CGS/Obr_*.png`,
  `resources/zprávy/za 2024/graphics_2024/`,
  `resources/zprávy/za 2025/graphics_2024/`,
  `resources/zprávy/za 2025/graphics_2025/`
- Cíl:
  udělat z Uhelné hlavní ukázku aplikace systému se všemi podstatnými vstupy

### 6. Aplikace na jinou lokalitu

- Primární zdroje:
  repozitář HLAVO,
  sekce o datových zdrojích a konfiguraci z předchozích zpráv
- Očekávaný charakter textu:
  obecný postup aplikace pro zatím neurčenou lokalitu v České křídové tabuli,
  nikoli plná druhá případová studie
- Cíl:
  srozumitelně oddělit snadno přenositelné části systému od částí silně
  závislých na místních geologických datech

## Zapracované upřesnění
AGENT: removed, given in AGENTS.md

## Otevřené otázky pro další kolo

1. Jak otevřeně formulovat limity řešení a nedokončené části integrace?
AGENT: limity formulovat jasně, nedokončené části zatím upozornit pomocí \todo{...}
repozitář velmi pokročil vůči zprávě z 2025 a řada věcí není ještě sloučená do main

2. Do jaké míry mají být ve zprávě explicitní názvy softwarových modulů a
   technologií?
AGENT: Explicitně uvést zejména klíčové knihovny a simulační nástroje integrované do projektu.
   
3. Které obrázky z podkladů TUL a ČGS považujete za prioritní pro první draft?
AGENT: Uvedu v textu, dávej obrázků spíš více, já je případně zamítnu/ přesunu.

## Pracovní poznámky

- Stávající zpráva za 2025 používá `natbib`, ale nová kostra je založena na
  `biblatex`, jak požaduje `AGENTS.md`. AGENT: OK.
- Kostra byla po upřesnění zjednodušena na jediný zdroj `main.tex`.
- Veřejný repozitář HLAVO byl předběžně ověřen jako relevantní zdroj pro
  sekce o softwaru a architektuře systému.
