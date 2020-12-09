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

<button type="button" id='sorteio' class='btn' onclick="document.getElementById('pontosorteado').innerHTML = sorteia({{min}}, {{max}})">Sortear ponto</button>
<button type="button" id='apagar' class='btn' onclick="resetstyle()">Apagar seleção</button>
<button type="button" id='exemplo' class='btn' onclick="carrega_exemplo()">Carregar exemplo</button>
<button type="button" id='oficial' class='btn' onclick="carrega_oficial()">Carregar pontos</button>

### Ponto sorteado: <span class="badge" id="pontosorteado"></span>

---

### Como usar:

* Para usar o sorteador, carregue uma das listas (clicando em **Carregar exemplo** ou **Carregar pontos**).
* Você também pode editar manualmente os campos dos pontos, mas perderá as alterações se fechar ou recarregar a página.
* Use então o botão **Sortear ponto** para fazer o sorteio. Este botão ficará desabilitado até você clicar em **Apagar seleção**.

<script>
document.getElementById("sorteio").disabled = true;
document.getElementById("apagar").disabled = true;

function sorteia(min, max) {
  var num = Math.floor(Math.random() * (max - min + 1) ) + min;
  var ponto = document.getElementById(num).value;
  document.getElementById(num).classList.add("sorteado");
  document.getElementById("sorteio").disabled = true;
  document.getElementById("apagar").disabled = false;
  return `${num}. ${ponto}`;
}

function resetstyle() {  
  for(num={{min}}; num<={{max}}; num++) {
    document.getElementById(num).classList.remove("sorteado");
    document.getElementById('pontosorteado').innerHTML = "";
    document.getElementById("sorteio").disabled = false;
    document.getElementById("apagar").disabled = true;
  }
}

function carrega_exemplo() {
  {% assign n=1 %}
  {% for ponto in site.data.pontossorteio.exemplo %}
    document.getElementById("{{n}}").value = "{{ponto}}";
    {% assign n=n | plus: 1 %}
  {% endfor %}
  document.getElementById("sorteio").disabled = false;
  document.getElementById("apagar").disabled = true;
  resetstyle()
}

function carrega_oficial() {
  {% assign n=1 %}
  {% for ponto in site.data.pontossorteio.oficial %}
    document.getElementById("{{n}}").value = "{{ponto}}";
    {% assign n=n | plus: 1 %}
  {% endfor %}
  document.getElementById("sorteio").disabled = false;
  document.getElementById("apagar").disabled = true;
  resetstyle();
}
</script>

---

© {{ site.time | date: '%Y' }} [{{ site.name }}]({{ site.dados }}){: target="_blank"}.
