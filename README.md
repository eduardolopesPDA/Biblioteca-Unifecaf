# Biblioteca Digital UniFECAF

Interface web da nova Biblioteca Digital da UniFECAF, criada para facilitar o acesso dos estudantes a livros, materiais acadêmicos e serviços de apoio à aprendizagem.

O projeto transforma o protótipo de baixa fidelidade fornecido pela instituição em uma página final responsiva, alinhada à identidade visual da UniFECAF e desenvolvida exclusivamente com **HTML5** e **CSS3**, sem JavaScript, frameworks ou templates.

## Seções da página

- **Cabeçalho**: marca da biblioteca, navegação principal, acesso à estante pessoal e botão de entrada.
- **Destaque principal**: apresentação da biblioteca, busca por título, autor, assunto ou ISBN e sugestões de termos mais buscados.
- **Categorias**: oito áreas do conhecimento com ícone e quantidade de títulos, além dos outros tipos de material do acervo.
- **Acervo em destaque**: livros mais consultados, com capa, área, título, autor, edição e acesso à leitura.
- **Serviços**: empréstimo digital, normalização ABNT, bases de dados científicas, atendimento com bibliotecário, leitura acessível e sugestão de aquisição.
- **Rodapé**: informações institucionais, links úteis, contato e horário de atendimento.

## Estrutura

```
├── index.html
├── css/
│   └── style.css
└── assets/
    └── imagens/
        ├── logo-unifecaf.png
        └── aluno-com-livros.png
```

## Identidade visual

A paleta parte das cores do logo da UniFECAF:

| Cor | Hex | Uso |
| --- | --- | --- |
| Azul FECAF | `#0B2257` | Cor institucional, destaque principal, títulos e botões |
| Azul noturno | `#071638` | Rodapé e fundos de contraste |
| Verde FECAF | `#35D98A` | Ações principais, indicadores e detalhes da marca |
| Papel | `#F5F7FB` | Fundo das seções alternadas |
| Tinta | `#16213F` | Texto principal |

Os elementos gráficos também vêm do logo: a moldura com canto recortado e o quadrado verde aparecem no destaque principal e nos ícones das categorias.

A tipografia combina **Sora**, uma sans geométrica para títulos e interface, com **Source Serif 4**, uma serifada para textos corridos, reforçando o caráter acadêmico da leitura.

## Responsividade

O CSS foi escrito com abordagem **mobile-first** e media queries em dois pontos principais:

- **Até 639px (celular)**: categorias, livros, serviços e etiquetas viram carrosséis horizontais com `scroll-snap`, reduzindo a altura da página. O card seguinte fica parcialmente visível para indicar que há mais conteúdo.
- **A partir de 640px (tablet)**: as listas voltam a ser grades, com quatro categorias e dois livros por linha.
- **A partir de 1024px (desktop)**: navegação em linha no cabeçalho, destaque em duas colunas, três livros por linha e serviços em duas colunas.

## Integração contínua

O projeto usa GitHub Actions (`.github/workflows/ci.yml`): a cada push e pull request na branch `main`, o HTML é verificado com [html-validate](https://html-validate.org/) e o CSS com [Stylelint](https://stylelint.io/), usando o conjunto de regras padrão.

## Boas práticas aplicadas

- HTML semântico com `header`, `nav`, `main`, `section`, `article`, `address` e `footer`.
- Variáveis CSS para cores, tipografia, espaçamentos e sombras, evitando valores repetidos.
- Capas dos livros construídas em CSS com proporção fixa, e imagens com `object-fit`, sem distorções.
- Foco visível para navegação por teclado, link para pular direto ao conteúdo e textos alternativos nas imagens.
- Respeito à preferência do sistema por movimento reduzido (`prefers-reduced-motion`).
