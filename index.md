---
title: Processo Seletivo - Editais ATAc/EEL/USP
---

## Pontos para a prova didática:

<output id="inputs">
</output>

<button type="button" id='sorteio' class='btn' onclick="document.getElementById('pontosorteado').innerHTML = sorteia(1, N)">Sortear ponto</button>
<button type="button" id='apagar' class='btn' onclick="resetstyle()">Apagar seleção</button>

### Ponto sorteado: <span class="badge" id="pontosorteado"></span>

---

## Definição dos pontos:

<input type="file" id="pontosfile" accept=".txt, .csv, .dat, .yml" hidden />

<button type="button" id='mais' class='btn' onclick="add_input()">Adicionar ponto</button>
<button type="button" id='menos' class='btn' onclick="remove_input()">Remover ponto</button>
<button type="button" id='limpa' class='btn' onclick="limpa()">Remover todos</button>

<button type="button" id='exemplo' class='btn' onclick="carrega_exemplo()">Carregar exemplo</button>
<button type="button" id='abrir' class='btn' onclick="abrir()">Abrir arquivo...</button>
<a type="button" id='salvar' class='btn' download="pontos.txt" onclick="lista_pontos()">Salvar arquivo...</a>

---

### Como usar:

- Carregue uma lista de pontos clicando em **_Abrir arquivo..._**. O arquivo  deve ser em formato texto (.txt, por exemplo) com um ponto por linha.
- É possível adicionar ou remover campos para inserir manualmente os pontos, clicando nos botões **_Adicionar ponto_** e **_Remover ponto_**, respectivamente. Para não perder as alterações, pode clicar em **_Salvar arquivo..._**.
- Um exemplo para fins de teste do sorteador é obtido clicando em _**Carregar exemplo**_.
- Com a lista de pontos, use  o botão _**Sortear ponto**_ para fazer o sorteio. Este botão ficará desabilitado até você clicar em _**Apagar seleção**_.

---

### Observações:

* Julgamos pertinente estabelecer um máximo de {{site.MAXPONTOS}} pontos. Se seu arquivo contiver mais pontos, eles serão ignorados, mas uma mensagem será exibida.
* **_Importante_**: o arquivo a ser lido deve conter um ponto por linha, com a última linha (e apena ela!) em branco, como neste [exemplo]({{site.baseurl}}/assets/exemplo/exemplo-pontos.txt){: target="_blank" download="exemplo-pontos.txt"}.

<!-- Carregando os scripts -->

{% include scripts.html %}

---

© {{ site.time | date: '%Y' }} [{{ site.name }}]({{ site.dados }}){: target="_blank"}.
