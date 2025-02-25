# Anotações da Aula 📝

## Diferenças de nomenclaturas entre SQL e NoSQL
| SQL | NoSQL |
| --- | --- |
| Tabelas | Collections |
| Registro | Documentos |
| Atributos | Atributos |

## Tipos de Chaves
foreign key<br>
primary key<br>
foreign master<br>

## Método de Incorporação
Toda vez que buscar dados de outro lugar e copiar esses dados de uma collection e colar em outra é um método de **INCORPORAÇÃO**, ou seja, **INCORPORAR VALORES**<br>
Toda vez que tem master key é por **INCORPORAÇÃO**<br>
**Copiar dados entre collections** = **INCORPORAÇÃO**<br><br>
**Exemplo de Incorporação**
```
    "funcionarios":{
        "_id": 1,
        "idFuncionario": 1,
        "nome": "Carlos",
        "emails":["carlos1@email.com","carlos2@email.com"],
        "telefones":[{"ddd":11, "numero":932580079, "descricao":"whatsapp"},{"ddd":11, "numero":48247257, "descricao":"residencial"}],
        
        "departamento":{"_id":200,"nome":"TI"} 
    },
    
    "departamentos":{
        "_id": 200,
        "nome": "TI"
    }
```
Neste caso, há incorporação na collection 'funcionários', pois os dados de 'departamento' foram copiados e colados dos dados masters da collection 'departamentos' 

## Método de Referencia
Toda vez que, em uma collection, realizar referencia de outra collection por meio de um ``_id``, está sendo utilizado o método de **REFERÊNCIA**<br>
**Exemplo de Referência**
```
    "funcionarios":{
        "_id": 1,
        "idFuncionario": 1,
        "nome": "Carlos",
        "emails":["carlos1@email.com","carlos2@email.com"],
        "telefones":[{"ddd":11, "numero":932580079, "descricao":"whatsapp"},{"ddd":11, "numero":48247257, "descricao":"residencial"}],
        "departamento":{"_id":200,"nome":"TI"},

        "cargo": 800
    },
    
    "cargos":{
        "_id": 800,
        "nome": "Desenvolvedor Back-End"
    }
```
Neste caso, está sendo utilizada referência em 'funcionários' pois o dado 'cargo' é um id que relaciona um item na collection 'cargos'

## Relação Cruzada
Um funcionário trabalha em X projetos<br>
Um projeto possui X funcionários<br>
Como relacionar isso?<br>
**Exemplo**
```
    "funcionarios":{
        "_id": 1,
        "nome": "Carlos",
        "projetos":[{"_id": 300,"nome": "Projeto X"},
                    {"_id": 301,"nome": "Projeto Y"}]
    },
    
    "projetos": [
        {"_id": 300,
        "nome": "Projeto X",
        "dhInicio": "2025-02-19 20:31:00",
        "funcionarios":[{"_id":1,"nome":"Carlos"},
                        {"_id":2, "nome": "Maria"} ]
        },

        {"_id": 301,
        "nome": "Projeto Y",
        "dhInicio": "2025-02-19 21:00:00",
        "funcionarios":[{"_id":1,"nome":"Carlos"},
                        {"_id":3, "nome": "Joao"} ]
        }
    ]
```
Neste exemplo, cada funcionário precisa estar relacionado aos projetos no qual participa. Para isso, em sua collection haverá relação por incorporação com a tabela projetos, onde há uma "cópia" dos dados id e nome do projeto da collection 'projetos'. Na collection 'projetos' também é necessário relacionar aos funcionários que atuam neles, então também é realizada referência por incoporação indicando ids e nomes de seus funcionários.

## Dica
### [Hackolade Studio](https://studio.hackolade.com)
Modelagem de Bancos de Dados Relacionais e Não Relacionais
Passo a Passo:
1. New Data Model
2. MongoDB
3. Create
<br><br>![image](https://github.com/user-attachments/assets/56b08849-07fc-4d40-a38a-24151354c139)
