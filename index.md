---
title: Processo Seletivo - Edital ATAc/EEL/USP 10/2020
---

{% assign min = 1 %}
{% assign max = site.data.pontossorteio.exemplo | size %}

## Pontos para a prova didática:

<div class="form__group field">
{% assign n=min%}
<ol>
{% for ponto in site.data.pontossorteio.exemplo %}
<li><input class="form__field" id='{{n}}' type="text" style="width:100%"></li>
{% assign n=n | plus: 1%}
{% endfor %}
</ol>
</div>


---

<input type="file" id="pontosfile" hidden />
<button type="button" id='exemplo' class='btn' onclick="carrega_exemplo()">Carregar exemplo</button>
<!-- <button type="button" id='oficial' class='btn' onclick="carrega_oficial()">Carregar pontos</button> -->
<input type="button" id='abrir' class='btn' onclick="abrir()" value="Abrir arquivo...">
<button type="button" id='sorteio' class='btn' onclick="document.getElementById('pontosorteado').innerHTML = sorteia({{min}}, {{max}})">Sortear ponto</button>
<button type="button" id='apagar' class='btn' onclick="resetstyle()">Apagar seleção</button>

### Ponto sorteado: <span class="badge" id="pontosorteado"></span>

---

### Como usar:

* Para usar o sorteador, carregue uma lista de pontos clicando em **_Abrir arquivo..._**. O arquivo com os pontos deve ser um arquivo texto (.txt, .csv, etc.) com um ponto por linha (sem linhas em branco!)
* Você também pode editar manualmente os campos dos pontos, mas perderá as alterações se fechar ou recarregar a página.
* Um exemplo para fins de teste do sorteador é obtido clicando em _**Carregar exemplo**_
* Use então o botão _**Sortear ponto**_ para fazer o sorteio. Este botão ficará desabilitado até você clicar em _**Apagar seleção**_.

---

#### _Atenção_: o sorteador funciona apenas para uma lista de exatamente dez (10) pontos. Planejo no futuro remover essa restrição. Peço desculpas pelo inconveniente.

{% include scripts.html %}

---

© {{ site.time | date: '%Y' }} [{{ site.name }}]({{ site.dados }}){: target="_blank"}.
