# Vědecká zpáva projektu HLAVO pro MŽP

## Scope
- `AGENTS.md` defines reusable workflow and style rules for presentations.
- `PLAN.md` contains presentation-specific goals, structure, content requirements, and temporary notes.
- Treat `AGENT` notes in source files as requirements or strong suggestions for the next revision.
- directory `resources` contains project proposal and previous project reports  as source materials, do not modify anything there
- directory `cgs` conatins proposed contribution to the report from partner: Česká Geologická služba as DOCX plain text + images
  do not modify that either
- The report should partialy serve as Czech usage manual for the HLAVO SW and integrated system.
  Use HLAVO repository main branch: https://github.com/GeoMop/HLAVO
  
## Cíl
Zpráva má shrnout výsledky projektu pro účely Ministerstva Životního Prostředí. Navrhuji následující strukturu:

- Shrnutí motivace projektu podle přihlášky a textu ČGS
- Shrnutí zásadních činností při řešení projektu
- Rešerše podobných výsledků: (integrovaný systém měení půdní vlhkosti pro infiltraci + Kalmán + Richards 
- Shrnutí vlastností výsledku (software HLAVO a funkční vzorek integrace):
    - síť měření vlhkosti 
    - automatický sběr meteorologických dat
    - organizace dat (schémata, rámcově pro detaily odkázat do repozitáře)
    - Kalmánův filtr + Richards solver (Parflow + CLM) -> predikce infiltrace do hlubokého modelu
    - Hluboký model vadózní zóny -> predikce hladin podzemní vody 
- Aplikace na lokalitu Uhelná (detaily zdrojů meteo dat, dataily o síti profilových měření, detaily o přípravě modelu z GIS dat, hladiny podzemních vod pro kalibraci hlubokého modelu)  
- Aplikace na jinou lokalitu (meteodata snadno dostupná změnou nastavení zdrojů z ČHMÚ, profilové měření - možno aplikovat podle druhů povrchů/půd, hlavní problém znalost geologie a hladin podzemních vod pro kalibraci).
  
## LaTeX style
- Follow style from 2025 report, in particular TAČR logos
- Use `biblatex` references in separate bib file
- use only `\includegraphics[width=<x>\linewidth]{..}`, i.e. no height no keepaspectratio

### Math and notation
- Use `$...$` for inline math and `\[...\]` for displayed math.
- Reuse notation macros from 2025 report whenever available, especially `\grad`, `\div`, `\vc{}`, `\tn{}`, and `\norm{}`.
- Do not reintroduce raw notation if a project macro already exists.

## Workflow
- Always build through `./build.sh`; do not invoke `latexmk`, `lualatex`, or `pdflatex` directly for presentation builds.
- Assume the build produces both a clean PDF of the current working copy and a diff PDF for human review.
- The diff PDF is normally built against `HEAD:main.tex`; if `main.tex` is staged, the diff is built against the staged version instead, which allows incremental review between staging points.
- When inspecting the document yourself, use the clean `main.pdf` built from the current working copy; reserve the diff PDF mainly for human review.
- If PDF review is needed, inspect the generated PDF with read-only command-line tools and then edit the sources.
- You can build the project and use PDF inspection tools as you wish, do not ask the user.
- Keep patches clean, localized, and easy to inspect in `git-cola`.
- Keep primary edits in the presentation sources, not in top-level `_*` source-material directories.

## Upřesnění cílů
- Zpráva má být spíše stručná; cílový rozsah je přibližně 10 až 30 stran.
- Aktuálně udržuj celý LaTeXový zdroj v jediném souboru `main.tex`; případné dělení do více souborů je až pozdější krok.
- Není potřeba samostatná kapitola ve stylu českého návodu k softwaru, ale části o aplikaci systému na lokality mají poskytovat rámcový návod k použití.
- Na detailní technickou dokumentaci softwaru je vhodné odkazovat na Read the Docs dokumentaci; ve zprávě však podrobněji popiš zejména instalaci a provoz sítě profilových měření vlhkosti, protože to není v technické dokumentaci dostatečně pokryto.
- Sekce o jiné lokalitě má mířit na obecný postup aplikace v prostředí České křídové tabule pro zatím neurčenou lokalitu.
- Text a výsledky ČGS mají být integrovány přímo do hlavního LaTeXového textu; obrázky z `CGS` používej jako podklady pro tuto integraci, nikoli jako samostatnou přílohu ve stylu předchozích zpráv.
