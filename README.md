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
## **(Questão 1) - Tarifação Inteligente no Transporte Público:**

Um sistema de transporte público usa uma tarifa dinâmica que depende do número de passageiros. A tarifa T(x), em reais, é definida como: 

T(x) = 4 + 0.5x,        x ∈ [0,20] 

onde x representa o número de passageiros no ônibus. 

---

### ** 1. Interpretação da Fórmula**

A fórmula dada para a tarifa dinâmica do transporte público é:

\[
T(x) = 4 + 0.5x
\]

Onde:

- \( T(x) \) é a tarifa em reais (R$) que depende do número de passageiros, \( x \).
- \( x \) é o número de passageiros no ônibus, variando entre 0 e 20.

#### 1.1 Significado do coeficiente angular e do termo independente:

1. **Coeficiente angular (0.5)**:
   - O coeficiente angular \( 0.5 \) indica a taxa de variação da tarifa em relação ao número de passageiros. Ou seja, para cada passageiro adicional, a tarifa aumenta R$ 0,50.
   - Esse valor mostra que a tarifa cresce de forma linear à medida que o número de passageiros aumenta.

2. **Termo independente (4)**:
   - O termo independente \( 4 \) representa o valor inicial da tarifa quando não há passageiros (\( x = 0 \)). Ou seja, a tarifa mínima será de R$ 4,00 quando não houver nenhum passageiro no ônibus.
   
### ** 2. Análise Gráfica**

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

### **3. Cálculo Aplicado:**

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

### **4. Implementação no Scilab**

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

// Adicionando a legenda ao gráfico.
legend("T_x = 4 + 0.5*x")
```

#### **4.1 Grafico**

![image](https://github.com/user-attachments/assets/f7040110-917f-45f0-9359-48dc77d01a36)

---

## **(Questão 2) - Trajetória de um Drone de Entregas:**

O percurso de um drone de entregas é modelado pela equação da altura em função do tempo: 

h(t) = −4t2 + 16t + 10,  t ∈ [0,5] 

onde h(t) é a altura em metros e t é o tempo em segundos após a decolagem.

--- 

### Análise do Percurso de um Drone de Entregas

Este documento apresenta a análise da trajetória de um drone de entregas modelada por uma equação quadrática. O objetivo é compreender o comportamento da função e implementar a simulação no Scilab.

### 1. Equação do Movimento

A altura do drone em função do tempo é dada por:

$$
h(t) = -4t^2 + 16t + 10
$$

Onde:

- \(h(t)\) representa a altura do drone em metros.
- \(t\) é o tempo em segundos após a decolagem, no intervalo \(t \in [0,5]\).

### 2. Interpretação da Equação

- **Coeficiente \(-4\) (termo de \(t^2\)): Indica uma concavidade para baixo, ou seja, o drone sobe até um ponto máximo e depois desce.
- **Coeficiente \(16\) (termo de \(t\)): Representa a velocidade inicial do drone.
- Termo independente \(10\): Indica a altura inicial do drone ao decolar.

### 3. Esboço Manual

Antes de utilizar o Scilab, desenhe manualmente a trajetória do drone, incluindo:

- \*\*Altura inicia (**\(h(0)\)**
- \*\*Altura máxima e o tempo em que ocorre-o ponto onde o drone retorna ao solo \(h(t) = 0\)**o \(h(t) = 0\), se estiver dentro do intervalo)**

*(Anexar o esboço manual aqui)*

### 4. Cálculo Aplicado

#### 4.1 Altura Inicial

$$
h(0) = -4(0)^2 + 16(0) + 10 = 10
$$

O drone parte de **10 metros** de altura.

#### 4.2 Altura Máxima

A altura máxima ocorre no vértice da parábola:

$$
t_{\text{máx}} = \frac{-b}{2a} = \frac{-16}{2(-4)} = \frac{16}{8} = 2 \text{ segundos}
$$

Substituindo \(t = 2\) na equação:

$$
h(2) = -4(2)^2 + 16(2) + 10 = 26
$$

A altura máxima é **26 metros** em **2 segundos**.

#### 4.3 Retorno ao Solo

Resolvendo \(h(t) = 0\):

$$
t = \frac{-16 \pm \sqrt{256 + 160}}{-8} = \frac{-16 \pm 20.4}{-8}
$$

$$
t_2 = \frac{-36.4}{-8} = 4.55
$$

O drone retorna ao solo após **4,55 segundos**.

### 5. Implementação no Scilab

```scilab
// 1. Definir o intervalo de tempo
t = 0:0.1:5;
h = -4*t.^2 + 16*t + 10;

