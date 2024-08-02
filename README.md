# mermaidnotes
Práticas de anotações mermaid

### Representação de um diagrama de classes seguindo boas práticas UML. Representação básica


````mermaid

classDiagram

%% Representação de herança
AparelhoTelefonico <|-- Iphone
Aplicativo <|-- ReprodutorMusical
Aplicativo <|-- NavegadorInternet

    

    %% Defining the classes
    class NavegadorInternet{
        +Boolean loginRealizado
        +String paginaInicial
        +List listaFavoritos

        +exibirPagina(String url)
        +addAosFavoritos(String url)
        +adicionarNovaAba()
        +atualizarPagina()
    }
    class ReprodutorMusical{
        +Boolean loginRealizado
        +List listaMusicasCurtidas
        
        +tocar()
        +pausar()
        +parar()
        +selecionarMusica(String musica)
    }
    class AparelhoTelefonico{
        +String modelo
        +String imei
        +String marca

        +realizarChamada(Chamada)
        +atenderChamada(Chamada)
    }
    class Iphone {
        +String numeroTelefonico
        +Date dataFabricacao

        +instalaAplicativo(Aplicativo)
        +executaAplicativo(User)
        +iniciarCorreioDeVoz()
    }
    class Aplicativo {
        +int AplicativoID
        +String nomeAplicativo
        +String marcaCriadora
        
        +inicializaSistema(Iphone)
        +realizaLogin(User)
        +executaProcesos()
    }
    class User {
        +String UserName
        +Date UserDeadline

        +selecionaAplicativo(Aplicativo)
    }

    %% Definição das relações com as respectivas cardinalidades
    Aplicativo "1" --> "0..*" Iphone : executa procesos
    Iphone "1" --> "*" Aplicativo : pode conter
    
    Aplicativo "1..*" --> "1" User : é executado por
    User "1" --> "0..*" Aplicativo : pode acessar

    %% Adição de notas ao diagrama
    note for Iphone "Um celular pode ter aplicativos instalados, realizar chamadas,<br> atender chamadas e Iniciar o correio de voz"

    note for Aplicativo "Um aplicativo pode ser acessado por um Usuário."

    note for User "Um usuário pode acessar e usar vários aplicativos ao mesmo tempo."

    %% Applying CSS classes using shorthand notation
    class Iphone:::celularStyle
    class Aplicativo:::reprodutorMusicalStyle
    class User:::projectStyle

    %% Apply CSS classes using cssClass statement
    %% cssClass "Company, Employee, Project" generalClass

     style Iphone fill: #002266,stroke:#333,stroke-width:4px
     style Aplicativo fill: #206040,stroke: #2eb82e,stroke-width:2px
     style User fill: #990000,stroke: #ffb31a,stroke-width:2px,color:#fff,stroke-dasharray: 5 5
     style ReprodutorMusical fill:#263,stroke: #2eb82e,stroke-width:2px,color:#fff,stroke-dasharray: 5 2
     style NavegadorInternet fill:#263,stroke: #2eb82e,stroke-width:2px,color:#fff,stroke-dasharray: 5 2
````
