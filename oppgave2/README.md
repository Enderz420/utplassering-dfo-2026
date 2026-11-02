# Prosjekt

Dere skal lage en nettside som bruker Nuxt rammeverket.
Målet er å hovedsakelig eksperimentere med Vue og Nuxt i sin helhet.

Prosjektet i dens daværende tilstand skal bli vist fram foran meg og Sondre på fredagen denne uka.

Prøv å komme dere så langt som mulig, vi skal jobbe videre med det i neste uke.

Det anbefales å bruke Typescript for dette men vanilla Javascript er lov.
AI er lov men anbefaler å utforske selv, samt spørre rundt før man prøver AI.

For styling så kan man bruke hva som helst, vanilla CSS er fint men anbefaler å få erfaring med Tailwind CSS.

Det anbefales også å bruke et UI-Rammeverk sånn som

- [NuxtUI](https://ui.nuxt.com/)
- [PrimeVue](https://primevue.org/)
- [Vuetify](https://vuetifyjs.com/en/)
- [Reka](https://reka-ui.com/)

Det oppfordres til å bruke GitHub for prosjektet her. Husk å commit ofte.

## Nettsiden skal inneholde:

- En index side. Innholdet er valgfritt.
- En navbar med to lenker til forskjellige deler av nettsiden.
- En layout med navbar og footer. [Layouts](https://nuxt.com/docs/4.x/getting-started/views#layouts)
  - Navbaren skal være i layouten
  - Footeren skal inneholde brukernavn/navn og årstall f.eks Enderz 2026
- En side med data fra et egenvalgt API og vises i en tabell/kort (avhenger av API). [Hvordan fetche data i Nuxt](https://nuxt.com/docs/4.x/getting-started/data-fetching)
  - Usikker på hva slags API du ønsker å bruke? Scroll ned til Index på denne GitHub repoet: [Liste over public API](https://github.com/public-apis/public-apis)
- En side ved bruk av dynamisk routing. Eksempel: /user/[id] [Dokumentasjon](https://nuxt.com/docs/4.x/directory-structure/app/pages#dynamic-routes)
- En eller flere komponenter. for eksempel: en klokke, knapp eller en komponent som viser data fra et api. [Dokumentasjon](https://nuxt.com/docs/4.x/directory-structure/app/components)

## PS:

Hvis du finner ut at du gjenbruker logikk så kan man se på å flytte koden ut i en "composable". Sjekk ut disse sidene for mer.
https://vuejs.org/guide/reusability/composables.html
https://nuxt.com/docs/4.x/directory-structure/app/composables

## Ferdig?

Kommer dere langt nokk så kan dere eksperimentere med:

- Et eget middleware som logger hvor brukeren kommer fra og skal til.
- Et skjema for å gi tilbakemelding på siden.
  - Trenger ikke sende data noen steder, bare et blank skjema som "later" som at den sender data til et sted.

## Ekstra++

Prøv å få implementert en golang backend gjennom denne tutorialen og koble den opp mot nettsiden til å vise resultatet
https://go.dev/doc/tutorial/web-service-gin

## Ressurser

- [Vue Introduction](https://vuejs.org/guide/introduction.html)
- [Nuxt Getting Started](https://nuxt.com/docs/4.x/getting-started/)
- [Nuxt Directory Structure](https://nuxt.com/docs/4.x/directory-structure)
- [Nuxt API Reference](https://nuxt.com/docs/4.x/api)
- [Nuxt in 100 seconds](https://www.youtube.com/watch?v=dCxSsr5xuL8)
- Lærlingene
- https://github.com/Enderz420/testcontainers
