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
## (Questão 1) - Tarifação Inteligente no Transporte Público:

Um sistema de transporte público usa uma tarifa dinâmica que depende do número de passageiros. A tarifa T(x), em reais, é definida como: 

T(x) = 4 + 0.5x,        x ∈ [0,20] 

onde x representa o número de passageiros no ônibus. 

---

### **Interpretação da Fórmula**

A fórmula dada para a tarifa dinâmica do transporte público é:

\[
T(x) = 4 + 0.5x
\]

Onde:

- \( T(x) \) é a tarifa em reais (R$) que depende do número de passageiros, \( x \).
- \( x \) é o número de passageiros no ônibus, variando entre 0 e 20.

#### Significado do coeficiente angular e do termo independente:

1. **Coeficiente angular (0.5)**:
   - O coeficiente angular \( 0.5 \) indica a taxa de variação da tarifa em relação ao número de passageiros. Ou seja, para cada passageiro adicional, a tarifa aumenta R$ 0,50.
   - Esse valor mostra que a tarifa cresce de forma linear à medida que o número de passageiros aumenta.

2. **Termo independente (4)**:
   - O termo independente \( 4 \) representa o valor inicial da tarifa quando não há passageiros (\( x = 0 \)). Ou seja, a tarifa mínima será de R$ 4,00 quando não houver nenhum passageiro no ônibus.
   
### **Análise Gráfica**

A função \( T(x) = 4 + 0.5x \) é uma reta, porque é uma função linear. Ao analisar graficamente:

- A **interseção com o eixo y** (quando \( x = 0 \)) ocorre em \( T(0) = 4 \). Ou seja, quando não há passageiros, a tarifa é R$ 4,00.
- O **coeficiente angular** de 0.5 indica que a reta sobe com uma inclinação constante, ou seja, a cada novo passageiro, a tarifa aumenta R$ 0,50.

**Zeros da função**:
Para encontrar os zeros, precisamos resolver \( T(x) = 0 \):

\[
0 = 4 + 0.5x
\]
\[
0.5x = -4
\]
\[
x = -8
\]

Entretanto, esse valor não faz sentido dentro do contexto da função, pois o número de passageiros não pode ser negativo. Isso confirma que a função não atravessa o eixo x no intervalo \( x \in [0, 20] \), ou seja, a tarifa nunca será zero dentro desse intervalo.

### **Cálculo Aplicado:**

Vamos calcular a diferença máxima entre a menor e a maior tarifa cobradas, dado que o número de passageiros varia entre 5 e 18.

- **Menor tarifa** (quando \( x = 5 \)):
  \[
  T(5) = 4 + 0.5 \times 5 = 4 + 2.5 = 6.5
  \]

- **Maior tarifa** (quando \( x = 18 \)):
  \[
  T(18) = 4 + 0.5 \times 18 = 4 + 9 = 13
  \]

**Diferença máxima entre as tarifas**:
\[
\Delta T = 13 - 6.5 = 6.5
\]

Portanto, a diferença máxima entre a menor e a maior tarifa cobradas é R$ 6,50.

### **Implementação no Scilab**

Agora, vamos ao código Scilab para gerar o gráfico da função e incluir os comentários explicando cada linha:

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

// 4. Destacar o ponto para x = 5 e x = 18, que são os valores de interesse para o cálculo
x_min = 5;
x_max = 18;
T_min = 4 + 0.5 * x_min;  // Calcula a tarifa para x = 5
T_max = 4 + 0.5 * x_max;  // Calcula a tarifa para x = 18

// Plotando os pontos específicos no gráfico
plot(x_min, T_min, "bo");  // Ponto para a menor tarifa (x=5)
plot(x_max, T_max, "go");  // Ponto para a maior tarifa (x=18)

// Exibir as diferenças de tarifa no gráfico
disp("Diferença máxima de tarifa: " + string(T_max - T_min));  // Exibe a diferença máxima entre as tarifas
```

### **Explicação do Código:**

- **`x = 0:0.1:20`**: Define o intervalo de passageiros de 0 a 20 com incremento de 0.1.
- **`T = 4 + 0.5 * x`**: Calcula a tarifa para cada valor de \( x \) no intervalo definido.
- **`plot(x, T)`**: Plota o gráfico da função tarifária.
- **`xlabel` e `ylabel`**: Adiciona rótulos aos eixos x e y para descrever o que cada um representa.
- **`title`**: Define o título do gráfico.
- **`plot(x, T, "r-")`**: Plota a curva da tarifa com linha vermelha.
- **`x_min = 5` e `x_max = 18`**: Define os valores de \( x \) para os quais calculamos as tarifas mínima e máxima.
- **`plot(x_min, T_min, "bo")`** e **`plot(x_max, T_max, "go")`**: Marca no gráfico os pontos correspondentes aos valores de \( x = 5 \) e \( x = 18 \).
- **`disp`**: Exibe a diferença máxima entre as tarifas no console.

### **Esboço Manual do Gráfico**

Para o esboço manual, imagine uma reta começando em \( T(0) = 4 \) e subindo com uma inclinação de 0.5. A reta intercepta o eixo y em \( T = 4 \), e para \( x = 20 \), \( T(20) = 4 + 0.5 \times 20 = 14 \).

Marque os pontos \( x = 5 \) e \( x = 18 \) no gráfico, mostrando que a diferença entre as tarifas nesses pontos é de R$ 6,50.

### **Entrega Final:**

1. **Esboço Manual**: O gráfico mostra uma linha reta iniciando em \( T = 4 \) e subindo com uma inclinação de 0.5.
2. **Cálculos**: A diferença entre a maior e a menor tarifa é R$ 6,50.
3. **Código Scilab**: O código fornecido implementa a fórmula da tarifa dinâmica e gera o gráfico com os pontos de interesse destacados.
4. **Gráfico Gerado**: O gráfico foi gerado com as rotulações nos eixos e com os pontos de interesse.
