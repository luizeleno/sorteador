# Sorteador
Sorteador de pontos para concursos e processos seletivos online da EEL/USP

### Informações

* Os pontos de exemplo estão no arquivo `pontossorteio.yml` do diretório `_data` (no ramo `gh-pages`).
* Para usar o sorteador, carregue uma lista de pontos clicando em **_Abrir arquivo..._**. O arquivo  deve ser em formato texto (.txt, .csv, etc.) com um ponto por linha
* Você também pode editar manualmente os campos dos pontos, mas perderá as alterações se fechar ou recarregar a página (futuras versões terão um botão _Salvar_).
* Um exemplo para fins de teste do sorteador é obtido clicando em _**Carregar exemplo**_
* Use então o botão _**Sortear ponto**_ para fazer o sorteio. Este botão ficará desabilitado até você clicar em _**Apagar seleção**_.
* Uma versão operacional do Sorteador está em <https://computeel.org/sorteador/>.
* O ponto é sorteado usando a seguinte função em _javascript_, que retorna um inteiro aleatório de `min` a `max`, cujos valores são `1` e o número máximo de pontos, respectivamente:
  ```javascript
  function getRndInteger(min, max) {
    var num = Math.floor(Math.random() * (max - min + 1) ) + min;
    return num;
  }
  ```

---

### Observações:

* Julgamos pertinente estabelecer um número máximo de 20 pontos. Se seu arquivo contiver mais pontos, apenas os 20 primeiros serão lidos e uma mensagem será exibida.
  - a variável `MAXPONTOS` no arquivo `_config.yml` controla este número máximo (padrão: 20)
* **_Importante_**: o arquivo a ser lido deve conter um ponto por linha, com a última linha (e apena ela!) em branco, como neste [exemplo](//computeel.org/sorteador/assets/exemplo/exemplo-pontos.txt).

---

© 2020 [Prof. Dr. Luiz T. F. Eleno](http://www.demar.eel.usp.br/docentes/luiz-tadeu-fernandes-eleno.html).
