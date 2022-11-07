## Nome dei grafici

`dato_f(y)_data.svg`

- dato:
  - scritto secono l'ID presente nella sezione metadata nel DB
  - itwork <br>
    CO<br>
	altitude<br>
	humidity<br>
	ozone<br>
	pressure<br>
	temperature
	
- f(y)
  - in cosa è in funzione
  - boh devi dirmi in cosa può essere in funzione così metto le opzioni adatte
   (usa nomi inglesi)
  
- data
  - giorno singolo: `YYYY-MM-DD` con 0 prima del numero se è minore di 10
    ex:<br>
    2022-05-24, <br>
	 2022-11-02
  - range di giorni: `YYYY-MM-DDRYY-MM-DD` R indica che è un range
    ex: <br>
	2022-10-05R2022-11-05<br>
	2022-11-05R2022-11-7
  - range date con orari: `YYYY-MM-DDThh:mm:ssRYYYY-MM-DDThh:mm:ss` R indica i range e T l'orario
    ex: <br>
	2022-10-24T11:13:00R2022-11-03T15:00:23<br>
	2022-11-07T08:15:42R2022-11-07T13:34:00
    
### Esempi
Sui grafici gia sul server

[Temperatura in funzione di umidità del 22-03-2022](https://storage.progettochearia.it/graph/Temperatura%20in%20f(umidit%C3%A0)_temperature_22-03-2022.svg):<br>
`temperature_f(humidity)_2022-03-22.svg`

[Temperatura in fuzione di tempo 22-03-2022](https://storage.progettochearia.it/graph/Temperatura%20in%20f(tempo)_temperature_22-03-2022.svg):<br>
`temperature_F(time)_2022-03-22.svg`
 

Pressione in funzione di altitudine il 2022-11-07 dalle 8:15 alle 10:<br>
`pressure_f(altitude)_2022-11-07T08:15:00R2022-11-07T10:00:00`