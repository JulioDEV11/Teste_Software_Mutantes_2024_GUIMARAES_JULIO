# Aluno: Júlio Geovani Oliveira Guimarães 

## Atividade 2 - Guia de Testes de Mutação para Projetos Python

*Universidade Federal de Sergipe*

## Resumo da Atividade de Testes de Mutação

Os Testes de Mutação, testes utilizados para avaliar a qualidade e a robustez dos testes de software, confirma e verifca se os casos testes são realmente apropriados para um determinado código. Encontram falhas que testes normais não são capazes de identificar. Funcionamento: Insere pequenas modificações em várias partes do código, com o objetivo de encontrar falhas em testes de softwares.

Utilizei um projeto básico no github que execute funções básicas de uma calculadora, nesse caso, soma, subtração, multiplicação, divisão, potência de 2 e raiz quadrada. Utilizei os comandos pytest - teste de unidade, pytest-cov - devolve cobertura dos testes e o mutmut aplica os testes de mutação.

[Documento tutorial em PDF](https://github.com/JulioDEV11/JulioDEV11-Teste_Software_Mutantes_2024_GUIMARAES_JULIO/blob/main/Atividade%202.pdf)

## Tecnologias utilizadas
Sistema Operacional: Windowns 
IDE: Visual Studio Code 
Ferramentas: Venv(Ambiente Virtual), pytest, pytest-cov e mutmut. 
 
Configurações feitas no ambiente: 

Em primeiro, um clone no repositório: 

Código:  “git clone https://github.com/valdas-v1/A-Simple-Python-Calculator.git ” 
 
Em segundo, a instalação do venv:  

Código: “python -m venv venv” 
                   “python3 -m venv meu-diretório\venv”

Em terceiro, a Ativação do venv (Ambiente Virtual): 

 Código: “venv/Scripts/activate” 

Em quarto, a instalação dos pacotes já disponíveis no repositório: 

Código: “pip3 install -r requirements.txt” 
Obs: Adição dos pacotes pytest-cov e mutmut ao 	requirements.txt.

## Execução dos testes: 

Execução do arquivo de teste utilizando o pytest:  “pytest -vv meu-diretório\tests\test_calculator.py”
Execução do teste de cobertura: “pytest -vv meu-diretório\tests\test_calculator.py --cov=calculator”
Gerando html com as informações do teste de cobertura: pytest -vv  meu-diretório\tests\test_calculator.py --cov=calculator --cov-branch --cov-report html
Execução do teste de mutação: “mutmut run --paths-to-mutate=meu-diretório\calculator\calculator.py --tests-dir=meu-diretório\tests”

Conclusão: De forma geral, os casos de teste se comportaram bem em relação ao teste de mutação, eliminaram praticamente todos os 38 mutants inseridos, sobrevivendo apenas 3 mutants.  

Um dos problemas encontrados foi na possível passagem do valor None ao self.memory que estava pegando por padrão o valor 0.
![image](https://github.com/user-attachments/assets/c8bbd8bf-5d5e-44a2-ac34-a1a464ae116e)
![image](https://github.com/user-attachments/assets/aa992457-ed28-4877-a243-43ce01a00f7e)
![image](https://github.com/user-attachments/assets/5e647e12-1d84-404b-90db-27044eb38c6e)


Com uma pequena alteração para pegar exatamente o memory=0 que a função recebia por padrão, mais 1 mutant foi eliminado. 

![image](https://github.com/user-attachments/assets/2c77ae67-68d4-426e-b340-30656be53aea)
![image](https://github.com/user-attachments/assets/0d875c74-b982-49d5-9fac-47028f6a2adc)

Dessa forma, sobraram apenas dois mutants. Novos casos de teste resultaram em uma melhor detecção de mutantes, melhorando a confiabilidade do código.


 

