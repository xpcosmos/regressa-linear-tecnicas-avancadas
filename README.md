# Regressão Linear - Técnicas avançadas

## 1 Introdução
Nesse projeto iremos fazer uma análise de dados e implementar um modelo preditivo utilizando uma distribuição de dados que não segue uma distribuição normal.
Vamos utilizar um conjunto de dados relativamente simples.

### 1.1 Explicando conjunto de dados.

Em nosso conjunto de dados temos 4 variáveis diferentes

* **Valor:**
<br> Essa é a variável que tentaremos explicar através de nossa análise. Ela se refere ao preço dos imóveis

* **Área:**
<br> Utilizaremos essa variável como variável explicativa. Ela expressa a área do imóvel.

* **Dist_Praia:**
<br> Essa variável é explicativa e expressa a distância do imóvel em relação a praia.

* **Dist_Farmacia:**
<br> Essa variável é explicativa e expressa a distância do imóvel em relação a farmácias
 
### 1.2 Objetivo
O objetivo dessa análise é lidar com um conjunto de dados que não apresenta uma curva de distribuição normal.

## 2 Desenvolvimento


### 2.1 Entendendo dados:

Visualização preliminar de tabela de dados

<pre>
Valor	Area	Dist_Praia	Dist_Farmacia
0	4600000	280	0.240925	0.793637
1	900000	208	0.904136	0.134494
2	2550000	170	0.059525	0.423318
3	550000	100	2.883181	0.525064
4	2200000	164	0.239758	0.192374
</pre>

#### Distribuição de dados

Vamos buscar entender de que forma os dados se distribuem 

---
* **Valores**
![3e4c8b50-786b-478d-8c48-7f83c757902e](https://user-images.githubusercontent.com/85235525/145248776-f71d057c-8632-40d4-89c3-4af500100020.png)
---
* **Área**
![4d5d5542-a087-4e40-aaca-5b348ed689ae](https://user-images.githubusercontent.com/85235525/145249064-facbe163-23fc-4307-a737-e7714af64545.png)
---
* **Distância da Praia**
![de2d9ded-8093-41f8-84da-0f4ab31fd6b6](https://user-images.githubusercontent.com/85235525/145249272-98bdd51a-a73a-4b2c-a761-3785c22f9d9b.png)
---
* **Distância farmácia**
![58fb129a-0fd5-4385-b35d-90432dd00c55](https://user-images.githubusercontent.com/85235525/145249409-6d5fa7ff-8946-446c-80c4-b5b0d62bbead.png)

---
### 2.2 Normalização de dados

Vamos tentar normalizar os dados criando variável logarítimas dos dados.

#### Nova distribuição de valores:

![55847803-20e2-4204-94fc-27edba2a2a9c](https://user-images.githubusercontent.com/85235525/145250372-a4fdd223-a87b-45a9-933f-a2fb83f288f0.png)

Temos uma nova distribuição de valores, agora podemos aplicar nossos métodos estísticos, mas antes vamos visualizar a tendência dos dados em relação ao valor do imóvel:

![48b3b776-d1bf-4b65-9584-b5b28123fc0b](https://user-images.githubusercontent.com/85235525/145251971-d5928e5b-2b3a-4769-b422-0e70c3d8994a.png)


#### Estimação de variáveis:

<pre>
================================
 var                   P>|t|    
--------------------------------
log_dist_praia        0.000     
log_area              0.000       
log_dist_farmacia     0.547      
</pre>

<pre>
Teste F: 0.00
R²: 0.80
</pre>

_Não encontramos significância no nosso modelo que incluisse a distância do imóvel da farmácia._

---

#### Estimando novo modelo sem a presença da distância da farmácia.

<pre>
================================
 var                   P>|t|    
--------------------------------
log_dist_praia        0.000     
log_area              0.000          
</pre>

<pre>
Teste F: 0.00
R²: 0.80
</pre>

_Encontramos significância em todos as variáveis do modelos_


### Realizando predições

Vamos aleatoriamente selecionar indices para a realização de nossas predições:

<pre>
[Valor Previsto]  [Valor Real]
---------------------------------
406968            389000
1920020           3900000
1647973           1490000
</pre>

## Conclusão

Nosso modelo foi normalizado e encontramos as significâncias para a validação das variáveis em nosso modelo preditivo.




