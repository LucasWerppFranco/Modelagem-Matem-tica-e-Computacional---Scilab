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

### **1. Interpretação da Fórmula**

A fórmula dada para a tarifa dinâmica do transporte público é:

\[
T(x) = 4 + 0.5x
\]

Onde:

- \( T(x) \) é a tarifa em reais (R$) que depende do número de passageiros, \( x \).
- \( x \) é o número de passageiros no ônibus, variando entre 0 e 20.

#### **1.1 Significado do coeficiente angular e do termo independente**

1. **Coeficiente angular (0.5)**:
   - O coeficiente angular \( 0.5 \) indica a taxa de variação da tarifa em relação ao número de passageiros. Ou seja, para cada passageiro adicional, a tarifa aumenta R$ 0,50.
   - Esse valor mostra que a tarifa cresce de forma linear à medida que o número de passageiros aumenta.

2. **Termo independente (4)**:
   - O termo independente \( 4 \) representa o valor inicial da tarifa quando não há passageiros (\( x = 0 \)). Ou seja, a tarifa mínima será de R$ 4,00 quando não houver nenhum passageiro no ônibus.
   
### **2. Análise Gráfica**

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

### **3. Cálculo Aplicado**

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

### **1. Equação do Movimento**

A altura do drone em função do tempo é dada por:

$$
h(t) = -4t^2 + 16t + 10
$$

Onde:

- \(h(t)\) representa a altura do drone em metros.
- \(t\) é o tempo em segundos após a decolagem, no intervalo \(t \in [0,5]\).

### **2. Interpretação da Equação**

- **Coeficiente \(-4\) (termo de \(t^2\)): Indica uma concavidade para baixo, ou seja, o drone sobe até um ponto máximo e depois desce.
- **Coeficiente \(16\) (termo de \(t\)): Representa a velocidade inicial do drone.
- Termo independente \(10\): Indica a altura inicial do drone ao decolar.

### **3. Esboço Manual**

Antes de utilizar o Scilab, desenhe manualmente a trajetória do drone, incluindo:

- \*\*Altura inicia (**\(h(0)\)**
- \*\*Altura máxima e o tempo em que ocorre-o ponto onde o drone retorna ao solo \(h(t) = 0\)**o \(h(t) = 0\), se estiver dentro do intervalo)**

*(Anexar o esboço manual aqui)*

### **4. Cálculo Aplicado**

#### **4.1 Altura Inicial**

$$
h(0) = -4(0)^2 + 16(0) + 10 = 10
$$

O drone parte de **10 metros** de altura.

#### **4.2 Altura Máxima**

A altura máxima ocorre no vértice da parábola:

$$
t_{\text{máx}} = \frac{-b}{2a} = \frac{-16}{2(-4)} = \frac{16}{8} = 2 \text{ segundos}
$$

Substituindo \(t = 2\) na equação:

$$
h(2) = -4(2)^2 + 16(2) + 10 = 26
$$

A altura máxima é **26 metros** em **2 segundos**.

#### **4.3 Retorno ao Solo**

Resolvendo \(h(t) = 0\):

$$
t = \frac{-16 \pm \sqrt{256 + 160}}{-8} = \frac{-16 \pm 20.4}{-8}
$$

$$
t_2 = \frac{-36.4}{-8} = 4.55
$$

O drone retorna ao solo após **4,55 segundos**.

### **5. Implementação no Scilab**

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
### **1. Equação do Consumo Energético**

A função que modela o consumo de energia agora é:
E(x)=x2−10x−30
E(x)=x2−10x−30

Onde:

- E(x)E(x) representa o consumo de energia em megawatts.

- xx é a quantidade de máquinas em operação.

### **2. Interpretação da Equação**

- **Coeficiente \(1\) (termo \(x^2\))**: Indica que a função é uma parábola com concavidade para cima, ou seja, existe um ponto de mínimo.
- **Coeficiente \(-10\) (termo \(x\))**: Representa a taxa de variação do consumo em relação ao número de máquinas.
- **Termo independente \(30\)**: Indica o consumo energético básico quando nenhuma máquina está em operação.

### **3. Esboço Manual**

Antes de utilizar o Scilab, desenhe manualmente o gráfico da função e identifique:

- **Ponto de mínimo da função** (quantidade ideal de máquinas para menor consumo).
- **Zeros da função** (se existirem dentro do intervalo de interesse).

*(Anexar o esboço manual aqui)*

### **4. Otimização**

Para minimizar o consumo, encontramos o vértice da parábola:

$$
x_{ótimo} = \frac{-b}{2a} = \frac{-(-10)}{2(1)} = \frac{10}{2} = 5
$$

