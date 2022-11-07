# Progetto CHeArIA

> Version 1.0


# Documentazione del backend del progetto CHeArIA


## Path Table

| Method | Path | Description |
| --- | --- | --- |
| GET | [/board/time](#getboardtime) | Gettime |
| GET | [/board/timems/{tz}](#getboardtimemstz) | Gettimems |
| GET | [/board/timems](#getboardtimems) | Gettimems |
| GET | [/board/time/hour](#getboardtimehour) | Gettime H |
| GET | [/board/time/min](#getboardtimemin) | Gettime Min |
| GET | [/board/date/{tz}](#getboarddatetz) | Getdate |
| GET | [/board/date](#getboarddate) | Getdate |
| PUT | [/board/putdata/{dataid}](#putboardputdatadataid) | Putdata |
| GET | [/resources/graph/all](#getresourcesgraphall) | Lista di tutti i grafici |
| POST | [/resources/graph/query](#postresourcesgraphquery) | Query Graph |
| GET | [/resources/datas](#getresourcesdatas) | Cerca i dati per tipo |
| GET | [/resources/datas/last](#getresourcesdataslast) | Ritorna l'ultimo dato per tipo |
| GET | [/resources/datas_stream](#getresourcesdatas_stream) | Stream dei dati in tempo reale |

## Reference Table

| Name | Path | Description |
| --- | --- | --- |
| DataResponse | [#/components/schemas/DataResponse](#componentsschemasdataresponse) |  |
| DatasResponse | [#/components/schemas/DatasResponse](#componentsschemasdatasresponse) |  |
| HTTPValidationError | [#/components/schemas/HTTPValidationError](#componentsschemashttpvalidationerror) |  |
| Metadata | [#/components/schemas/Metadata](#componentsschemasmetadata) |  |
| ValidationError | [#/components/schemas/ValidationError](#componentsschemasvalidationerror) |  |
| routers__board__Data | [#/components/schemas/routers__board__Data](#componentsschemasrouters__board__data) |  |
| routers__resources__Data | [#/components/schemas/routers__resources__Data](#componentsschemasrouters__resources__data) |  |

## Path Details

***

### [GET]/board/time

- Summary  
Gettime

#### Responses

- 200 Successful Response

`text/plain`

```ts
{
  "type": "string"
}
```

***

### [GET]/board/timems/{tz}

- Summary  
Gettimems

#### Responses

- 200 Successful Response

`text/plain`

```ts
{
  "type": "string"
}
```

- 422 Validation Error

`application/json`

```ts
{
  detail: {
    loc?: Partial(string) & Partial(integer)[]
    msg: string
    type: string
  }[]
}
```

***

### [GET]/board/timems

- Summary  
Gettimems

#### Parameters(Query)

```ts
tz?: string
```

#### Responses

- 200 Successful Response

`text/plain`

```ts
{
  "type": "string"
}
```

- 422 Validation Error

`application/json`

```ts
{
  detail: {
    loc?: Partial(string) & Partial(integer)[]
    msg: string
    type: string
  }[]
}
```

***

### [GET]/board/time/hour

- Summary  
Gettime H

#### Responses

- 200 Successful Response

`text/plain`

```ts
{
  "type": "string"
}
```

***

### [GET]/board/time/min

- Summary  
Gettime Min

#### Responses

- 200 Successful Response

`text/plain`

```ts
{
  "type": "string"
}
```

***

### [GET]/board/date/{tz}

- Summary  
Getdate

#### Responses

- 200 Successful Response

`text/plain`

```ts
{
  "type": "string"
}
```

- 422 Validation Error

`application/json`

```ts
{
  detail: {
    loc?: Partial(string) & Partial(integer)[]
    msg: string
    type: string
  }[]
}
```

***

### [GET]/board/date

- Summary  
Getdate

#### Parameters(Query)

```ts
tz?: string
```

#### Responses

- 200 Successful Response

`text/plain`

```ts
{
  "type": "string"
}
```

- 422 Validation Error

`application/json`

```ts
{
  detail: {
    loc?: Partial(string) & Partial(integer)[]
    msg: string
    type: string
  }[]
}
```

***

### [PUT]/board/putdata/{dataid}

- Summary  
Putdata

#### RequestBody

- application/json

```ts
{
  // The value of data from sensor
  datavalue: number
  // The timzone to use to calculate the timestamp
  timestamptz?: string
  // The key for authenticate request
  key: string
}
```

#### Responses

- 200 Successful Response

`text/plain`

```ts
{
  "type": "string"
}
```

- 422 Validation Error

`application/json`

```ts
{
  detail: {
    loc?: Partial(string) & Partial(integer)[]
    msg: string
    type: string
  }[]
}
```

***

### [GET]/resources/graph/all

- Summary  
Lista di tutti i grafici

#### Parameters(Query)

```ts
type?: string
```

#### Responses

- 200 Return all graphs

`application/json`

```ts
string[]
```

- 422 Validation Error

`application/json`

```ts
{
  detail: {
    loc?: Partial(string) & Partial(integer)[]
    msg: string
    type: string
  }[]
}
```

***

### [POST]/resources/graph/query

- Summary  
Query Graph

#### Parameters(Query)

```ts
dataid?: string[]
```

```ts
gte?: string
```

```ts
lte?: string
```

```ts
unique?: string
```

#### Responses

- 200 Successful Response

`application/json`

```ts
{}
```

- 422 Validation Error

`application/json`

```ts
{
  detail: {
    loc?: Partial(string) & Partial(integer)[]
    msg: string
    type: string
  }[]
}
```

***

### [GET]/resources/datas

- Summary  
Cerca i dati per tipo

- Description  
Questa funzione permette di cercare per dato e per tipo i dati raccolti nel DB,   
[Trova i dati](https://web.progettochearia.it)

#### Parameters(Query)

```ts
dataid?: string[]
```

```ts
// Data d'inizio, ex: 2022-05-15_10:24:00 or 2022-05-15
gte?: string
```

```ts
// Data di fine, ex: 2022-10-15_16:12:00 or 2022-10-15
lte?: string
```

```ts
// Giorno singolo, ex: 2022-10-15
day?: string
```

```ts
type?: string
```

```ts
sort?: string
```

#### Responses

- 200 sucess response

`application/json`

```ts
{
  dataid: {
    time: string
    value: number
    metadata: {
      id: string
    }
  }[]
}
```

- 422 Validation Error

`application/json`

```ts
{
  detail: {
    loc?: Partial(string) & Partial(integer)[]
    msg: string
    type: string
  }[]
}
```

***

### [GET]/resources/datas/last

- Summary  
Ritorna l'ultimo dato per tipo

#### Parameters(Query)

```ts
dataid?: string[]
```

```ts
type?: string
```

#### Responses

- 200 sucess response

`application/json`

```ts
{
  dataid: {
    time: string
    value: number
    metadata: {
      id: string
    }
  }
}
```

- 422 Validation Error

`application/json`

```ts
{
  detail: {
    loc?: Partial(string) & Partial(integer)[]
    msg: string
    type: string
  }[]
}
```

***

### [GET]/resources/datas_stream

- Summary  
Stream dei dati in tempo reale

- Description  
Questa funzione restituisce uno streaming dei dai che arrivano dai sensori

#### Responses

- 200 Successful Response

`application/json`

```ts
{}
```

## References

### #/components/schemas/DataResponse

```ts
{
  dataid: {
    time: string
    value: number
    metadata: {
      id: string
    }
  }
}
```

### #/components/schemas/DatasResponse

```ts
{
  dataid: {
    time: string
    value: number
    metadata: {
      id: string
    }
  }[]
}
```

### #/components/schemas/HTTPValidationError

```ts
{
  detail: {
    loc?: Partial(string) & Partial(integer)[]
    msg: string
    type: string
  }[]
}
```

### #/components/schemas/Metadata

```ts
{
  id: string
}
```

### #/components/schemas/ValidationError

```ts
{
  loc?: Partial(string) & Partial(integer)[]
  msg: string
  type: string
}
```

### #/components/schemas/routers__board__Data

```ts
{
  // The value of data from sensor
  datavalue: number
  // The timzone to use to calculate the timestamp
  timestamptz?: string
  // The key for authenticate request
  key: string
}
```

### #/components/schemas/routers__resources__Data

```ts
{
  time: string
  value: number
  metadata: {
    id: string
  }
}
```
