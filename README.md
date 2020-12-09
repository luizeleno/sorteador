# Sorteador
Sorteador de pontos para concursos e processos seletivos online da EEL/USP

### Informações

O ponto é sorteado usando a seguinte função em _javascript_:

```javascript
function getRndInteger(min, max) {
  var num = Math.floor(Math.random() * (max - min + 1) ) + min;
  return num;
}
```

que retorna um inteiro aleatório de `min` a `max`, cujos valores são `1` e o número máximo de pontos, respectivamente.

---

© 2020 [Prof. Dr. Luiz T. F. Eleno](http://www.demar.eel.usp.br/docentes/luiz-tadeu-fernandes-eleno.html).
