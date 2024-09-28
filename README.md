# Portifólio •  Júlia Pereira Quitério
Repositório Dedicado ao Portifólio do API - Banco de Dados

Este repositório é dedicado ao Portifólio dos Projetos Integradores que envolve o API , que são projetos dedicados a aplicação de todo o Aprendizado repassado em sala de aula, com o objetivo de maior aproveitamento de todo o conhecimento adquirido.

# Sobre mim


<p align="center"><img src="julia.png" width="300" height="320" alt="Imagem de Júlia"></p>

<br>

Me chamo Júlia Pereira Quitério, e sou estudante de Banco de Dados (6º semestre) na Fatec de São José dos Campos (SP). Tenho grande admiração pelo universo dos dados e da tecnologia. Atualmente, atuo como Analista de Dados com foco em meios de pagamento, onde posso aplicar e ampliar meus conhecimentos. Tenho buscado destacar meus aprendizados e torná-los cada vez mais visíveis, sempre aberta a contribuir e a aprender. Trabalhar com os projetos APIs tem me permitido expandir minhas habilidades, não apenas em Banco de Dados, mas também em outras áreas técnicas (hard skills) e de desenvolvimento pessoal (soft skills), enriquecendo minha abordagem profissional.

Este Trabalho de Graduação (TG), na modalidade Portfólio das Aprendizagens, foi desenvolvido a partir de um Projeto Integrador (APIs) e apresentado à Faculdade de Tecnologia de São José dos Campos como parte dos requisitos para a obtenção do título de Tecnóloga em Banco de Dados.

# Projetos API


<details><summary>1º semestre</summary>


<h3> 1º semestre - 1/2022 </h3>

Parceiro Acadêmico: <a href="https://fatecsjc-prd.azurewebsites.net/">Fatec Prof. Jassen Vidal - São José dos Campos | Professor Fabiano Sabha</a>


<h4>Link do repositório:</h4>

<p align="left">
 <a href="https://github.com/juliaquiterio/GrupoCachinhos">Acesse aqui</a>
</p>

<div align="center">

<img src="mo_viagem.png" alt="Grupo Cachinhos" width="300" height="290">


</div>



<h2>Assistente Virtual de Viagens</h2>

<h3>Descrição do Projeto</h3>
Mó Viagem é uma assistente virtual é uma aplicação web feita em <a href="https://www.python.org/">Python</a> criada para ajudar turistas a planejar roteiros de viagem. Nossa missão é mostrar aos usuários como eles podem explorar e aproveitar ao máximo as belezas de seu próprio país, muitas vezes ainda desconhecidas ou subestimadas.




<h4><li><b>Desafio Proposto</b></li></h4>
        <p align="justify">
       O professor Fabiano Sabha que representa o nosso cliente (Fatec Prof. Jassen Vidal) propôs o desafio de criar uma assistente virtual utilizando python como linguagem principal, ficando a critério do Grupo escoher a finalidade para tal.
        </p>




<summary><h2>Tecnologias Aplicadas</h2></summary>
<img src="https://www.tshirtgeek.com.br/wp-content/uploads/2021/03/com001.jpg" width="150" height="150">

</p>
          <a href="https://www.python.org/">Python</a>
          <p align="justify">
         O Python é uma linguagem de programação amplamente usada em aplicações da Web, desenvolvimento de software, ciência de dados e machine learning (ML).No projeto foi utilizado com um dos requisitos especificados e foi a principal linguagem para construção da aplicacão web. Abaixo tenho listadas as bibliotecas que utilizamos: </p>

<h3>Bibliotecas Python</h3>

- **SpeechRecognition**: Reconhece e interpreta fala humana.
- **PyAudio**: Interface Python para trabalhar com áudio.
- **API OpenWeather**: Acessa dados meteorológicos em tempo real.
- **Pandas**: Analisa e manipula dados.
- **Wikipédia**: Busca e recupera conteúdo da Wikipédia.
- **Requests**: Simplifica requisições HTTP.
- **Translator**: Traduz textos entre idiomas.
- **Holidays**: Informa sobre feriados em diversos países.
- **Re**: Pesquisa e manipula texto com expressões regulares.
- **Webbrowser**: Abre URLs no navegador padrão.
- **Pyttsx3**: Síntese de voz no Python.


