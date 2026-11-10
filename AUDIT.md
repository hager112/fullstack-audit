# AUDIT – fullstack-audit

## Steg 1: Starta från noll
- Jag hade .NET 9, men projektet kräver .NET 10. README säger vilken version som behövs men inte var man laddar ner den.
- README säger inte att backend och frontend måste köras samtidigt i två olika terminaler.
- När jag körde `npm install` ändrades `package-lock.json`. README borde säga `npm ci` i stället.
- Efter det startade både backend och frontend med README:s instruktioner.

## Steg 2: Checklistan (0 = saknas, 1 = finns lite, 2 = sitter bra)

### Hur koden är byggd
| Punkt | Poäng | Kommentar |
|---|---|---|
| Tunna controllers, logik i services | 2 | TodosController anropar bara TodoService |
| DTOs används | 2 | TodoResponse och CreateTodoRequest |
| Frontend lätt att hitta i | 1 | Inte granskat ordentligt än |

### Hur koden mår
| Punkt | Poäng | Kommentar |
|---|---|---|
| Tester som körs med ett kommando | 1 | Backend: 7 tester. Frontend: bara 2 tester |
| Servern kollar att datan är rimlig | 2 | Tom uppgift sparas inte (README: 400 om titeln är tom) |
| Vettigt besked när något går fel | 0 | Tom ruta + "Lägg till" = ingenting händer, inget meddelande |
| Laddning och tom lista visas | 1 | Tom lista visar text. Laddning inte kontrollerat |

### Hur repot fungerar för ett team
| Punkt | Poäng | Kommentar |
|---|---|---|
| README räcker för att starta | 1 | Fungerar, men saknar länkar och info om två terminaler |
| bin, obj, node_modules utanför git | 2 | git status visar dem inte |
| Inga lösenord i koden | 2 | appsettings.json innehåller inga hemligheter |
| Commit-historiken är en berättelse | 1 | Bara 1 commit ("Initial commit"), för lite att bedöma |
| Samma formatering överallt | 2 | dotnet format och prettier --check går igenom |

## Mina 5 viktigaste förbättringar
1. Visa ett felmeddelande när man försöker lägga till en tom uppgift.
2. README: länka till .NET 10 SDK och Node.js, och förklara att backend och frontend körs i två terminaler.
3. README: använd `npm ci` i stället för `npm install`.
4. Skriv fler frontend-tester, till exempel för vad som händer när API:t svarar med fel.
5. Låt GitHub köra build, tester och formatering automatiskt vid varje Pull Request.

## AI-användning
Jag var inte med på genomgången, men jag läste lärarens instruktioner och
checklista på Learnpoint i efterhand. Jag tog hjälp av AI för att förstå stegen,
till exempel hur man installerar .NET 10 och vad git status visar. Alla kommandon
och tester har jag kört själv, och fynden kommer från det jag såg när jag testade appen.
