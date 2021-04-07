# NextJS Lab – Valtech Talangprogram VT21
## Krav
* `node` och `npm` installerat

## Länkar
* [NextJS dokumentation](https://nextjs.org/docs)
* [React dokumentation](https://reactjs.org/docs/getting-started.html)
* [Pers presentation](https://docs.google.com/presentation/d/1UMIlyIm38No7mz_TjNZRrol_N7PDV5u7TaLb5iPBp7k/edit?usp=sharing)
* [Exempelsida på Next olika renderingsmetoder](https://nextjs-rendering-example.vercel.app/)
* [Källkoden till exempelsidan](https://github.com/perenstrom/nextjs-rendering-example)

## Resurser
* [Pers film-API med inbyggd fördröjning](https://github.com/perenstrom/example-movie-api)

## Lab
Den här labben handlar om att bekanta sig lite med grundbultarna i NextJS. Ni kommer få testa på olika typer av renderingsmetoder och dess tillhörande datahämtningsmetoder. Ni kommer få testa på API-routes och dynamiska sidor.

Till er hjälp finns det ett API (se rubriken Resurser) som kommer returnera en lista på filmer. API:t har en inbyggd delay på 5 sekunder så att ni kan se de olika renderingsmetodernas effekt mer tydligt, den här delayen går att justera mellan 0 och 9 sekunder (se dokumentationen). 

Ni behöver inte använda det här API:t om ni inte vill, har ni något annat API ni vill använda så är det fritt fram. Detsamma gäller uppgifternas innehåll nedan, ni behöver inte göra en lista på filmer, det är inte det som är poängen, så länge ni använder er av de renderingsmetoderna som är syftet att lära sig.

De olika renderingsmetoderna kommer inte vara lika tydliga när man utvecklar, då kommer Next utvecklingsmiljö göra optimeringar och generera saker on the fly. Så bli inte förvånade om det inte riktigt stämmer överens med exempelsidan.

Generella tips är som all utveckling. Dela upp allt i små problem, gör små delar i taget, testa ofta. Fråga om hjälp när ni vill.

### 1. Få upp en fungerande Next-miljö
1. Kör `npx create-next-app` i den mapp där ni vill skapa ert Next-projekt.
1. Kör `npm run dev` för att starta utvecklarmiljön och se resultatet i webbläsaren

### 2. Skapa en statisk sida med lista på filmer
1. Gör en ny sida under `/pages`
1. Lägg till en `getStaticProps`-metod som hämtar informationen från API:t och returnerar props för sidan
1. Kom ihåg att lägga till en environment-variabel med API-urlen i `.env.local` (ändrar man filen måste man stoppa servern och köra `npm run dev` igen för att de ska gå igenom).
1. Skriv ut listan på filmer (gärna snyggt formatterad, med filmposters, kika i Next-dokumentationen eller presentationen om CSS Modules) på sidan baserat på props:en ni hämtade
1. (Om ni vill SE filerna som kommer ur från en statisk export kan man köra `next build && next export`, då får ni exporterade filer i en `out`-mapp)

### 3. Skapa en dynamisk sida med en enskild film
1. Gör en ny, dynamisk, sida under `/pages`
1. Lägg till en `getStaticPaths`-metod som hämtar information från API:t om vilka filmer som finns och därmed vilka sidor som ska byggas
1. Lägg till en `getStaticProps`-metod som hämtar informationen från API:t och returnerar props för sidan
1. Visa upp filminformationen (gärna snyggt formatterad, med filmposters) på sidan

### 4. Skapa en serverrenderad sida med lista på filmer
1. Gör en ny (eller bygg om den befintliga) sida under `/pages`
1. Lägg till en `getServerSideProps`-metod som hämtar informationen från API:t och returnerar props för sidan
1. Skriv ut listan på filmer (gärna snyggt formatterad, med filmposters) på sidan baserat på props:en ni hämtade

### 5. Skapa en klientrenderad sida med lista på filmer
1. Gör en ny (eller bygg om den befintliga) sida under `/pages`
1. Skapa ett state för filmer och för laddningsstatus
1. Hämta filmer i en `useEffect`-hook (se exempel på `async`-fetch i `useEffect` i presentationen eller källkoden till exempelsidan)
1. Kom ihåg att environment-variabeln med API-urlen i `.env.local` måste börja med `NEXT_PUBLIC_` för att klienten ska kunna använda den
1. Uppdatera state för filmer och laddning
1. Skriv ut laddnings-vy eller filmer baserat på laddningsstatus

### 6. Bygg om den klientrenderade sidan för att gå via API-routes
1. Gör en ny API-route under `/pages/api`
1. Kopiera skelettet från Next-JS autogenererade `hello.js`
1. Kopiera datahämtningen från den serverrenderade sidan till den nya apirouten
1. Byt ut returnerandet av props till att skicka ett 200-svar
  * `res.status(200).end(JSON.stringify(films));`
5. Byt ut urlen i datahämtningen i den klientrenderade sidan till att gå mot det lokala API:t istället (`/api/movies`)
