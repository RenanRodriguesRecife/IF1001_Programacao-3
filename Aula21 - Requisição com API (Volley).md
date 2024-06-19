# Requisição com API

- Volley
- RequestQueue
- StringRequest
- JSON

## Volly

- Biblioteca HTTP
- Desenvolvida pela Google e introduzida em 2013
- Gerencia o processamento e caching de requisições de rede
- Guarda todas as resposta em memória durante o parse da requisição
  - Não é recomendado para download e operações de streaming
 
- Última atualização 2021
  - Versão 1.2.1
 
## Request Queue

- Gerência worker threads que rodam operações de rede, lê e escreve no cache e faz o parse da respostas

- O request faz o parsing das respostas cruas e o volley se encarrega de "despachar" as respostas que estão no request de volta para main thread

- ```kotlin
  private val requestQueue: RequestQueue = Volley.newRequestQueue(context)
  ```

## String request

- É a requisição que queremos enviar

<img src=".assets/">

## JSON

- Utilizado para estruturar dados em formato de texto e permitir a troca de dados entre aplicações de forma simples, leve e rápida.

<img src=".assets/">

<img src=".assets/">


## Colocar dependência

Kotlin

```kotlin

dependencies{
  implementation("com.android.volley:volley:1.2.1")
}
```

<img src=".assets/">

<img src=".assets/">

<img src=".assets/">


```
registro de usuário

171.22.73.167:3000/registerUser

login

172.22.73.167:3000/login

```
