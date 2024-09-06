# SED-transporte-carga

## Problema

O sistema de transporte de carga é composto por uma via circular com 8 seções e 3 veículos. Entre cada seção, exceto entre as seções 2 e 3, há um semáforo que controla a entrada de veículos, permitindo que apenas um veículo transite por vez em cada seção. Inicialmente, os veículos estão posicionados nas seguintes seções:
- Veículo 1 na seção 1
- Veículo 2 na seção 4
- Veículo 3 na seção 7

Por questões de segurança, apenas um veículo pode ocupar uma seção por vez.

![Ilustração do Problema](https://github.com/user-attachments/assets/7cd030a6-a5e8-46ec-8713-c1358689fcdd)

## Objetivo

Desenvolver um modelo de autômato e o respectivo supervisor para esse sistema utilizando o software Supremica.

## Abordagem

A solução foi estruturada através da modelagem de cada seção individualmente, resultando na criação de três tipos distintos de autômatos:

1. **Modelo para as seções 1, 4, 5, 6, 7, e 8**: Essas seções compartilham um mesmo comportamento. O semáforo permanece vermelho enquanto um veículo estiver presente na seção e muda para verde assim que o veículo transita para a próxima seção.
   
2. **Modelo para a seção 2**: Devido à ausência de um semáforo na seção 3, o semáforo da seção 2 só volta a ficar verde quando o veículo chega à seção 4. Além disso, um autolaço no sinal vermelho garante que a seção 3 só seja acessada após a passagem pela seção 2.
   
3. **Modelo para a seção 3**: Funciona de forma semelhante ao modelo das seções 1, 4, 5, 6, 7, e 8, mas sem o controle de semáforo devido à ausência de um semáforo nesta seção.

Abaixo estão representações gráficas dos três modelos de autômatos utilizados no projeto:

![Modelos de Autômatos](https://github.com/user-attachments/assets/a7631a42-57bd-48ff-82c9-7d8f8521538a)

### Composição dos Autômatos

Após a criação dos modelos individuais, foi realizada a composição paralela dos oito autômatos, resultando na versão final do sistema. A montagem dos autômatos no Supremica é ilustrada a seguir:

![Montagem no Supremica](https://github.com/user-attachments/assets/507c5704-e372-42b7-913a-a15a3d825325)

### Modelo Final

A composição paralela dos autômatos gerou o modelo final do sistema. Embora a análise de cada autômato individualmente seja mais clara para fins de compreensão, a representação completa do sistema oferece uma visão geral do comportamento integrado:

![Modelo Final](https://github.com/user-attachments/assets/782319f4-4008-4ea8-b7a3-845980ff5543)
