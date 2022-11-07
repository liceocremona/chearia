# Progetto CHeArIA

# Documentazione del backend del progetto CHeArIA

## Version: 1.0

**Contact information:**  
<https://progettochearia.it>  

**License:** [GNU General Public License v3.0](https://raw.githubusercontent.com/liceocremona/chearia-backend/main/LICENSE)

### /board/time

#### GET
##### Summary

Gettime

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Successful Response |

### /board/timems/{tz}

#### GET
##### Summary

Gettimems

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| tz | path |  | Yes | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Successful Response |
| 422 | Validation Error |

### /board/timems

#### GET
##### Summary

Gettimems

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| tz | query |  | No | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Successful Response |
| 422 | Validation Error |

### /board/time/hour

#### GET
##### Summary

Gettime H

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Successful Response |

### /board/time/min

#### GET
##### Summary

Gettime Min

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Successful Response |

### /board/date/{tz}

#### GET
##### Summary

Getdate

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| tz | path |  | Yes | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Successful Response |
| 422 | Validation Error |

### /board/date

#### GET
##### Summary

Getdate

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| tz | query |  | No | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Successful Response |
| 422 | Validation Error |

### /board/putdata/{dataid}

#### PUT
##### Summary

Putdata

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| dataid | path |  | Yes | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Successful Response |
| 422 | Validation Error |

### /resources/graph/all

#### GET
##### Summary

Lista di tutti i grafici

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| type | query |  | No | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Return all graphs |
| 422 | Validation Error |

### /resources/graph/query

#### POST
##### Summary

Query Graph

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| dataid | query |  | No | [ string ] |
| gte | query |  | No | string |
| lte | query |  | No | string |
| unique | query |  | No | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Successful Response |
| 422 | Validation Error |

### /resources/datas

#### GET
##### Summary

Cerca i dati per tipo

##### Description

Questa funzione permette di cercare per dato e per tipo i dati raccolti nel DB,
[Trova i dati](https://web.progettochearia.it)

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| dataid | query |  | Yes | [ string ] |
| gte | query | Data d'inizio, ex: 2022-05-15_10:24:00 or 2022-05-15 | No | string |
| lte | query | Data di fine, ex: 2022-10-15_16:12:00 or 2022-10-15 | No | string |
| day | query | Giorno singolo, ex: 2022-10-15 | No | string |
| type | query |  | No | string |
| sort | query |  | No | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | sucess response |
| 422 | Validation Error |

### /resources/datas/last

#### GET
##### Summary

Ritorna l'ultimo dato per tipo

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| dataid | query |  | Yes | [ string ] |
| type | query |  | No | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | sucess response |
| 422 | Validation Error |

### /resources/datas_stream

#### GET
##### Summary

Stream dei dati in tempo reale

##### Description

Questa funzione restituisce uno streaming dei dai che arrivano dai sensori

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Successful Response |

### Models

#### DataResponse

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| dataid | object |  | Yes |

#### DatasResponse

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| dataid | [ object ] |  | Yes |

#### HTTPValidationError

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| detail | [ object ] |  | No |

#### Metadata

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| id | string |  | Yes |

#### ValidationError

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| loc | [  ] |  | Yes |
| msg | string |  | Yes |
| type | string |  | Yes |

#### routers__board__Data

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| datavalue | number | The value of data from sensor | Yes |
| timestamptz | string | The timzone to use to calculate the timestamp | No |
| key | binary | The key for authenticate request | Yes |

#### routers__resources__Data

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| time | string |  | Yes |
| value | number |  | Yes |
| metadata | object |  | Yes |
