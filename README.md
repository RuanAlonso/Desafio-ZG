# Desafio-ZG
Desafio para o Acelera ZF 6.0 - 2024

Iniciamos o desafio com a seguinte especifiação:
 ' Inicie o desafio realizando uma requisição do tipo GET para seguinte endpoint:
https://aczgdesafio.rj.r.appspot.com/passo1 '

Aqui, optei por seguir com o código em JavaScript utilizando funcionalidade de fetch API para fazer requisições HTTP assíncronas direto de um navegador, segue o código:


// Essa linha usa a função 'fetch' para fazer requisição HTTP GET para o endpoint fornecido no desafio.
fetch('https://aczgdesafio.rj.r.appspot.com/passo1') 

# O 'then' aqui é usado para lidar com a resposta da requisição que fizemos acima. Ele receberá um ''callback'' quando a resposta estiver disponível.
  .then(response => {        
 
# Esse bloco condicional serve para verificar se a resposta HTTP foi bem sucedidade, caso não seja, lança um erro com uma mensagem que incçui o status da resposta
    if (!response.ok) {
      throw new Error(Erro de rede: ${response.status});
    }  

# Se a resposta for bem sucedida, este método extrai e retorna o corpo da resposta como um objeto JSON.
    return response.json();
  })
# Este método 'then' é usado para lidar com os dados retornados pela chamada 'response.json()'. Ele recebe um callback que será executado se ocorrer um erro, e aqui imprimi no consolo.
  .then(data => {
 
    console.log('Resposta:', data);
  })

# Por fim, este catch é usado para lidar com quaisquer erros que ocorram durante o processo de requisição ou de análise de dados. Também receberá um callback que será executado se ocorrer um erro, e imprime no console.
  .catch(error => {

    console.error('Ocorreu um erro:', error);
  });
