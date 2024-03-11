Olá! Eu me chamo Murilo Della Justina

- 🔭 Atualmente estou trabalhando na empresa CISAMURES como estágiario.  
- 🌱 Estou cursando o curso de ciência da computação no IFSC câmpus Lages.
- 💬 Pergunte-me sobre o que tiver interesse em saber.
- 📫 Como chegar até mim: murilod.j1307@gmail.com
- ⚡ Curiosidade: Tenho apenas 17 anos 
<div>
    <a href="https://github.com/Murilodellajustina">
        <img height="180cm" src="https://github-readme-stats.vercel.app/api?username=Murilodellajustina&show_icons-true&theme-dark&include_all_commits=true&coun0t_private-true"/>
        <img height="180cm" src="https://github-readme-stats.vercel.app/api/top-langs/?username=Murilodellajustina&layout-compact&langs_count=168&theme-dark"/>
    </a>
  
</div>
<div style="display: inline_block"><br>
  <img align="center" alt="Rafa-Js" height="30" width="40" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/javascript/javascript-plain.svg">
  <img align="center" alt="Rafa-React" height="30" width="40" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/canva/canva-original.svg">
  <img align="center" alt="Rafa-React" height="30" width="40" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/react/react-original.svg">
  <img align="center" alt="Rafa-HTML" height="30" width="40" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/html5/html5-original.svg">
<div/>
<div>
  <a href = "mailto:murilod,j1307@gmail.com"><img src="https://img.shields.io/badge/-Gmail-%23333?style=for-the-badge&logo=gmail&logoColor=white" target="_blank"></a>
   <a href="https://instagram.com/murilodellajustina" target="_blank"><img src="https://img.shields.io/badge/-Instagram-%23E4405F?style=for-the-badge&logo=instagram&logoColor=white" target="_blank"></a>
</div>
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Murilodellajustina/Murilodellajustina/output/github-contribution-grid-snake-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Murilodellajustina/Murilodellajustina/output/github-contribution-grid-snake.svg">
  <img alt="github contribution grid snake animation" src="https://raw.githubusercontent.com/Murilodellajustina/Murilodellajustina/output/github-contribution-grid-snake.svg">
  name: generate animation

on:
  # run automatically every 24 hours
  schedule:
    - cron: "0 */24 * * *" 
  
  # allows to manually run the job at any time
  workflow_dispatch:
  
  # run on every push on the master branch
  push:
    branches:
    - master
    
  

jobs:
  generate:
    permissions: 
      contents: write
    runs-on: ubuntu-latest
    timeout-minutes: 5
    
    steps:
      # generates a snake game from a github user (<github_user_name>) contributions graph, output a svg animation at <svg_out_path>
      - name: generate github-contribution-grid-snake.svg
        uses: Platane/snk/svg-only@v3
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: |
            dist/github-contribution-grid-snake.svg
            dist/github-contribution-grid-snake-dark.svg?palette=github-dark
          
          
      # push the content of <build_dir> to a branch
      # the content will be available at https://raw.githubusercontent.com/<github_user>/<repository>/<target_branch>/<file> , or as github page
      - name: push github-contribution-grid-snake.svg to the output branch
        uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
</picture>
