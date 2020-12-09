---
title: Processo Seletivo - Edital ATAc/EEL/USP 10/2020
---

{% assign min = 1 %}
{% assign max = site.data.pontossorteio.exemplo | size %}

## Pontos para a prova didática:

{% assign n=min%}
<ol>
{% for ponto in site.data.pontossorteio.exemplo %}
<li><input id='{{n}}' type="text" style="width:100%"></li>
{% assign n=n | plus: 1%}
{% endfor %}
</ol>

---

<button type="button" id='sorteio' class='btn' onclick="document.getElementById('pontosorteado').innerHTML = getRndInteger({{min}}, {{max}})">Sortear ponto</button>
<button type="button" id='apagar' class='btn' onclick="resetstyle()">Apagar</button>
<button type="button" id='exemplo' class='btn' onclick="carrega_exemplo()">Carregar exemplo</button>
<button type="button" id='oficial' class='btn' onclick="carrega_oficial()">Carregar pontos</button>

#### Ponto sorteado: <span class="badge" id="pontosorteado">&nbsp;&nbsp;</span>

---

### Informações

O ponto é sorteado usando a seguinte função em _javascript_:

```javascript
function getRndInteger(min, max) {
  var num = Math.floor(Math.random() * (max - min + 1) ) + min;
  return num;
}
```

que retorna um inteiro aleatório de `min` a `max`, cujos valores são `1` e o número máximo de pontos, respectivamente.

<script>
document.getElementById("sorteio").disabled = true;
document.getElementById("apagar").disabled = true;

function getRndInteger(min, max) {
  var num = Math.floor(Math.random() * (max - min + 1) ) + min;
  document.getElementById(num).style.fontWeight = "900";
  document.getElementById("sorteio").disabled = true;
  document.getElementById("apagar").disabled = false;
  return num;
}

function resetstyle() {  
  for(num={{min}}; num<={{max}}; num++) {
    document.getElementById(num).style.fontWeight = null;
    document.getElementById('pontosorteado').innerHTML = "&nbsp;&nbsp;";
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
}

function carrega_oficial() {
  {% assign n=1 %}
  {% for ponto in site.data.pontossorteio.oficial %}
    document.getElementById("{{n}}").value = "{{ponto}}";
    {% assign n=n | plus: 1 %}
  {% endfor %}
  document.getElementById("sorteio").disabled = false;
}
</script>
