# Inlämningsrapport

Information

OBS!!! Ändra absolut inte rubrikerna i denna fil!!!!

## Databasdesign

### Beskriv hur du har strukturerat din data i MongoDB

Jag har strukturerat min data i MongoDB genom att använda samlingar (collections) och dokument, där varje dokument lagras i JSON-format (BSON).

### 1. Samlingar

Jag har en samling för att lagra mina recept:

- **Recept (recipes)**: Denna samling innehåller alla recept(namn, ingredienser, tillagningssteg, tillagningstid).

### 2. Dokument

Varje dokument i receptsamlingen representerar ett individuellt recept och kan innehålla olika fält som beskriver receptet.

--- Skriv ovanför och ta inte bort denna raden ---

### Jämför kort hur denna struktur skiljer sig från hur du skulle ha gjort i en relationsdatabas

- **Datamodell**:

  **MongoDB**: Data lagras som flexibla JSON-dokument med inbäddade fält och arrayer, vilket ger en hierarkisk struktur.medan Relationsdatabas data lagras i fasta tabeller med rader och kolumner, där varje tabell har en definierad struktur.

--- Skriv ovanför och ta inte bort denna raden ---

### Nämn några skillnader mellan relationsdatabaser och dokumentdatabaser

- **Flexibilitet**:

  - **MongoDB**: Dokument kan ha olika fält, vilket gör det enkelt att ändra datamodellen utan att påverka andra dokument.
  - **Relationsdatabas**: Ändringar kräver att hela tabeller kan behöva uppdateras, vilket kan vara mer tidskrävande.
    **Prestanda**:

- **MongoDB**: Snabbare hämtning av data eftersom relaterad information ofta finns i samma dokument. Detta minimerar behovet av flera databasfrågor.
- **Relationsdatabas**: Prestanda kan påverkas av `JOIN`-operationer, särskilt när flera tabeller är involverade, vilket kan leda till längre svarstider.

--- Skriv ovanför och ta inte bort denna raden ---

### Förklara vad collection, document och field är

- **Collection**: En grupp av dokument i MongoDB som liknar tabeller i en relationsdatabas.
- **Document**: En individuell post i en samling som lagras i JSON-format.
- **Field**: Attributen för dokumentet och kan innehålla olika datatyper, inklusive strängar, nummer, arrayer och inbäddade dokument.

--- Skriv ovanför och ta inte bort denna raden ---

### Beskriv vad det är för skillnad på BSON och JSON

- **JSON**: Textbaserat format, enkelt och läsbart för människor, stöder begränsade datatyper.
- **BSON**: Binärt format, mer kompakt och snabbt, stöder fler datatyper och används av MongoDB för effektiv datalagring.

--- Skriv ovanför och ta inte bort denna raden ---

## Analys och reflektion

### Analysera databasdesignen och nämn några fördelar och några nackdelar med denna typ av databas

**Fördelar**:

- Enkelt och snabbt att göra CRUD-operationer med denna.
- Bra UI, vilket kanske är lättare för nybörjare.
- Ingen behov av att specificera datatyper eller autoincrement för ID eftersom det görs automatiskt.
- Kan spara alla fält på en gång.

**Nackdelar**:

- Kan bli långsammare efter att man lagt till index, särskilt vid uppdateringar eller om man lägger till mycket data, så det är bättre att lägga till index när CRUD är klart och endast göra sökningar efteråt.
- De som inte gillar kommandon kommer kanske inte att uppskatta denna datatyp.
- Mindre lämpliga för komplexa relationer: Joins kan vara utmanande.
- Potentiell dataredundans: Data kan behöva dupliceras över flera dokument.

--- Skriv ovanför och ta inte bort denna raden ---

### Reflektera över möjligheter och begränsningar i MongoDB

**Möjligheter**: Flexibilitet, snabbhet och passar bra för att hantera stora mängder data.  
**Begränsningar**: Komplexa frågor kan vara svåra att genomföra och kan bli lite komplicerade.

--- Skriv ovanför och ta inte bort denna raden ---

## Reflektion och utvärdering

### Vad lärde du dig genom att genomföra projektet?

- Skillnaderna mellan relationsdatabaser och dokumentdatabaser.
- Implementera kommandon genom Mongo Shell och VSCode.
- Grundläggande skapande av data med CRUD.


--- Skriv ovanför och ta inte bort denna raden ---

### Vilka möjligheter ser du för framtida projekt baserat på denna erfarenhet?

- När man ska hantera stora mängder data i framtiden. Att göra applikationer mer dynamiska, även inom dataanalys och rapportering.

--- Skriv ovanför och ta inte bort denna raden ---