Substituindo \(x = 5\) na equação:

$$
E(5) = (5)^2 - 10(5) + 30 = 25 - 50 + 30 = 5
$$

Portanto, o consumo mínimo de energia é **5 megawatts** quando **5 máquinas** estão em operação.

### **5. Simulação no Scilab**

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

#### **5.1 - Grafico**

![image](https://github.com/user-attachments/assets/f3611393-4ff1-48e4-8f1b-dd066597338e)

---

## **(Questão 4) - Trajetória de um Drone de Entregas:**

Um estudo ambiental prevê que a poluição em uma cidade crescerá linearmente com o tempo, seguindo o modelo: 

P(t) = 50+12t,   t ∈ [0,10] 

onde P(t) é o índice de poluição e t é o número de anos a partir de 2025. 

---

### **1. Equação do Modelo de Poluição**

A poluição da cidade é modelada pela função linear:

$$
P(t) = 50 + 12t
$$

Onde:

- \( P(t) \) é o índice de poluição no tempo \( t \), em unidades específicas de poluição.
- \( t \) é o número de anos a partir de 2025, no intervalo \( t \in [0,10] \).

### **2. Interpretação da Equação**

- **Coeficiente angular (12)**: O coeficiente angular \( 12 \) indica a taxa de crescimento da poluição ao longo do tempo. Ou seja, a cada ano, o índice de poluição aumenta em 12 unidades. Isso significa que, conforme os anos passam, a poluição se intensifica linearmente.

### **3. Projeções para 2030 e 2035**

Queremos calcular o índice de poluição para os anos de 2030 e 2035. Sabemos que \( t = 0 \) corresponde a 2025.

#### **Índice de Poluição em 2030**:

Para 2030, \( t = 5 \) (5 anos após 2025):

$$
P(5) = 50 + 12(5) = 50 + 60 = 110
$$

Logo, o índice de poluição em 2030 será **110 unidades**.

#### **Índice de Poluição em 2035**:

Para 2035, \( t = 10 \) (10 anos após 2025):

$$
P(10) = 50 + 12(10) = 50 + 120 = 170
$$

Logo, o índice de poluição em 2035 será **170 unidades**.

### **4. Política Pública - Limite de Poluição**

A partir do modelo, podemos ver que o índice de poluição atingirá **170 unidades** em 2035. A política pública deve ser implementada antes desse ano, para evitar danos. A sugestão seria:

- **Reduzir a taxa de crescimento da poluição** por meio de iniciativas como:
  - **Implementação de tecnologias mais limpas** no setor industrial.
  - **Incentivos a transportes sustentáveis** (como bicicletas e transporte público eficiente).
  - **Reflorestamento e aumento de áreas verdes**.
  - **Educação ambiental e engajamento da população**.

A meta seria reduzir a taxa de crescimento da poluição para um valor abaixo de 12, para que o índice de poluição se estabilize ou diminua.

### 5. **Representação Gráfica - Esboço Manual e Análise do Gráfico**

- **Esboço Manual**: Antes de usar o Scilab, desenhe a reta do gráfico, começando em \( P(0) = 50 \) (índice de poluição em 2025). A reta terá uma inclinação de 12, o que significa que a cada ano o índice aumenta em 12 unidades.
- **Ponto onde \( P(t) = 0 \)**: Para encontrar os zeros da função, resolvemos \( P(t) = 0 \):
  
  \[
  0 = 50 + 12t \quad \Rightarrow \quad t = -\frac{50}{12} \approx -4.17
  \]

Este valor não faz sentido no contexto do problema, pois não pode haver anos negativos em relação a 2025. Isso confirma que a função nunca atravessa o eixo \( t \).

### **6. Código Scilab - Implementação da Função e Geração do Gráfico**

```scilab
// 1. Definir o intervalo de tempo (anos desde 2025)
t = 0:0.1:10;  // Vetor t de 0 a 10, representando os anos a partir de 2025

// 2. Função de poluição P(t) = 50 + 12t
P = 50 + 12 * t;  // Calcula o índice de poluição para cada valor de t

// 3. Plotar o gráfico
plot(t, P, "r--");  // Plota a função de poluição com linha vermelha tracejada grossa
xlabel("Ano (t - 2025)");  // Rótulo do eixo x, indicando que t é o número de anos a partir de 2025
ylabel("Índice de Poluição (P(t))");  // Rótulo do eixo y, indicando o índice de poluição
title("Crescimento da Poluição Atmosférica");  // Título do gráfico

// 4. Projeção para 2030 e 2035
P_2030 = 50 + 12 * 5;  // Calcula a poluição em 2030
P_2035 = 50 + 12 * 10;  // Calcula a poluição em 2035

// 5. Destacar os pontos para 2030 e 2035
plot(5, P_2030, "bo");  // Ponto para 2030 em azul
plot(10, P_2035, "go");  // Ponto para 2035 em verde

// Exibir os resultados no console
disp("Índice de poluição em 2030: " + string(P_2030));
disp("Índice de poluição em 2035: " + string(P_2035));

// 6. Adicionar legenda ao gráfico
legend("Crescimento da poluição", "Poluição em 2030", "Poluição em 2035");  // Adiciona a legenda explicando os pontos
```

#### **6.1 Grafico**

![image](https://github.com/user-attachments/assets/7e7ee2d4-994d-4081-8ba9-b9941d00e767)

---

## **(Questão 5) - Aplicativo de Transporte:**

---

Um aplicativo de transporte cobra uma taxa fixa de R$ 7,00 assim que a corrida é iniciada. Além disso, a cada quilômetro percorrido, é cobrado um adicional de R$ 2,50. 

---

### **1. Equação do Custo da Corrida**

A equação que representa o custo \( C \) da corrida em função da distância \( d \) percorrida é dada por:

$$
C(d) = 7 + 2.50d
$$

Onde:

- \( C(d) \) é o custo total da corrida em reais (R$).
- \( d \) é a distância percorrida em quilômetros.

A taxa fixa de R$ 7,00 é cobrada assim que a corrida começa, e o valor adicional de R$ 2,50 é cobrado por cada quilômetro percorrido.

### **2. Cálculo do Custo para uma Corrida de 10 km**

Substituindo \( d = 10 \) na equação:

$$
C(10) = 7 + 2.50(10) = 7 + 25 = 32 \text{ reais}
$$

Portanto, o custo de uma corrida de 10 km será **R$ 32,00**.

### **3. Cálculo com Desconto de 10% para Corridas Acima de 15 km**

Se a distância for maior que 15 km, o aplicativo oferece um desconto de 10% no custo da corrida. Vamos calcular o custo para uma corrida de 16 km, por exemplo.

Primeiro, calculamos o custo sem o desconto para \( d = 16 \):

$$
C(16) = 7 + 2.50(16) = 7 + 40 = 47 \text{ reais}
$$

Agora, aplicamos o desconto de 10%:

$$
C_{\text{desconto}} = 47 \times 0.90 = 42.30 \text{ reais}
$$

Portanto, o custo de uma corrida de 16 km com o desconto será **R$ 42,30**.

### **4. Projeção de Custo para Diferentes Distâncias**

Para distâncias menores ou iguais a 15 km, o custo é dado diretamente pela equação \( C(d) = 7 + 2.50d \). Para distâncias maiores que 15 km, deve-se aplicar o desconto de 10%.

### **5. Esboço Manual do Gráfico**

- **Até 15 km**: O gráfico será uma reta crescente com inclinação de \( 2.50 \) e interceptação em \( C(0) = 7 \).
- **Acima de 15 km**: A reta continuará a crescer, mas com a redução de 10% no custo.

O gráfico terá um ponto de inflexão em \( d = 15 \), onde o desconto começa a ser aplicado.

### **6. Código Scilab - Implementação da Função e Geração do Gráfico**

```scilab
// 1. Definir a função custo
function C = custo(d)
    if d <= 15 then
        C = 7 + 2.50 * d;  // Cálculo do custo sem desconto
    else
        C = (7 + 2.50 * d) * 0.90;  // Cálculo do custo com 10% de desconto
    end
endfunction

// 2. Definir o intervalo de distâncias (de 0 a 20 km)
d = 0:0.1:20;  // Distâncias entre 0 e 20 km

// 3. Calcular os custos correspondentes
C_values = arrayfun(custo, d);  // Aplica a função custo para cada valor de d

// 4. Plotar o gráfico
plot(d, C_values, "r--");  // Linha vermelha tracejada
xlabel("Distância (km)");  // Rótulo do eixo x
ylabel("Custo (R$)");  // Rótulo do eixo y
title("Custo da Corrida em Função da Distância");  // Título do gráfico

// 5. Marcar o ponto de desconto
plot(15, custo(15), "bo");  // Ponto de inflexão em d = 15 km

// 6. Exibir o custo de 10 km
disp("Custo de uma corrida de 10 km: " + string(custo(10)));

// 7. Exibir o custo com desconto para 16 km
disp("Custo de uma corrida de 16 km com desconto: " + string(custo(16)));

// 8. Adicionar legenda
legend("Custo da corrida", "Ponto de inflexão (desconto)");
```

#### **6.1 Gráfico**
