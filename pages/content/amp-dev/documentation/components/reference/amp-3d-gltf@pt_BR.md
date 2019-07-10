---
$category@: media
formats:
- websites
teaser:
  text: Exibe modelos 3D no formato GL Transmission Format (gITF).
---

<!--
       Copyright 2018 The AMP HTML Authors. Todos os direitos reservados.

       Licenciado sob a Licença Apache, Versão 2.0 (a "Licença"). O uso deste arquivo só é permitido em conformidade com a Licença.
       Uma cópia da Licença está disponível em

       http://www.apache.org/licenses/LICENSE-2.0

       A menos que exigido pela legislação aplicável ou acordado por escrito, o software fornecido de acordo com a Licença é distribuído "NO ESTADO EM QUE SE ENCONTRA", SEM GARANTIAS OU CONDIÇÕES DE QUALQUER TIPO, expressas ou implícitas.
       Consulte a Licença para ver informações sobre permissões e limitações para o idioma específico.
  -->

#amp-3d-gltf

Exibe modelos 3D no formato GL Transmission Format (gITF).

<table>
  <tr>
    <td width="40%"><strong>Script obrigatório</strong></td>
    <td><code>&lt;script async custom-element="amp-3d-gltf" src="https://cdn.ampproject.org/v0/amp-3d-gltf-0.1.js"&gt;&lt;/script&gt;</code></td>
  </tr>
  <tr>
    <td class="col-fourty"><strong><a href="https://www.ampproject.org/docs/guides/responsive/control_layout.html">Layouts compatíveis</a></strong></td>
    <td>fill, fixed, fixed-height, flex-item, responsive</td>
  </tr>
  <tr>
    <td><strong>Exemplos</strong></td>
    <td>Consulte um <a href="https://ampbyexample.com/components/amp-3d-gltf/">exemplo de amp-3d-gltf</a> no site AMP By Example.</td>
  </tr>
</table>

##Uso

O componente `amp-3d-gltf` exibe modelos 3D que estão no formato gITF.

**Observação**: um navegador compatível com WebGL é necessário para que esses modelos sejam exibidos.

###Exemplo

```html
<amp-3d-gltf
    layout="responsive"
    width="320"
    height="240"
    alpha="true"
    antialiasing="true"
    src="path/to/model.glb"></amp-3d-gltf>
```

###Limitações

Atualmente, só funciona com o glTF 2.0.

Recursos não compatíveis:

- Câmeras incorporadas
- Animação

###CORS

O `amp-3d-gltf` faz uma solicitação `fetch` a partir da origem `https://<random>.ampproject.net`, então `access-control-allow-origin: *.ampproject.net` precisa ser definido no cabeçalho de resposta do endpoint especificado como `src`. O caractere curinga é necessário, porque a origem tem um componente de subdomínio aleatório.

##Atributos

<table>
  <tr>
    <td width="40%"><strong>src [obrigatório]</strong></td>
    <td>Um atributo obrigatório que especifica o URL para o arquivo gltf.</td>
  </tr>
  <tr>
    <td width="40%"><strong>alpha [opcional]</strong></td>
    <td>Um atributo booleano que especifica se o espaço livre na tela é transparente. Por padrão, o espaço livre é preenchido com a cor preta.
        O valor padrão é <code>false</code>.</td>
    </tr>
    <tr>
      <td width="40%"><strong>antialiasing [opcional]</strong></td>
      <td>Um atributo booleano que especifica se o anti-aliasing é ativado ou não. O valor padrão é <code>false</code>.</td>
    </tr>
    <tr>
      <td width="40%"><strong>clearColor [opcional]</strong></td>
      <td>Uma string que precisa conter uma cor CSS válida, que será usada para preencher o espaço livre na tela.</td>
    </tr>
    <tr>
      <td width="40%"><strong>maxPixelRatio [opcional]</strong></td>
      <td>Um valor numérico que especifica o limite superior para a opção de renderização pixelRatio. O padrão é <code>window.devicePixelRatio</code>.</td>
    </tr>
    <tr>
      <td width="40%"><strong>autoRotate [opcional]</strong></td>
      <td>Um atributo booleano que especifica se a câmera deve girar automaticamente ao redor do centro do modelo ou não. O valor padrão é <code>false</code>.</td>
    </tr>
    <tr>
      <td width="40%"><strong>enableZoom [opcional]</strong></td>
      <td>Um atributo booleano que especifica se o zoom deve ser ativado ou não. O valor padrão é <code>true</code>.</td>
    </tr>
  </table>

##Ações

<table>
  <tr>
    <td width="40%"><strong>setModelRotation(x, y, z, xMin, xMax, yMin, yMax, zMin, zMax)</strong></td>
    <td>Define a rotação do modelo. A ordem de rotação é ZYX.
      <ul>
        <li>x/y/z: número 0..1, o padrão é o valor anterior da rotação do modelo.</li>
        <li>min/max: ângulo em radianos, o padrão é 0 / pi * 2, define o intervalo desejado.</li>
      </ul>
      Por exemplo, <code>setModelRotation(x=0.5, xMin=0, xMax=3.14)</code> altera o componente <code>x</code> da rotação para <code>1.57</code>.</td>
    </tr>
  </table>

##Validação

Consulte as [regras do amp-3d-gltf](https://github.com/ampproject/amphtml/blob/master/extensions/amp-3d-gltf/validator-amp-3d-gltf.protoascii) (link em inglês) na especificação do validador de AMP.