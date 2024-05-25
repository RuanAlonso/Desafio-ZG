                                         
                                                   ## Desafio-ZG
                                        ## Desafio para o Acelera ZG 6.0 - 2024
   


Iniciamos o desafio com a seguinte especifiação:
 ' Inicie o desafio realizando uma requisição do tipo GET para seguinte endpoint:
https://aczgdesafio.rj.r.appspot.com/passo1 '

Aqui, optei por seguir com o código em JavaScript utilizando funcionalidade de fetch API para fazer requisições HTTP assíncronas direto de um navegador, segue o código:


// Essa linha usa a função 'fetch' para fazer requisição HTTP GET para o endpoint fornecido no desafio.
```JavaScript
fetch('https://aczgdesafio.rj.r.appspot.com/passo1') 
```
// O 'then' aqui é usado para lidar com a resposta da requisição que fizemos acima. Ele receberá um ''callback'' quando a resposta estiver disponível.

```JavaScript
  .then(response => {        
 ```

// Esse bloco condicional serve para verificar se a resposta HTTP foi bem sucedidade, caso não seja, lança um erro com uma mensagem que incçui o status da resposta

```JavaScript
    if (!response.ok) {
      throw new Error(Erro de rede: ${response.status});
    }  
```
// Se a resposta for bem sucedida, este método extrai e retorna o corpo da resposta como um objeto JSON.

```JavaScript
    return response.json();
  })
```

// Este método 'then' é usado para lidar com os dados retornados pela chamada 'response.json()'. Ele recebe um callback que será executado se ocorrer um erro, e aqui imprimi no consolo.

```JavaScript
  .then(data => {
 
    console.log('Resposta:', data);
  })
```
// Por fim, este catch é usado para lidar com quaisquer erros que ocorram durante o processo de requisição ou de análise de dados. Também receberá um callback que será executado se ocorrer um erro, e imprime no console.

```JavaScript
  .catch(error => {

    console.error('Ocorreu um erro:', error);
  });
```

// Como resposta a esse código, obtive :

```JavaScript
    "status": 200,
    "mensage": "Parabéns, você concluiu o Passo 1!",
    "description": "No passo 2 realize uma requisição do tipo POST no endpoint: https://aczgdesafio.rj.r.appspot.com/passo2",
    "recomendations": "Envie no corpo da requisição um Json informando seu cpf, no seguinte formato: {cpf:xxx.xxx.xxx-xx}"
}
```

Para essa parte do desafio, utilizei o seguinte código:


// Define os dados a serem enviados na requisição

```JavaScript
const dados = {
  cpf: "xxx.xxx.xxx-xx"
};
```

// Configura as opções da requisição e já definindo o método HTTP como Post para que depois seja definido o tipo de conteúdo como JSON

```JavaScript
const options = {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json' 
  },
```
// Converte os dados para JSON e os envia no corpo da requisição

```JavaScript
  body: JSON.stringify(dados) 
};
```

// Faz uma requisição POST para o endpoint fornecido, passando as opções configuradas e na sequência, converte a resposta para texto, manipula os dados retornados pela resposta e captura e trata os erros que ocorram durante o processo de requisição

```JavaScript
fetch('https://aczgdesafio.rj.r.appspot.com/passo2', options)


  .then(response => response.text())


  .then(data => console.log(data))


  .catch(error => console.error('Erro:', error));
```








