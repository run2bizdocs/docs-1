Title: Markdown Basic Syntax

# Markdown Basic Syntax

A documentação de nossos produtos é feita utilizando o padrão de liguagem Markdown. 


## O que é o Markdown?

O Markdown é uma linguagem de marcação leve que você pode usar para adicionar elementos de formatação de documentos em texto simples. Criado por John Gruber em 2004, o Markdown é hoje uma das linguagens de marcação mais populares do mundo.

## Sitax básica

To create a heading, add number signs (#) in front of a word or phrase. The number of number signs you use should correspond to the heading level. For example, to create a heading level three (<h3>), use three number signs (e.g., ### My Header).

### Headings

To create a heading, add number signs (`#`) in front of a word or phrase. The number of number signs you use should correspond to the heading level. For example, to create a heading level three (`<h3>`), use three number signs (e.g., `### My Header`).

examples:
  - markdown: "# Heading level 1"
    html: "<h1>Heading level 1</h1>"
  - markdown: "## Heading level 2"
    html: "<h2>Heading level 2</h2>"
  - markdown: "### Heading level 3"
    html: "<h3>Heading level 3</h3>"
  - markdown: "#### Heading level 4"
    html: "<h4>Heading level 4</h4>"
  - markdown: "##### Heading level 5"
    html: "<h5>Heading level 5</h5>"
  - markdown: "###### Heading level 6"
    html: "<h6>Heading level 6</h6>"
	
### Alternate Syntax

Alternatively, on the line below the text, add any number of `==` characters for heading level 1 or `--` characters for heading level 2.

<table class="table table-bordered">
  <thead class="thead-light">
    <tr>
      <th>Markdown</th>
      <th>HTML</th>
      <th>Rendered Output</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code class="highlighter-rouge">Heading level 1<br/>===============</code></td>
      <td><code class="highlighter-rouge">&lt;h1&gt;Heading level 1&lt;/h1&gt;</code></td>
      <td><h1 class="no-anchor" data-toc-skip>Heading level 1</h1></td>
    </tr>
    <tr>
      <td><code class="highlighter-rouge">Heading level 2<br/>---------------</code></td>
      <td><code class="highlighter-rouge">&lt;h2&gt;Heading level 2&lt;/h2&gt;</code></td>
      <td><h2 class="no-anchor" data-toc-skip>Heading level 2</h2></td>
    </tr>
  </tbody>
</table>