<h2>Contribuições Pessoais</h2>


<details>
    <summary>Backend</summary>

  __Desenvolvimento do Roteiro e Curiosidades:__
   Como desenvolvedora eu pude lidar com a Tecnologia do Python , utilizando as bibliotecas da Wikepedia, PyAudio,  Re e Webbrower, onde utilizei a junção dessas bibliotecas para que o Usuário pudesse saber mais sobre os roteiros das cidades onde ele buscava a partir de uma chamada HTTPS na Wekipedia como referência e ele conseguia ouvir e assim ter uma gama de roteiros em que ele pudesse explorar, e sobre curiosidades daquele local que ele estava perguntando a Assistente Virtual.

Veja abaixo um exemplo do Script:

```
#Roteiro de viagens
        elif "roteiro" in texto:
            convertFala("Qual cidade você quer conhecer")

            rec = sr.Recognizer()

            with sr.Microphone() as mic:
                print("Por favor, fale o nome da cidade para saber o roteiro de viagem: ")
                rec.adjust_for_ambient_noise(mic)
                audio = rec.listen(mic)

            roteiro = rec.recognize_google(audio, language="pt-BR")

            wikipedia.set_lang('pt')

            resposta = wikipedia.page(roteiro)
            print('Roteiro da cidade escolhida: ', roteiro)
            print('\n')
            print("Caso retorne em branco não foi encontrado o roteiro da cidade desejada.")

            conteudo = resposta.section(section_title='Turismo')
            conteudo2 = resposta.section(section_title='Cultura')

            print(conteudo)
            convertFala(conteudo)

            print("Cultura da cidade:", roteiro)
            print('\n')
            print(conteudo2)
            convertFala(conteudo2)
            # A biblioteca wikipedia RETORNA NONE para subtópicos, ainda que correspondam ao tópico 'Turismo/Cultura' (função elif/else não funciona neste caso)
            print('')
```




```
 #Curiosidades
        elif "curiosidades" or "curiosidade" in texto:
            
            convertFala("Quer conhecer qual cidade")
            rec = sr.Recognizer()

            with sr.Microphone() as mic:
                print("Por favor, fale o nome da cidade para saber as curiosidades: ")
                rec.adjust_for_ambient_noise(mic)
                audio = rec.listen(mic)

            curiosidade = rec.recognize_google(audio, language="pt-BR")
                      
            wikipedia.set_lang('pt')
            
            resposta = wikipedia.summary(curiosidade, sentences=2)
            print(resposta)
            convertFala(resposta)
            
        #Lista de Desejos
        elif "desejo" in texto:
            convertFala("Você deseja visualizar a lista ou adicionar")
            print("\n")
            print("1- Visualizar")
            print("2- Adicionar")
            print("\n")

            rec = sr.Recognizer()

            with sr.Microphone() as mic:
                print("Escolha uma opção: ")
                rec.adjust_for_ambient_noise(mic)
                audio = rec.listen(mic)

            resposta = rec.recognize_google(audio, language="pt-BR")

            if ("visualizar" in resposta):
                arquivo = open('lista.txt', 'r')
                print("----Lista de Desejos----")

                for linha in arquivo:
                    print(linha.rstrip())
                    convertFala(linha.rstrip())

                print("Para retirar um destino da lista, vá até o arquivo lista.txt e elimine o que desejar")
                convertFala("Para retirar ou alterar um destino da lista, vá até o arquivo lista.txt e elimine ou altere o que desejar")
                arquivo.close()

            elif ("adicionar" in resposta):
                from classe import listadesejo
                arquivos.append(listadesejo())
                arquivo = open('lista.txt', 'a')

                convertFala("Qual cidade você deseja visitar")
                rec = sr.Recognizer()

                with sr.Microphone() as mic:
                    print("Qual o nome da cidade: ")
                    rec.adjust_for_ambient_noise(mic)
                    audio = rec.listen(mic)

                nomecidade = rec.recognize_google(audio, language="pt-BR")

                arquivos[contador].setnomecidade(nomecidade)

                convertFala("Qual o nome do estado brasileiro")
                rec2 = sr.Recognizer()

                with sr.Microphone() as mic:
                    print("Qual o nome do estado: ")
                    rec2.adjust_for_ambient_noise(mic)
                    audio = rec2.listen(mic)

                estado = rec2.recognize_google(audio, language="pt-BR")

                arquivos[contador].setestado(estado)

                convertFala("Quais são os pontos turísticos")
                rec3 = sr.Recognizer()

                with sr.Microphone() as mic:
                    print("Quais os pontos turísticos: ")
                    rec3.adjust_for_ambient_noise(mic)
                    audio = rec3.listen(mic)

                ponto = rec3.recognize_google(audio, language="pt-BR")

                arquivos[contador].setponto(ponto)

                arquivo.write("--------------------" + "\n")
                arquivo.write("Nome da Cidade:" + arquivos[contador].getnomecidade() + "\n")
                arquivo.write("Nome do Estado:" + arquivos[contador].getestado() + "\n")
                arquivo.write("Pontos Turísticos:" + arquivos[contador].getponto() + "\n")
                arquivo.write("--------------------" + "\n")
                arquivo.close()

                print("Destino adicionado com sucesso")
                convertFala("Destino adicionado com sucesso")
            else:
                convertFala("Não entendi, poderia repetir")
```

