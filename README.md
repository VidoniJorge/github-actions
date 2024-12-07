# github-actions
Proyecto para probar las capacidades de github-actions

## Operadores

| Operador  | Descripción         |
| --------- |:-------------:|
| ()        | Agrupacion lógica   |
| []        | Índice              |
| .         | Feferencia de propiedad |
| !         | Not                 |
| <         | Menor que           |
| <=        | Menor o igual que   |
| >         | Mayor que           |
| =>        | Mayor o igual que   |
| ==        | Igual               |
| !=        | No igual a          |
| &&        | Y                   |
| ||        | Or                  |

## Funciones

###if
```
if:${{<expresión>}}
```
###contains
```
contains(github.event.issue.labels.*.name, 'bug')
```

###toJson
```
toJSON(value)
```

###fromJson
```
fromJSON(value)
```
