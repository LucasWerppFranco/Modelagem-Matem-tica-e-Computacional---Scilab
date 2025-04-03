# Modelagem Matematica e Computacional - Scilab


```
 __  __           _      _                                             
|  \/  | ___   __| | ___| | __ _  __ _  ___ _ __ ___                   
| |\/| |/ _ \ / _` |/ _ \ |/ _` |/ _` |/ _ \ '_ ` _ \                  
| |  | | (_) | (_| |  __/ | (_| | (_| |  __/ | | | | |                 
|_|  |_|\___/ \__,_|\___|_|\__,_|\__, |\___|_| |_| |_|                 
 __  __       _                  |___/_   _                            
|  \/  | __ _| |_ ___ _ __ ___   /_/_| |_(_) ___ __ _    ___           
| |\/| |/ _` | __/ _ \ '_ ` _ \ / _` | __| |/ __/ _` |  / _ \          
| |  | | (_| | ||  __/ | | | | | (_| | |_| | (_| (_| | |  __/          
|_|__|_|\__,_|\__\___|_| |_| |_|\__,_|\__|_|\___\__,_|  \___|       _  
 / ___|___  _ __ ___  _ __  _   _| |_ __ _  ___(_) ___  _ __   __ _| | 
| |   / _ \| '_ ` _ \| '_ \| | | | __/ _` |/ __| |/ _ \| '_ \ / _` | | 
| |__| (_) | | | | | | |_) | |_| | || (_| | (__| | (_) | | | | (_| | | 
 \____\___/|_| |_| |_| .__/ \__,_|\__\__,_|\___|_|\___/|_| |_|\__,_|_| 
                     |_|                                              
```
## Questão 1 - Tarifação Inteligente no Transporte Público:

Um sistema de transporte público usa uma tarifa dinâmica que depende do número de passageiros. A tarifa T(x), em reais, é definida como: 

T(x) = 4 + 0.5x,        x ∈ [0,20] 

onde x representa o número de passageiros no ônibus. 

---

Para gerar o código Scilab que implemente a tarifação inteligente no transporte público, conforme a equação fornecida, e plotar o gráfico, podemos seguir os seguintes passos:

1. Definir a função tarifária \( T(x) = 4 + 0.5x \) onde \( x \) é o número de passageiros, que varia de 0 a 20.
2. Criar um vetor de valores para \( x \) no intervalo \([0, 20]\).
3. Calcular os valores de \( T(x) \) correspondentes.
4. Plotar o gráfico com os devidos rótulos nos eixos.

Aqui está o código Scilab com os devidos comentários explicando cada parte:

```scilab
// 1. Definir o intervalo de passageiros e a função tarifária
x = 0:0.1:20;  // Vetor de valores para o número de passageiros (x) variando de 0 a 20
T = 4 + 0.5 * x;  // Função tarifária T(x) = 4 + 0.5x

// 2. Plotar o gráfico
plot(x, T);  // Plota a curva T(x) versus x
xlabel("Número de Passageiros (x)");  // Rótulo do eixo x
ylabel("Tarifa (T(x)) - em Reais");  // Rótulo do eixo y
title("Tarifação Inteligente no Transporte Público");  // Título do gráfico

// 3. Melhorar o gráfico com uma linha sólida e cor personalizada
plot(x, T, "r-");  // Plota com linha vermelha
```

### Explicação:

- **`x = 0:0.1:20`**: Cria um vetor de valores para o número de passageiros, variando de 0 a 20, com incrementos de 0.1.
- **`T = 4 + 0.5 * x`**: Calcula os valores da tarifa com base na fórmula dada \( T(x) = 4 + 0.5x \).
- **`plot(x, T)`**: Plota o gráfico com os valores de \( x \) no eixo horizontal e os valores de \( T(x) \) no eixo vertical.
- **`xlabel("Número de Passageiros (x)")`**: Rótulo do eixo x, indicando que ele representa o número de passageiros.
- **`ylabel("Tarifa (T(x)) - em Reais")`**: Rótulo do eixo y, indicando que ele representa a tarifa em reais.
- **`title("Tarifação Inteligente no Transporte Público")`**: Adiciona o título ao gráfico.
- **`plot(x, T, "r-")`**: O gráfico é desenhado com uma linha vermelha.

### Resultado Esperado:

Esse código gerará um gráfico com a função tarifária \( T(x) = 4 + 0.5x \) no intervalo de \( x \in [0, 20] \), com os eixos devidamente rotulados e a curva representando a relação entre o número de passageiros e a tarifa.