<h2>Lições Aprendidas</h2>


<p>
Como desenvolvedora, tive a oportunidade de aprender, inicialmente, sobre o que é um Projeto Integrador na faculdade, o que contribuiu significativamente para meu desenvolvimento tanto educacional quanto profissional. Nesse processo, pude vivenciar o desenvolvimento de um projeto do zero, trabalhando em equipe, lidando com um cliente e, acima de tudo, enfrentando desafios. Aprendi novas formas de desenvolver meu raciocínio lógico e aplicar os conhecimentos adquiridos ao projeto. Além disso, atuei no Backend, utilizando bibliotecas com as quais ainda não havia trabalhado, explorando sua performance e entendendo como poderiam beneficiar o projeto.


   __- Hard Skills:__ <br>
   Python <br>
   Lógica de Programação <br>
   Metodologia Ágil | Scrum

   __- Soft Skills:__ <br>
   Organização <br>
   Proatividade <br>
   Trabalho em equipe
</p>




</details>



</details>

----

<details><summary>3º semestre</summary>

<h3> 3º semestre - 2/2023 </h3>

Parceiro Acadêmico: <a href="https://www.domrock.net/">Dom Rock</a>


<h4>Link do repositório:</h4>

<p align="left">
 <a href="https://github.com/equipe-vox/api-3sem">Acesse aqui</a>
</p>

<div align="center">

<img src="https://lh3.googleusercontent.com/DQwTyeS8X7nOJnhzfO5WKebBPgcO2XI1jVB9SPGiEDBtoeCdW8X5F2h2MoKN4uDuH6sW0epYnlxhtKnBtjtlI2mH4Q03d4MVbg-TdA=w680" alt="Dom Rock" width="500" height="97">

</div>


<h2>Sistema de Gerenciamento de Vendas</h2>

<h3>Descrição do Projeto</h3>
Sales Vox é uma aplicação web de um Sistema de Gerenciamento de Vendas com foco em auxiliar os vendedores a terem uma visão sobre suas vendas e o administrador que poderia ter um controle geral sobre.

<h4><li><b>Desafio Proposto</b></li></h4>
        <p align="justify">
       A empresa Dom Rock lançou um desafio aos alunos do curso de Banco de Dados para que auxiliasse na resolução para um obstáculo que era acompanhar alguns KPI's através de Dashboards de um sistema  de Gerenciamento de Vendas. Como solução geramos uma aplicação WEB  com Spring Boot possibilitando que o usuário acompanhasse 
o andamento das vendas e pudesse tirar algumas respostas através do que os dados informavam.
        </p>

<details>
<summary>Tecnologias Aplicadas</summary>
<img src="https://www.digics.si/wp-content/uploads/2020/09/spring_boot_logo.png" width="300" height="150">

