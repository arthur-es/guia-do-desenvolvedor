# Guia do Desenvolvedor Hyerdev
Seja bem-vindo a Hyerdev!

Neste guia iremos passar por cima das boas práticas de desenvolvimento de software que nós adotamos e que o livro código limpo ensina. O Clean Code é uma pratica muito bem vista no mercado pois melhora a legibilidade, manutenibilidade e reuso do código. Prolongando significativamente a vida útil de um produto de software.


## Código Limpo
Para que você entenda melhor o objetivo deste guia, teremos uma breve abordagem sobre Clean Code. De acordo com o livro "*Código Limpo*" de *Robert C. Martin*, um código limpo é um código elegante, legível e que definitivamente foi cuidado e recebeu a atenção de algum profissional.

Para te ajudar a entender um pouco mais sobre esse conteúdo, te recomendamos essa playlist de videos do Felipe Deschamps:

![Miniatura do vídeo do Felipe Deschamps sobre o livro Clean Code](https://github.com/arthur-es/guia-do-desenvolvedor/blob/master/cleancode.png?raw=true)

[Link para a playlist: Clean Code - Felipe Deschamps](https://www.youtube.com/watch?v=9w3o9NHXqu0&list=PLMdYygf53DP5Sc6yFYs6ZmjsuuA2fu0TK&ab_channel=FilipeDeschamps)


Mas por que devemos nos preocupar em cuidar de um código? Só para um futuro desenvolvedor conseguir ler o seu trabalho? Não só isso, um código sujo pode trazer inúmeros problemas a longo prazo, o custo de manutenção de um sistema tende a subir exponencialmente da mesma forma que o débito técnico sobre aquele código.

Um código bem escrito influencia futuros desenvolvedores a manter o código bem escrito, mas se o código está sujo, bagunçado e difícil de ler, a situação tende a piorar. 

## Primeiros Passos
Agora que sabemos da importância e impacto de um código, iremos tratar de sua escrita, sua saúde. Começando pelo básico, iremos tratar da nomeação de variáveis, funções e entidades.

Algumas questões depende da linguagem com qual você está trabalhando, como por exemplo:

    snake_case ou camelCase
  
Portanto, não será abordado neste guia as boas práticas específicas de alguma linguagem, mas sim questões que podem ser tratadas em qualquer uma.

### Nomeando variáveis
Nomear uma variável nunca é uma tarefa fácil, uma vez que é necessário atribuir um nome que explicite sua função/necessidade. O tipo da variável pode ajudar nesses casos, por exemplo:

    activeModal: boolean

Um nome simples, pequeno e que traduz a existência desta variável, definir se um modal está ativo ou não. Um outro nome para esta variável poderia ser:

    isActive: boolean
Porém este nome não sugere o que está ativo ou não, além da palavra "*is*" ser desnecessária neste contexto.

### Nomeando Funções
Da mesma forma que ocorre com as variáveis, uma função deve ter seu nome definido de acordo com o seu papel naquele meio, podemos utilizar os parâmetros recebidos e seu conteúdo de retorno para auxiliar em sua nomeação. Vamos a um exemplo:

    getLoggedUserName(): String {
	    return 'Hyago';
    }
    
    concatNames(first: String, second: String): String {
	    return first.concat(second);
    }

Somente pelo seu nome, podemos perceber a primeira função retorna o Username do usuário logado. Já a segunda concatena dois nomes, sem que seja necessário um nome grande ou explicitar quantos nomes a função iria concatenas, já que seu parâmetros explicitam isso.

Código sujo deste segundo método acima:

    concatTwoNamesAndReturnTheResult(firstName: String, secondName: String): String {
	    return first.concat(second);
    }

### Nomeando Entidades
Entidades e objetos são, talvez, os mais fáceis de se nomear, talvez pelo fato de surgirem de acordo com o negócio o problema do software. Se for uma entidade a ser estendida, que ela tenha seu nome genérico para que isso possa ser notado, como por exemplo:

    Usuario {}
    Aluno extends Usuario {}
    Professor extends Usuario {}

Uma prática ruim e que prejudica o código seria fazer o seguinte: 

    EntidadePessoa {}
    Aluno extends EntidadePessoa {}
    Professor extends EntidadePessoa {}

Não há a necessidade de deixar a nomenclatura tão estranha e genérica a fim de demonstrar algo que já existe um nome conhecido e comum, então a dica é, não invente nomes ou definições que estão fora do mercado ou do senso comum, pois só você saberá o que é.

## Dicas
Caso seja necessário categorizar algo em seu código, use *Enum*, o código fica mais elegante, legível e manutenível. Exemplo:

    Enum Role {
	    ADMIN;
	    SUPPORT;
	    NORMAL;
    }

Caso você tenha uma função onde:

    retornaBoleano(value: Boolean): Boolean {
	    if (value) { return true; }
	    else { return false }
    }

Você pode simplificar e deixar esta função mais elegante fazendo:

    retornaBoleano(value: Boolean): Boolean {
	    return value
    }

As funções fazem a mesma coisa, porém, uma é mais limpa que a outra.

## Conclusão

Lembre-se de deixar o seu código o mais limpo e legível possível, claro que nem sempre iremos conseguir este feito, mas cuidar de um código dando a devida atenção e tempo já é um grande passo. Cuide do código como se fosse seu ambiente de trabalho, afinal, todos gostam de trabalhar em um ambiente bem organizado e limpo.
