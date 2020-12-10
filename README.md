# Sorteador
Sorteador de pontos para concursos e processos seletivos online da EEL/USP

### Informações

* Os pontos de exemplo estão no arquivo `pontossorteio.yml` do diretório `_data` (no ramo `gh-pages`).
* Para usar o sorteador, carregue uma lista de pontos clicando em **_Abrir arquivo..._**. O arquivo com os pontos deve ser um arquivo texto (.txt, .csv, etc.) com um ponto por linha (sem linhas em branco!)
* Você também pode editar manualmente os campos dos pontos, mas perderá as alterações se fechar ou recarregar a página.
* Um exemplo para fins de teste do sorteador é obtido clicando em _**Carregar exemplo**_
* Use então o botão _**Sortear ponto**_ para fazer o sorteio. Este botão ficará desabilitado até você clicar em _**Apagar seleção**_.
* Uma versão operacional do Sorteador está em <https://computeel.org/sorteador/>.
* O ponto é sorteado usando a seguinte função em _javascript_, que retorna um inteiro aleatório de `min` a `max`, cujos valores são `1` e o número máximo de pontos, respectivamente.
  ```javascript
  function getRndInteger(min, max) {
    var num = Math.floor(Math.random() * (max - min + 1) ) + min;
    return num;
  }
  ```
* A versão atual só funciona para um número de exatamente dez (10) pontos. Pretendo remover essa restrição em futuras versões.

---

© 2020 [Prof. Dr. Luiz T. F. Eleno](http://www.demar.eel.usp.br/docentes/luiz-tadeu-fernandes-eleno.html).