</p>
          <li><a href="https://spring.io/">Spring Framework</a></li>
          <p align="justify">
         Segundo <a href="https://www.treinaweb.com.br/blog/o-que-e-o-spring-boot/">TreinaWeb</a> o Spring Boot é um framework que torna fácil a criação de aplicações Spring autossuficientes e robustas, possibilitando a execução imediata. Contudo isso só é possível por conta da abordagem opinativa sobre a plataforma Spring e bibliotecas de terceiros, que permite ao desenvolvedor gastar o mínimo de tempo possível configurando o projeto, e sim codificando suas regras de negócio. Foi utilizado como o principal framework para o desenvolvimento da aplicação web e foi de grande importância para o mesmo, facilitando o processo ao longo das sprints.</p>
          <img src="https://logodownload.org/wp-content/uploads/2022/12/figma-logo-1.png" height="150">
          <li><a href="https://www.figma.com/">Figma</a></li>
          <p align="justify">
          Segundo <a href="https://www.alura.com.br/artigos/figma">Alura</a> o Figma é uma plataforma colaborativa para construção de design de interfaces e protótipos, pertencente a empresa Fima, Inc. O objetivo era o de criar uma ferramenta que trouxesse colaboração entre pessoas e times, permitindo criar um produto para as mais diversas plataformas, mantendo a acessibilidade do sistema. Foi utilizado para o desenvolvimento do Front-end podendo colaborar de forma crucial para o desenvolvimento das telas em geral do projeto.</p>
          <img src="https://logospng.org/download/react/logo-react-1024.png" height="150">
          <li><a href="https://react.dev/">React</a></li>
          <p align="justify">
          O React, também conhecido como React.js ou ReactJS, é uma biblioteca de código aberto JavaScript amplamente utilizada para construir interfaces de usuário (UI) interativas e dinâmicas. É um componente fundamental no desenvolvimento de aplicativos web modernos e é especialmente popular para a criação de interfaces de usuário de página única (Single Page Applications - SPAs), de acordo
          <a href="https://kenzie.com.br/blog/react/.">Kenzie</a>. O React foi utilizado também para o desenvolvimento em parte do Front-end assim colaborando com a parte visual utilizando bibliotecas que apoiaram no desenvolvimento dos Dashboards.</p>
          <img src="https://th.bing.com/th/id/R.55692e7a8d3fa0da6a2325630ad177d1?rik=MPH0G8OKchACqA&pid=ImgRaw&r=0" height="150">
          <li><a href="https://www.apachefriends.org/pt_br/index.html">XAMPP</a></li>
          <p align="justify">
         Segundo  <a href="https://www.techtudo.com.br/noticias/2012/02/o-que-e-xampp-e-para-que-serve.ghtml">TechTudo</a> o XAMPP é um pacote com os principais servidores de código aberto do mercado, incluindo FTP, banco de dados MySQL e Apache com suporte as linguagens PHP e Perl. Foi utilizado para acesso ao nosso banco local como um servidor local.</p>
         <img src="https://th.bing.com/th/id/R.a0d754098a11d27b496dd867e9bcb26e?rik=ktyhKrtGerv2SA&riu=http%3a%2f%2fjcpdev.com%2fwp-content%2fuploads%2f2015%2f06%2fmysql-logo_2800x2800_pixels1.png&ehk=stX862qDhFHMNl5t8sy91A9mlH6zUShTkbwH8E8cxsc%3d&risl=&pid=ImgRaw&r=0" height="150">
         <li><a href="">MySQL Workbench</a></li>
         <p align="justify">
         Segundo <a href="https://www.danielimamura.com.br/manual-completo-do-mysql-workbench/">Danieli Mamura</a> MySQL Workbench é a ferramenta oficial do MySQL. É um ambiente completo que permite além de realizar consultas, criar diagramas e trabalhar com engenharia reversa.Utilizamos para o desenvolvimento do DDL das tabelas que utilizamos em nossa aplicação.
         </p>
         </details>

<h3>Contribuições Pessoais</h3>


<details>
    <summary>Backend - Rota HTTPs Login do Vendedor</summary>

  __Desenvolvimento da Tela de Login do Vendedor:__
   Como desenvolvedora eu pude lidar com a Tecnologia do Spring Boot focada no Backend onde usamos juntamente com a Arquitetura Rest podendo criar as rotas para o Login da persona (Vendedor), onde ele poderia acessar a rota permitindo o mesmo acessar a aplicação.


Segue o link abaixo das descrições para maior visibilidade:


