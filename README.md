# 💻 João Habib

**`Desenvolvedor Full Stack`**

Me chamo João Habib da Silva Júnior, tenho 16 anos e vivo no estado de São Paulo, na capital, estou no Terceiro Ano do Ensino Médio Técnico no Senac, no curso técnico em Informática. Estou estudando e me desenvolvendo em linguagens e áreas no Back End como no Front End.

My name is João Habib da Silva Júnior, I'm 16 years old and i live in São Paulo, in the capital, I'm in the Third Year of Technical High School at Senac, on the technical course in IT. I am studying and developing in languages and areas in Back End and Front End.

<p align="left">
    <a href="https://github.com/Joao-Habib-da-Silva?tab=followers">
        <img alt="Seguidores"
            title="Seguidores no Github"
            src="https://img.shields.io/github/followers/Joao-Habib-da-Silva?color=219ebc&labelColor=023047&style=for-the-badge&logo=github&label=Followers&logoColor=white"/>
    </a>
    <a href="https://github.com/Joao-Habib-da-Silva?tab=repositories&sort=stargazers">
        <img alt="Estrelas"
            title="Total de estrelas no Github"
            src="https://img.shields.io/github/stars/Joao-Habib-da-Silva?color=219ebc&style=for-the-badge&labelColor=023047&logo=star&label=Stars"/>
    </a>
</p>

   

   ---

   ### ⌨️ Linguagens e Tecnologias / Languages and Technologys


<img 
    align="left" 
    alt="HTML"
    title="HTML" 
    width="30px" 
    style="padding-right: 10px;" 
    src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/html5/html5-original.svg" 
/>


  <img
    align="left" 
    alt="HTML"
    title="HTML" 
    width="30px" 
    style="padding-right: 10px;"
src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/css3/css3-original.svg" />


 <img
    align="left" 
    alt="HTML"
    title="HTML" 
    width="30px" 
    style="padding-right: 10px;"
src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/javascript/javascript-original.svg" />


 <img 
    align="left" 
    alt="HTML"
    title="HTML" 
    width="30px" 
    style="padding-right: 10px;"
 src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/python/python-original.svg" />
 

  
  <img
      width="30px"
      align="left"
      alt='GIT'
      title='GIT'
      style="padding-right: 10px;"
      src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/git/git-original.svg" />
          
   
 

          
<br/>
<br/>

### 📊 Em progresso...
 <img
      width="30px"
      align="left"
      alt='NPM'
      title='NPM'
      style="padding-right: 10px;"
      src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/npm/npm-original-wordmark.svg" />
      
  <img 
        width="30px"
      align="left"
      alt='NODE'
      title='NODE'
      style="padding-right: 10px;"
      src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/nodejs/nodejs-original-wordmark.svg" />
      
   <img
        width="30px"
      align="left"
      alt='Photoshop'
      title='Photoshop'
      style="padding-right: 10px;"
       src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/photoshop/photoshop-original.svg" />
    
  <img
      width="30px"
      align="left"
      alt='Illustrator'
      title='Illustrator'
      style="padding-right: 10px;"
      src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/illustrator/illustrator-line.svg" />
          
<br/>
          <br/>

### 📊 Estatísticas / Stats


<img src="https://github-readme-stats.vercel.app/api?username=Joao-Habib-da-Silva&show_icons=true&theme=tokyonight&line_height=27" alt="GitHub Stats" />
<img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Joao-Habib-da-Silva&langs_count=8&layout=compact&theme=tokyonight" alt="Top Languages" />


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
