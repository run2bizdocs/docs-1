Title: Usando Markdown

# Usando Markdown

La documentación de nuestros productos se produce utilizando el patrón de lenguaje Markdown. Markdown es un lenguaje de marcado ligero que puede utilizar para agregar elementos de formato a documentos de texto en texto simple. Creada por John Gruber en 2004, Markdown es ahora uno de los lenguajes de marcado más populares del mundo.

A continuación se incluyen algunas opciones de sintaxis que se pueden utilizar para crear documentos.

## Sintaxis Básica

Estos son los elementos descritos en el documento de diseño original de John Gruber. Todas las aplicaciones de Markdown soportan estos elementos.

| Elemento | Sintaxis Markdown |
|---------|-----------------|
| Título | `# H1` <br/> `## H2` <br/> `### H3` |
| Negrita | `**texto en negrita**`|
|Cursiva	| `*texto en cursiva*` |
|Bloque de citas	| `> bloque de citas` |
|Lista no ordenada |	`1. Primero elemento` <br/> `2. Segundo elemento` <br/> `3. Tercero elemento` |
|Lista no ordenada	| `- Primero elemento` <br/> `- Segundo elemento` <br/> `- Tercero elemento` |
| Código | `código` |
| Regla horizontal | ``---`` |
| Link | `[título](https://www.exemplo.com)`|
| Imagen | `![alt text](image.jpg)` |


### Encabezamiento

Estruture seus comentários usando cabeçalhos. Os cabeçalhos segmentam comentários mais longos, facilitando a leitura.

Comece uma linha com um caractere hash # para definir um cabeçalho. Organize seus comentários com subtítulos, iniciando uma linha com caracteres hash adicionais, por exemplo, ####. Até seis níveis de títulos são suportados.

Exemplo:

```html
# Esse é um título H1
## Esse é um título H2
### Esse é um título H3
```

### Negrito/Itálico

Exemplo:

```html
*itálico*
**negrito**
***negrito-itálico***^
```

Resultado:

*itálico*
**negrito**
***negrito-itálico***^

### Citação

### Lista ordenada

1. Arrumar a cozinha
2. Preparar ingredientes
3. Cozinhar coisas deliciosas

### Lista não ordenada

Exemplo:

```html
* Leite
* Pão
    * Grãos integrais
* Manteiga
```

Resultado:

* Leite
* Pão
    * Grãos integrais
* Manteiga

### Código

### Linha Horizontal

### Link

### Imagem


## Sintaxe estendida

Esses elementos estendem a sintaxe básica adicionando recursos adicionais. Nem todos os aplicativos Markdown suportam esses elementos.

