# Instruções para Instalar, Configurar e Executar o Projeto

Este documento fornece as instruções necessárias para instalar, configurar e executar o projeto que utiliza VueJS VITE, TailwindCSS e exibe um gráfico de barras com dados da COVID API.

## Instalação

Certifique-se de ter o Node.js instalado antes de prosseguir.

1. Clone o repositório para a sua máquina local:

   # Terminal
   git clone https://github.com/AdilsonRotware/CovidTest.git


# Acesse o diretório do projeto:

1. Terminal
cd TestAP
Instale as dependências do projeto:

2. Terminal
npm install

# Configuração:

1. TailwindCSS
Certifique-se de que o TailwindCSS está configurado corretamente. Se necessário, consulte a seção "Instalar e configurar o TailwindCSS" no arquivo README.md.

2. COVID API
A aplicação consome a COVID API para obter dados sobre os casos confirmados por país. Certifique-se de ter uma conexão com a internet durante a execução.

# Execução
## Execute o servidor de desenvolvimento:

1. Terminal
npm run dev

2. Abra o navegador e acesse a seguinte URL: http://localhost:3000

Certifique-se de que o servidor está em execução e observe o gráfico de barras exibindo os casos confirmados por país.