# 🍕 Pizzameny - Vagabondo Pizzeria

En interaktiv pizzameny för Vagabondo Pizzeria med möjlighet att redigera priser och exportera/importera ändringar.

## 🌐 Live-version
[https://mastersnach.github.io/vagabondo-pizzaria/](https://mastersnach.github.io/vagabondo-pizzaria/)

## 📱 Hur man använder

### För kunder (som vill se menyn):
1. Öppna live-länken ovan
2. Bläddra genom pizzorna på framsidan och baksidan
3. **Spara som PDF**: Tryck "Skriv ut / Spara som PDF" för att få en tryckbar version

### För personal (som vill ändra priser):
- **Redigera priser**: Klicka på maträtter och ändra priser/namn/beskrivningar
- **Lägg till nya rätter**: Använd "Lägg till ny rätt" i redigeringsmodalen
- **Radera permanent**: Högerklicka på maträtter/rubriker → "Radera permanent" (går inte att ångra!)
- **Återställ raderade**: Om du ångrar dig finns "Återställ raderade" knapp (återställer allt)

#### Arbetsflöde för att uppdatera priser:

1. **Öppna menyn**: Gå till live-länken
2. **Redigera priser**: Klicka på maträtter och ändra priser
3. **Alternativ 1 - Spara som PDF**: Tryck "Skriv ut / Spara som PDF" - får direkt en PDF med alla ändringar
4. **Alternativ 2 - Exportera för delning**: Klicka "Exportera meny" - får en `.json`-fil
5. **Skicka filen**: Maila eller dela `pizza-menu-data.json` till GitHub-ägaren
6. **GitHub-ägaren importerar**: Öppnar menyn → "Importera meny" → väljer filen
7. **Uppdatera online**: Push till GitHub så alla ser ändringarna

## 🔧 Tekniska detaljer

- **Frontend**: HTML, CSS (Tailwind), JavaScript
- **Lagring**: localStorage (webbläsare)
- **Hosting**: GitHub Pages
- **Export/Import**: JSON-filer för delning av ändringar

## 🚀 För GitHub-ägare

### Uppdatera online-versionen:
```bash
# Efter att ha fått en pizza-menu-data.json fil:
# 1. Öppna index.html lokalt
# 2. Klicka "Importera meny"
# 3. Välj den mottagna .json-filen
# 4. Testa ändringarna
# 5. Commit och push till GitHub:
git add .
git commit -m "Uppdaterade priser från [namn]"
git push
```

## 📋 Funktioner

- ✅ Interaktiv meny med klickbara maträtter
- ✅ Redigera namn, priser och beskrivningar
- ✅ Export/import av ändringar via JSON-filer
- ✅ Responsiv design (fungerar på mobil och dator)
- ✅ Print-vänlig layout
- ✅ Lokal lagring av ändringar

## 🐛 Felsökning

Om sidan inte laddar:
1. Kontrollera att JavaScript är aktiverat
2. Prova `Ctrl+F5` för att rensa cache
3. Öppna Developer Tools (F12) och kolla Console för fel

---

*Skapad för Vagabondo Pizzeria - Enkelt att använda och uppdatera!* 🍕