```
@RestController
@CrossOrigin(origins = "*")
@RequestMapping("/vendedor")
public class VendedorController {

    @Autowired
    private VendedorRepository vendedorRepository;

@PostMapping("/login")
    public ResponseEntity<?> login(@RequestBody LoginRequest loginRequest) {
        String email = loginRequest.getEmail();
        String senha = loginRequest.getSenha();

        Vendedor vendedor = vendedorRepository.findByEmailAndSenha(email, senha);
        Admin admin = adminRepository.findByEmailAndSenha(email, senha);

        if (vendedor == null && admin == null) {
            return new ResponseEntity<Vendedor>(HttpStatus.BAD_REQUEST);
        }

        if (admin != null) {
            return new ResponseEntity<Admin>(admin, HttpStatus.OK);
        }

        return new ResponseEntity<Vendedor>(vendedor, HttpStatus.OK);
    }
```


<a href=https://github.com/equipe-vox/api-3sem/tree/main/api>Acesse aqui o repositório</a>

</details>


<details>
<summary>Modelagem de dados - DDL</summary>

__Apoio ao Desenvolvimento do Banco de Dados:__
 Fui responsável por dar o apoio a modelagem de Dados tanto as etapas de DER quanto MER e o DDL. Podendo aplicar os conhecimenro adquiridos em sala de aula.

 Segue abaixo um trecho do DDL:

 ```

create database banco;
use banco;

create table administrador(
    id bigint auto_increment primary key,
    email varchar(50) not null,
    nome varchar(50) not null,
    senha text not null
);

create table vendedor(
	id bigint auto_increment primary key,
	nome varchar(50) not null,
	nome_gerencia varchar(30) not null,
	senha text not null
);

create table cliente(
    id varchar(200) not null,
    cod_cliente varchar(200) not null,
    fk_vendedor bigint null,
    nome varchar(50) not null,
    primary key(id,cod_cliente),
    foreign key (fk_vendedor) references vendedor(id)
);

```


 </details>


 <details>
    <summary>Metodologia Ágil</summary>
<p>Eu pude contribuir como Product Owner , mais conhecido como PO do nosso grupo Vox. Assim realizando o levantamento dos requisitos que mais faziam sentido. E em paralelo pude contribuir com o Back-end do projeto atuando tanto na parte do Banco de Dados, quanto no código. </br>
Sendo as atividades desempenhadas:
</p>
 
 - __Definição dos Requisitos:__ Como Product Owner eu pude fazer o Backlog do Produto que era alinhado de acordo com os requisitos prioritários do Produto seguindo a metodologia de projeto do Scrum Master, que defini seguindo o que seria de maior valor (entregável) a cada Sprint. E pude também montar o Burndown usando a ferramenta de Excel onde tinhamos uma maior visibilidade do tempo que estava percorrendo.

 Segue o link abaixo das descrições para maior visibilidade:

<a href= https://github.com/equipe-vox/api-3sem#backlog-do-produto>Backlog do Produto</a> •
<a href= https://github.com/equipe-vox/api-3sem#link-disponivel-do-burndown> Burndown do Produto</a>

</details>

<h3>Lições Aprendidas</h3>


<p>
Como Desenvolvedora pude me desenvolver em Raciocínio Lógico e aprender mais sobre Spring Boot e ver como utilizá-lo para o desenvolvimento de projetos.E além da parte do BackEnd pude me desenvolver mais focada em Banco de Dados utilizando os conhecimentos passados em sala de aula e poder aplicar para desevolver a Modelagem dos dados.


   __- Hard Skills:__ <br>
   Java (Spring Boot) <br>
   Modelagem em Banco de Dados


   __- Soft Skills:__ <br>
   Organização <br>
   Proatividade
</p>


<p>
Como Product Owner(PO) pude aprender o dia a dia de como lidar e principalmente se comunicar com o cliente, e como isso é de suma importância para o desenvolvimento de um projeto, e que a organização é um ponto  que não pode ser deixado de lado , trabalhando juntamente com o time de desenvolvedores podemos alinhar os prazos e definir os requisitos de maior valor de entrega para o Cleinte.


   __- Hard Skills:__ <br>
   Ferramenta de Auxilio para Metodologia<br>

   __- Soft Skills:__ <br>
   Organização <br>
   Gestão de Projeto <br>

</p>
</details>

----