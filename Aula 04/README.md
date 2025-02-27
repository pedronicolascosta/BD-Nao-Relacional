# Anotações da Aula 📝

## Continuação: Modelagem de um BD Não Relacional
1. Acessar o site [Hackolade](https://hackolade.com/)
2. Clique em **Get started for FREE**
3. Clique em **Open data model**
4. Importe o arquivo [modelagem-ultima-aula](modelagem-ultima-aula.hck.json/) para dar continuidade a modelagem anteriormente iniciada
<br><br>![image](https://github.com/user-attachments/assets/56b08849-07fc-4d40-a38a-24151354c139)

## ARRAY [ ]
**O item está no plural? = array!**<br>
**Quer armazenar várias coisas? Vários emails, endereços? = ARRAY**<br>
Exemplo:<br>
```
{
    "telefones":[
        {"ddd":11,"numero":999999999},
        {"ddd":13,"numero":888888888}
    ]
}
```
O fato de telefones estar no plural indica que mais de um telefone poderá ser cadastrado, então um array deve ser criado.<br>

## DOCUMENTO { }
**Precisa armazenar vários atributos sobre um assunto específico? = documento!**<br>
**Quer armazenar dados de um endereço, como CEP, RUA, BAIRRO, CIDADE, ESTADO, PAÍS ETC...? = Documento!**<br>
Exemplo:<br>
```
{
    "endereco":{
        "CEP":"00000-000",
        "num":"00",
        "Rua":"Nome da Rua",
        "Bairro":"Nome do Bairro",
        "Cidade":"Nome da Cidade",
        "UF":"SP"
    }
}
```
Neste caso, o atributo endereço será um DOCUMENTO, onde armazenamos vários atributos que compõem o endereço.

## Atualizações na Modelagem
➡️[Veja aqui atualizações da aula](modelagem-final.hck.json)
- Maior descrição de atributos para os funcionários (sexo, telefones, emails, endereço, cargo e projetos)
- Criação da collection Cargos
- Criação da collection Projetos
- Relacionamento entre funcionários e cargos e projetos
<br><br>
![Captura de tela 2025-02-26 210249](https://github.com/user-attachments/assets/a3838eed-117b-4521-be53-40eb8eb65648)
