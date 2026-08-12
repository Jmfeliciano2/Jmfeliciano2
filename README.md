from pathlib import Path
import zipfile

out = Path("/mnt/data/Jmfeliciano2-profile")
out.mkdir(parents=True, exist_ok=True)

readme = """<div align="center">

# João Matheus

### Desenvolvedor Frontend · Engenharia de Software — FIAP

Construo experiências web com foco em **estrutura, responsividade e clareza visual**, transformando ideias em interfaces consistentes e bem executadas.

[Portfólio](https://jmfeliciano2.github.io/portifolio/) ·
[LinkedIn](https://www.linkedin.com/in/joaomatheusfeliciano/) ·
[E-mail](mailto:felicianomatheus265@gmail.com)

</div>

---

## Sobre

Curso **Engenharia de Software na FIAP** e direciono minha atuação para desenvolvimento frontend, combinando formação acadêmica com projetos próprios e soluções desenvolvidas na prática.

Trabalho principalmente com **HTML, CSS e JavaScript**, utilizando Git e GitHub para organizar e versionar o desenvolvimento. Gosto de interfaces objetivas, código compreensível e decisões técnicas que façam sentido para o produto — não apenas para a implementação.

## Stack

<p>
  <img src="https://skillicons.dev/icons?i=html,css,js,ts,git,github,vscode" alt="Tecnologias: HTML, CSS, JavaScript, TypeScript, Git, GitHub e VS Code" />
</p>

**Frontend:** HTML5 · CSS3 · JavaScript · TypeScript  
**Ferramentas:** Git · GitHub · VS Code  
**Também estudando e explorando:** C# · SQL · Python

## Projetos selecionados

### [Cinelog](https://github.com/Jmfeliciano2/Cinelog)
Aplicação web para registrar filmes assistidos, notas e favoritos, com foco em organização de conteúdo, interface e interatividade no navegador.

`HTML` `CSS` `JavaScript`

### [AgroSat](https://github.com/Jmfeliciano2/AgroSat)
Estação agrícola para monitoramento de temperatura, umidade e luminosidade, com alertas voltados a pequenos produtores.

`Arduino` `C++` `Prototipação`

### [Vinheria Agnello](https://github.com/Jmfeliciano2/vinheria-agnello)
Website responsivo para apresentação da vinheria, catálogo e canais de contato, trabalhando hierarquia visual e adaptação para diferentes telas.

`HTML` `CSS` `JavaScript`

## Portfólio

Uma visão mais completa dos meus projetos, stack e trajetória está disponível no meu portfólio:

### → [jmfeliciano2.github.io/portifolio](https://jmfeliciano2.github.io/portifolio/)

## Contato

Estou aberto a oportunidades para desenvolver produtos, colaborar com equipes e transformar boas ideias em experiências digitais bem construídas.

**E-mail:** [felicianomatheus265@gmail.com](mailto:felicianomatheus265@gmail.com)  
**LinkedIn:** [joaomatheusfeliciano](https://www.linkedin.com/in/joaomatheusfeliciano/)  
**GitHub:** [Jmfeliciano2](https://github.com/Jmfeliciano2)

---

<div align="center">
  <sub>João Matheus · São Paulo, Brasil</sub>
</div>
"""

(out / "README.md").write_text(readme, encoding="utf-8")

zip_path = Path("/mnt/data/Jmfeliciano2-profile-refeito.zip")
with zipfile.ZipFile(zip_path, "w", compression=zipfile.ZIP_DEFLATED) as zf:
    zf.write(out / "README.md", arcname="README.md")

print(f"README criado: {out / 'README.md'}")
print(f"ZIP criado: {zip_path}")
