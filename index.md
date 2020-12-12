---
title: Processo Seletivo - Edital ATAc/EEL/USP 10/2020
---

## Pontos para a prova didática:

<output id="inputs"></output>
<input type="file" id="pontosfile" accept=".txt, .csv, .dat, .yml" hidden />

---

<button type="button" id='exemplo' class='btn' onclick="carrega_exemplo()">Carregar exemplo</button>
<input type="button" id='abrir' class='btn' onclick="abrir()" value="Abrir arquivo...">
<button type="button" id='sorteio' class='btn' onclick="document.getElementById('pontosorteado').innerHTML = sorteia(1, window.N)">Sortear ponto</button>
<button type="button" id='apagar' class='btn' onclick="resetstyle()">Apagar seleção</button>

### Ponto sorteado: <span class="badge" id="pontosorteado"></span>

---

### Como usar:

* Para usar o sorteador, carregue uma lista de pontos clicando em **_Abrir arquivo..._**. O arquivo  deve ser em formato texto (.txt, .csv, etc.) com um ponto por linha.
* Você também pode editar manualmente os campos dos pontos, mas perderá as alterações se fechar ou recarregar a página (futuras versões terão um botão _Salvar_).
* Um exemplo para fins de teste do sorteador é obtido clicando em _**Carregar exemplo**_.
* Use então o botão _**Sortear ponto**_ para fazer o sorteio. Este botão ficará desabilitado até você clicar em _**Apagar seleção**_.

---

### Observações:

* Julgamos pertinente estabelecer um máximo de 20 pontos. Se seu arquivo contiver mais pontos, eles serão ignorados, mas uma mensagem será exibida.
* **_Importante_**: o arquivo a ser lido deve conter um ponto por linha, com a última linha (e apena ela!) em branco, como neste [exemplo]({{site.baseurl}}/assets/exemplo/exemplo-pontos.txt){: target="_blank"}.

<!-- Carregando os scripts -->

{% include scripts.html %}

---

© {{ site.time | date: '%Y' }} [{{ site.name }}]({{ site.dados }}){: target="_blank"}.
