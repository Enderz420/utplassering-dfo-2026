<table>  
  <tr>  
    <th>Tid</th>  
    <th>Mandag</th>  
    <th>Tirsdag</th>  
    <th>Onsdag</th>
    <th>Torsdag</th>
    <th>Fredag</th>
  </tr>  
  <tr>  
    <td>08:30</td>  
    <td>Oppmøte</td>  
    <td>Oppmøte</td>
    <td>Oppmøte</td>  
    <td>Oppmøte</td>
    <td>Oppmøte</td>    
  </tr>  
  <tr>  
    <td>09:00-10:45</td>  
    <td>Intro til uke 2</td>  
    <td>Prosjekt</td> 
    <td>Prosjekt</td>  
    <td>Prosjekt</td>
    <td>Misc</td>   
  </tr>  
  <tr>  
    <td>10:45</td>  
    <td>Standup</td>  
    <td>Standup</td>
    <td>Standup</td>  
    <td>Standup</td>
    <td>Standup</td>    
  </tr>  
  <tr>  
    <td>11:00-12:00</td>  
    <td>Lunsj</td>  
    <td>Lunsj</td> 
    <td>Lunsj</td>  
    <td>Lunsj</td>
    <td>Lunsj</td>   
  </tr>
  <tr>  
    <td>12:00-12:45</td>  
    <td>Prosjekt</td>  
    <td>Prosjekt</td>
    <td>Prosjekt</td>  
    <td>Prosjekt</td>
    <td>Ferdigstille prosjekt</td>    
  </tr>  
  <tr>  
    <td>12:45-15:30</td>  
    <td>Presentere plan for uken/skygge ansatte</td>  
    <td>Fortsettelse av prosjekt</td> 
    <td>Prosjekt</td>  
    <td>Prosjekt</td>
    <td>Vise ferdig prosjekt</td>   
  </tr>    
</table>

# Oppgave 3

## Prosjekt

Dere skal lage et REST API med Golang.

Dere kan laste ned GO [her](https://go.dev/dl/).

Hovedsakelig så skal dere bruke `net/http` pakken men andre like som `gorilla mux` og `gin` er lov.

For å være fullstendig skal man kunne sende en HTTP request og få tilbake en response.

AI er lov men ikke anbefalt for å lære. Anbefaler at dere spørr oss lærlinger/ansatte eller googler før man bruker AI direkte.

Dere kan referere til disse for å starte med.
https://go.dev/doc/tutorial/web-service-gin
https://github.com/Enderz420/testcontainers

Er fint å ikke bli ferdig men prøv å få noe ferdig. Vi vil gjerne se hva dere har klart å gjort til slutten av uka.

## Krav

- Du skal ha en healthcheck handler som gir tilbake 200 OK
- Du skal kunne ha et route til å hente data (GET)
- Du skal kunne sende data til en route (POST)
- Du skal kunne slette data (DELETE)
- Du skal kunne oppdatere data (PATCH)
- Du skal kunne Lage eller erstatte data (PUT)
- APIet skal være RESTful
- APIet skal ha en dynamisk route som `/endpoint/{id}` som returnerer unik mocket data. Kan være en noe som sier "hei 1" eller "hei 2".
- Implementer middleware. Vi anbefaler `justinas/alice` [pakken](https://pkg.go.dev/github.com/justinas/alice@v1.2.0) ettersom vi bruker det i Regnskapsportalen men hvis dere finner andre alternativ så er det helt lov.
- Du en logger som bruker `log/slog` stdlib. [relevant fil](https://github.com/Enderz420/testcontainers/blob/main/internal/logging/logging.go)

## Ferdig?

Hvis du blir ferdig tidlig så kan du eksperimentere å sette opp en database for å lagre data.
https://github.com/Enderz420/testcontainers/blob/main/internal/database/db.go
https://www.alexedwards.net/blog/organising-database-access

Dere kan også eksperimentere med å lage tester for handlers.
https://pkg.go.dev/net/http/httptest

Dere kan også implementere en enkel middleware auth som sjekker at brukeren har en hemmelig nøkkel. For eksempel:

```go
// middleware.go
func CheckAuthorization(next http.Handler) http.Handler {
	return http.HandlerFunc(func(w http.ResponseWriter, r *http.Request) {
		// get environment secret from a .env file or something equivalent
		key := w.Header().Get("X-API-Key")
		// if key doesn't match env variable then return unauthorized
		if key != os.Getenv("APP_API_KEY") {
			w.WriteHeader(http.StatusUnauthorized)
			return
		}

		// if nothing is caught by the if statement then run the request through
		next.ServeHTTP(w, r)
	})
}
```

## Ekstra?

Hvis dere har kommet dere langt nokk kan dere prøve å koble opp apiet deres mot en egenutviklet nettside eller prøve å koble opp oppgave 2 mot denne.

## Ressurser

- https://go.dev/
- https://gobyexample.com/
- https://go.dev/solutions/webdev
- https://go.dev/learn/#guided-learning-journeys
- https://go.dev/tour/welcome/1
- https://www.alexedwards.net/blog
