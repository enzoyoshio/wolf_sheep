# Projeto de Computação Experimental, por Enzo Yoshio

## Instalação

Use o comando no terminal:

```
    $ pip install -e git+https://github.com/projectmesa/mesa#egg=mesa

```

Depois de baixar, o modelo visual pode ser visto ao realizar o comando:

```
    $ mesa runserver
```

# Descrição do modelo 

A escolha pelo modelo usado foi pelo interesse no equilíbrio da natureza, portanto o modelo usado foi o wolf_sheep. As características dessa simulação são:

- Há três tipos de agentes: lobos, ovelhas e grama;
- Os lobos e ovelhas andam aleatoriamente pelo grid, ambos necessitam de energia para se locomover. Lobos ganham energia ao se alimentar de ovelhas, ovelhas ganham energia ao se alimentar de grama;
- Para um lobo se alimentar de uma ovelha é necessário que ambos estejam na mesma célula do grid.

# Descrição da hipótese e das modificações

Minha hipótese para modificar a simulação presa-predador foi assumir que quanto menor o tempo que um predador fica sem comer, maiores são as chances dele sobreviver. A hipótese poderia ser estendida para toda a cadeia alimentar, porém como é apenas um exercício para exercitarmos nosso pensamento crítico e desenvolvimento de hipóteses, além é claro do objetivo de se familiarizar com o framework mesa, o qual utilizaremos bastante nos próximos módulos da matéria para validarmos nossos experimentos e simulações, por esses motivos, uma hipótese mais simples utilizando apenas os predadores foi utilizada.

As modificações feitas foram:

 - Na classe do agente lobo foi introduzida algumas novas variáveis que calculam e verificam quanto tempo um lobo está sem comer, gerando também o tempo médio em que ele fica sem comer.
 - No modelo eu adicionei uma nova variável para limitar quanto tempo um lobo poderia ficar sem comer, pois eu estava interessado no resultado apenas com lobos em uma certa resistência, logo lobos que conseguiam ficar muito tempo sem comer não eram interessantes para as métricas da hipótese.

O que se esperava ao mudar o modelo era que pudessemos calcular o tempo médio que cada lobo fica sem comer e por quanto tempo ele irá viver. Espera-se que os lobos com a média menor de tempo fiquem mais tempo vivos, pois se alimentam mais.

# Planilha

Abaixo está descrito o significado de cada coluna na planilha:

 - RunId: número que identifica a iteração atual
 - iteration: iteração do momento
 - step: em qual passo está
 - width: largura do grid
 - height: altura do grid
 - sheep_reproduce: probabilidade de uma ovelha procriar a cada passo.
 - wolf_reproduce: probabilidade de um lobo procriar a cada passo.
 - wolf_gain_from_food: energia que os lobos ganham ao comer ovelhas.
 - grass: se a grama está totalmente crescida (inicialmente verdadeiro nas simulações).
 - grass_regrowth_time: tempo que leva para a grama crescer novamente após ser comida.
 - sheep_gain_from_food: energia que as ovelhas ganham ao comer grama.
 - initial_sheep: quantas ovelhas existem no início.
 - initial_wolves: quantos lobos existem no início.
 - Wolves: quantidade de lobos que ainda está viva.
 - Sheep: quantidade de ovelhas que ainda está viva.
 - maximum_time_without_eat: quanto tempo o lobo pode ficar sem comer nenhuma ovelha.
