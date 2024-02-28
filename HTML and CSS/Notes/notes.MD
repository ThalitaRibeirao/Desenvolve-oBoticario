## HTML

O HTML (hipertexto - um texto que se referencia a outros textos) não é uma linguagem de programação porque **não possui lógica**.
> Um arquivo HTML também pode terminar com a extensão .htm

Diferenças entre HTML (ou HTML4, publicado em 1999) e HTML5:
- Não é necessário utilizar ferramentas externas (como Flash Player) para **renderizar vídeo ou áudio**;
- Possui **compatibilidade com SVG** (vetor gráfico escalável) e MathML (fórmulas científicas);
- Melhorias de **tags semânticas** (criação de article, section, etc).

---

## Referrer (referente)

Está relacionado ao protocolo HTTP. Este campo indica **de onde o usuário está vindo**, antes de acessar a url de destino.

---

- **Quirks Mode:** traduzido como "modo peculiaridade", é ativado quando <span style="background-color: yellow;">não colocamos a tag DOCTYPE</span>. Serve para adaptar versões antigas do HTML para a versão 5, podendo gerar quebras.

> Obs.: em outras versões, era necessário colocar um DTD (definição de tipo de documento). Exemplo:

```
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
```

---

## Tags

- **Doctype**: não é case sensite;
- **em**: similar ao strong, mas que formata em itálico;
- **span**: segmenta textos

---

## CSS

- **Medidas absolutas:** Não dependem de referências e não variam entre dispositivos.
    - **Pixel (px)**; 
    - **Points (pt)**: é relacionado as fontes do projeto, e é utilizado para garantir o tamanho de impressões;
    - **Polegadas (in)**;
    - **Centímetro (cm) e milímetro (mm)**: utilizado para folhas de impressão;
    - **Paica (pc)**: utilizado para folhas de impressão.
    > Na verdade, o píxel do CSS NÃO é realmente um píxel da tela do dispositivo (hardware), e sim o que chamamos de píxel de referência que geralmente é maior do que o píxel real. 
- **Medidas relativas**:
    - **Porcentagem (%)**;  
    - **Ems (em)**: Essa unidade muda para os elementos filhos de acordo com o tamanho da fonte (font-size) do elemento pai. Exemplo:

    ```
    <style>
        #pai{
            font-size: 16px;
        }

        #filho{
            font-size: 2em; /* 32px, porque é 2 vezes o elemento pai (16px)*/
        }
    </style>

    <div id="pai">
        div pai
        <div id="filho">
            div filho
        </div>
    </div>
    ```

    - **Rems (rem)**: Está relacionado com o tamanho do elemento root - igual o em, mas somente para a tag HTML. Facilita o trabalho de tags aninhadas, uma vez que não crescerá exponencialmente.
    
    <div style="display: flex; justify-content: center; margin: 16px 0; font-weight: bold;">
        <p style="background-color: #FFC0CB; display: inline-block; padding: 8px 16px;">
            ❗O tamanho padrão é 16px!
        </p>
    </div>

    > Truque: utiizar font-size de 62,5%

    ```

    html {
    font-size: 62,5%;
    }

    h1 {
        font-size: 1.2rem;  /*equivalente a 12px*/
    }

    p {
        font-size: 2.4rem; /*equivalente a 24px*/
    }

    ```

    Existe uma abordagem que utiliza px, em e rem de maneira bem definida. A ideia consiste em definir o **font-size do elemento root em píxel, módulos utilizando rem e elementos interiores aos módulos utilizando em**, facilitando a manipulação do tamanho global que naturalmente escalará o tamanho para os módulos (utilizando rem) e esses por sua vez escalarão os elementos interiores (que utilizam em e referenciam ao elemento pai).

    - **Ex (ex)**:  Sssa unidade se relaciona com o tamanho da fonte (font-size) que está sendo utilizada naquele momento (font-family), mais especificamente ao tamanho do caractere x dessa fonte em questão (x-height). Esse valor pode vir diretamente com a fonte, o browser pode medir o caractere em caixa baixa (lower case) e se esses dois não funcionarem, o browser estipula um valor de 0.5em para 1ex.

    - **Character unit (ch)**: É definida na documentação como sendo a "medida avançada" da largura do caractere zero ("0"). A ideia é que um elemento com, por exemplo 100ch de largura poderá comportar uma string de 100 caracteres dessa determinada fonte, **caso essa fonte seja monospace (todos os caracteres têm o mesmo tamanho)**.
    - **Viewport width(vw)**: Viewport nada mais é que a área visível de uma página web para o seu usuário, variando de acordo com o dispositivo. 1vw representa 1% do tamanho da largura dessa área visível.
    - **Viewport height (vh)**;
    - **Vmin (viewport minimun)**: Imagine que estamos trabalhando com uma viewport de 1600px de altura e 900px de largura. Nesse caso, 1vmin terá o valor de 9px (1% da menor dimensão!), caso tenhamos 100vmin, esse será igual a 900px;
    - **Vmax (viewport maximun)**.

    > Na versão 9.0 do IE, o vmin foi implementado com um nome diferenciado (vm) Algumas versões do IE ainda não oferecem suporte para o vmax, nas novas versões isso foi corrigido.