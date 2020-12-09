# Sorteador
Sorteador de pontos para concursos e processos seletivos online da EEL/USP

### Informações

* Os pontos a serem sorteados estão no arquivo `pontossorteio.yml` do diretório `_data` (no ramo `gh-pages`), que contém uma lista `oficial` e uma de `exemplo`. Ambas devem ter o mesmo número de pontos, mas não há limite para tal número.
* Para usar o sorteador, carregue uma das listas (`exemplo` ou `oficial`). Use então o botão **Sortear ponto** para fazer o sorteio. Este botão ficará desabilitado até você clicar em "Apagar seleção".
* Alternativamente, você pode editar manualmente os campos dos pontos, mas perderá as alterações se fechar ou recarregar a página.
* Uma versão operacional do Sorteador está em <https://computeel.org/sorteador/>.
* O ponto é sorteado usando a seguinte função em _javascript_:
  ```javascript
  function getRndInteger(min, max) {
    var num = Math.floor(Math.random() * (max - min + 1) ) + min;
    return num;
  }
  ```
  que retorna um inteiro aleatório de `min` a `max`, cujos valores são `1` e o número máximo de pontos, respectivamente.

---

© 2020 [Prof. Dr. Luiz T. F. Eleno](http://www.demar.eel.usp.br/docentes/luiz-tadeu-fernandes-eleno.html).