// 2. Plotar o gráfico
plot(t, h, "r-");
xlabel("Tempo (s)");
ylabel("Altura (m)");
title("Trajetória do Drone de Entregas");

// 3. Destacar os pontos principais
t_max = 2;
h_max = 26;
plot(t_max, h_max, "bo");

t_solo = 4.55;
plot(t_solo, 0, "go");

// Exibir valores no console
disp("Altura inicial: 10 metros");
disp("Altura máxima: " + string(h_max) + " metros em t = " + string(t_max) + " s");
disp("Tempo de retorno ao solo: " + string(t_solo) + " s");

// Adicionar legenda
legend("Trajetória do drone", "Altura máxima", "Retorno aosolo");
```

#### **5.1 - Grafico**

![image](https://github.com/user-attachments/assets/d0c4f1b1-d39b-488a-a41e-d30e98d23e2f)

---

## **(Questão 3) - Otimização do Consumo de Energia em uma Indústria:**

O consumo de energia de uma indústria em função da produção de máquinas é modelado por: 

E(x) = x2 − 10x + 30,	x -30

onde E(x) é o consumo energético em megawatts e x é a quantidade de máquinas em operação.  

---

### Otimização do Consumo de Energia em uma Indústria

Este documento apresenta a análise da função que modela o consumo de energia em uma indústria, visando determinar a quantidade ótima de máquinas em operação para minimizar o consumo energético.

1. Equação do Consumo Energético

A função que modela o consumo de energia agora é:
E(x)=x2−10x−30
E(x)=x2−10x−30

Onde:

- E(x)E(x) representa o consumo de energia em megawatts.

- xx é a quantidade de máquinas em operação.

### 2. Interpretação da Equação

- **Coeficiente \(1\) (termo \(x^2\))**: Indica que a função é uma parábola com concavidade para cima, ou seja, existe um ponto de mínimo.
- **Coeficiente \(-10\) (termo \(x\))**: Representa a taxa de variação do consumo em relação ao número de máquinas.
- **Termo independente \(30\)**: Indica o consumo energético básico quando nenhuma máquina está em operação.

### 3. Esboço Manual

Antes de utilizar o Scilab, desenhe manualmente o gráfico da função e identifique:

- **Ponto de mínimo da função** (quantidade ideal de máquinas para menor consumo).
- **Zeros da função** (se existirem dentro do intervalo de interesse).

*(Anexar o esboço manual aqui)*

### 4. Otimização

Para minimizar o consumo, encontramos o vértice da parábola:

$$
x_{ótimo} = \frac{-b}{2a} = \frac{-(-10)}{2(1)} = \frac{10}{2} = 5
$$

Substituindo \(x = 5\) na equação:

$$
E(5) = (5)^2 - 10(5) + 30 = 25 - 50 + 30 = 5
$$

Portanto, o consumo mínimo de energia é **5 megawatts** quando **5 máquinas** estão em operação.

### 5. Simulação no Scilab

```scilab
// 1. Definir o intervalo de produção de máquinas
x = 0:0.1:10;  // O vetor x representa a quantidade de máquinas em operação, de 0 até 10 com incremento de 0.1

// 2. Função de consumo de energia E(x) = x^2 - 10x - 30
E = x.^2 - 10*x - 30;  // Calcula o consumo de energia para cada valor de x

// 3. Plotar o gráfico
plot(x, E, "b-");  // Plota a função E(x) com a curva em azul
xlabel("Número de Máquinas");  // Rótulo do eixo x (quantidade de máquinas)
ylabel("Consumo de Energia (MW)");  // Rótulo do eixo y (consumo de energia em megawatts)
title("Otimização do Consumo Energético");  // Título do gráfico

// 4. Destacar o ponto mínimo
x_min = 5;  // O número de máquinas no ponto mínimo, obtido com a fórmula do vértice
E_min = 5^2 - 10*5 - 30;  // Calcula o consumo de energia no ponto mínimo
plot(x_min, E_min, "ro");  // Plota o ponto mínimo no gráfico, usando um marcador vermelho

// 5. Exibir valores no console
disp("Número ideal de máquinas: " + string(x_min));  // Exibe no console o número ideal de máquinas
disp("Consumo mínimo de energia: " + string(E_min) + " MW");  // Exibe no console o consumo de energia mínimo

// 6. Adicionar legenda ao gráfico
legend("Consumo energético", "Ponto mínimo de consumo");  // Adiciona a legenda no gráfico
```

#### 5.1 - Grafico

![image](https://github.com/user-attachments/assets/f3611393-4ff1-48e4-8f1b-dd066597338e)

