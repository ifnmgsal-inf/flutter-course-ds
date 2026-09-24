## Slide 1: Capa

### Anatomia de um Aplicativo Flutter

**Curso Técnico em Informática**  
Desenvolvimento Mobile com Flutter e Dart

*Professor: Leonardo H G Silva*  
*IFNMG-Salinas*

---

## Slide 2: Objetivos 

### O que vamos aprender hoje?

- Entender o que é Flutter e para que serve
- Compreender o conceito de **Widget**
- Conhecer a estrutura básica de um app Flutter
- Identificar os principais widgets de interface
- Entender como os widgets se organizam em árvore
- Reconhecer a diferença entre widgets visuais e funcionais

---

## Slide 3: O que é Flutter?

### Framework para desenvolvimento mobile

- **Flutter** é um framework criado pelo Google
- Permite criar aplicativos para **Android** e **iOS** com um único código
- Usa a linguagem de programação **Dart**
- Baseado em **widgets** para construir a interface

**Vantagens:**
- Desenvolvimento mais rápido
- Interface consistente em diferentes plataformas
- Grande quantidade de widgets prontos

---

## Slide 4: Tudo é Widget!

### O conceito fundamental do Flutter

> "Tudo dentro de um aplicativo Flutter é um **widget**"

**O que é um widget?**
- São os "blocos de construção" da interface
- Cada elemento na tela é um widget (botão, texto, imagem, layout)
- Widgets podem conter outros widgets dentro deles
- Funcionam como peças de LEGO que se encaixam

**Exemplos de widgets:**
- `Text` - exibe texto
- `Icon` - exibe ícones
- `Image` - exibe imagens
- `Container` - caixa para organizar conteúdo

---

## Slide 5: Construindo com Widgets

### Empilhando widgets como LEGO

**Analogia do LEGO:**
- Assim como peças de LEGO, widgets são encaixados uns sobre os outros
- Você constrói a interface widget sobre widget
- Widgets simples formam estruturas complexas

**Exemplo prático:**
```
Aplicativo
└── Scaffold (tela)
    ├── AppBar (barra superior)
    └── Container (conteúdo)
        └── Column (coluna vertical)
            ├── Row (linha horizontal)
            │   ├── Text
            │   └── Icon
            └── Text
```

---

## Slide 6: Scaffold - A Estrutura Básica

### O widget que cria a tela

**Scaffold** é o widget principal que fornece:
- Estrutura básica da tela
- Suporte para barra superior (AppBar)
- Suporte para menu lateral (Drawer)
- Suporte para barra inferior (BottomNavigationBar)
- Área para conteúdo principal

**Sintaxe básica:**
```dart
Scaffold(
  appBar: AppBar(
    title: Text('Meu App'),
  ),
  body: Container(
    // conteúdo aqui
  ),
)
```

---

## Slide 7: AppBar - Barra Superior

### Navegação e título do app

**AppBar** é a barra que fica no topo da tela:

- Exibe o **título** do aplicativo
- Pode conter **ícones de ação** (buscar, menu, configurações)
- Facilita a **navegação** entre telas
- Segue o padrão visual do Material Design

**Exemplo:**
```dart
AppBar(
  title: Text('Minha Aplicação'),
  actions: [
    Icon(Icons.search),
    Icon(Icons.more_vert),
  ],
)
```

---

## Slide 8: Container - Caixa de Conteúdo

### Organizando e delimitando conteúdo

**Container** é uma caixa que pode:
- Delimitar uma área na tela
- Adicionar margens e padding
- Definir cores e bordas
- Conter outros widgets dentro

**É como uma "caixa" que organiza o conteúdo**

**Exemplo:**
```dart
Container(
  margin: EdgeInsets.all(16),
  padding: EdgeInsets.all(8),
  color: Colors.blue,
  child: Text('Conteúdo dentro da caixa'),
)
```

---

## Slide 9: Column - Layout Vertical

### Widgets em coluna (um sobre o outro)

**Column** organiza widgets **verticalmente**:
- Os filhos ficam um **em cima do outro**
- Útil para listas de elementos
- Controla alinhamento vertical e horizontal

**Quando usar:**
- Quando quiser elementos empilhados verticalmente
- Para criar listas de itens
- Para organizar conteúdo de cima para baixo

**Exemplo:**
```dart
Column(
  children: [
    Text('Item 1'),
    Text('Item 2'),
    Text('Item 3'),
  ],
)
```

---

## Slide 10: Row - Layout Horizontal

### Widgets em linha (lado a lado)

**Row** organiza widgets **horizontalmente**:
- Os filhos ficam **lado a lado**
- Útil para colocar ícones e textos juntos
- Controla alinhamento horizontal e vertical

**Quando usar:**
- Quando quiser elementos lado a lado
- Para criar botões com ícones
- Para organizar conteúdo da esquerda para direita

**Exemplo:**
```dart
Row(
  children: [
    Icon(Icons.star),
    Text('Avaliação 5 estrelas'),
  ],
)
```

---

## Slide 11: Widgets de Texto e Ícone

### Elementos básicos de interface

**Text - Exibe texto:**
- Mostra strings na tela
- Pode formatar fonte, cor, tamanho
- É um dos widgets mais usados

```dart
Text('Olá, mundo!',
  style: TextStyle(
    fontSize: 20,
    color: Colors.black,
  ),
)
```

**Icon - Exibe ícones:**
- Mostra ícones do Material Icons
- Útil para botões e indicações visuais

```dart
Icon(Icons.home, color: Colors.blue)
```

---

## Slide 12: Widget de Imagem

### Exibindo imagens no app

**Image** carrega e exibe imagens:

- `Image.asset()` - imagem do projeto
- `Image.network()` - imagem da internet
- `Image.file()` - imagem do dispositivo

**Exemplo - Imagem da internet:**
```dart
Image.network(
  'https://exemplo.com/imagem.jpg',
  width: 200,
  height: 150,
)
```

**Exemplo - Imagem local:**
```dart
Image.asset('imagens/logo.png')
```

---

## Slide 13: Árvore de Widgets

### A estrutura hierárquica do app

**O que é a árvore de widgets?**
- É a organização hierárquica de todos os widgets
- Widgets pais contêm widgets filhos
- Forma uma estrutura de árvore (tree)
- Define como a interface será renderizada

**Exemplo visual:**
```
Scaffold
├── AppBar
│   └── Text (título)
└── Container
    └── Column
        ├── Row
        │   ├── Text
        │   └── Icon
        └── Image.network
```

---

## Slide 14: Do Código para a Tela

### Como o código vira interface

**Estrutura do código Dart:**
```dart
Scaffold(
  appBar: AppBar(
    title: Text('Meu App'),
  ),
  body: Container(
    child: Column(
      children: [
        Row(
          children: [
            Text('Olá'),
            Icon(Icons.star),
          ],
        ),
        Text('Bem-vindo!'),
      ],
    ),
  ),
)
```

**Cada parêntese representa um nível na hierarquia**

---

## Slide 15: Widgets Visuais vs Funcionais

### Nem todo widget é só aparência

**Widgets Visuais (Design):**
- `Text` - mostra texto
- `Icon` - mostra ícone
- `Image` - mostra imagem
- `Container` - organiza layout
- **Função:** Definir aparência e posição

**Widgets Funcionais (Interatividade):**
- `NetworkImage` - carrega imagem da web
- `ElevatedButton` - botão clicável
- `TextField` - campo de entrada
- `ListView` - lista com rolagem
- **Função:** Adicionar interatividade e funcionalidade

---

## Slide 16: Exemplo Prático Completo

### Montando uma tela simples

```dart
Scaffold(
  appBar: AppBar(
    title: Text('Perfil do Usuário'),
  ),
  body: Container(
    padding: EdgeInsets.all(16),
    child: Column(
      children: [
        Image.network('https://exemplo.com/foto.jpg'),
        Row(
          children: [
            Icon(Icons.person),
            Text('João Silva'),
          ],
        ),
        Text('Desenvolvedor Flutter'),
      ],
    ),
  ),
)
```

**Resultado:** Uma tela com barra superior, foto, nome e profissão

---

## Slide 17: Principais Widgets

### Widgets que você precisa conhecer

| Widget | Função | Uso |
|--------|--------|-----|
| **Scaffold** | Estrutura da tela | Base de toda tela |
| **AppBar** | Barra superior | Título e navegação |
| **Container** | Caixa organizadora | Delimita conteúdo |
| **Column** | Layout vertical | Itens em coluna |
| **Row** | Layout horizontal | Itens em linha |
| **Text** | Exibe texto | Mostrar informações |
| **Icon** | Exibe ícone | Elementos visuais |
| **Image** | Exibe imagem | Fotos e ilustrações |

---

## Slide 18: Resumo - Roteiro

### Hands-on

1. **Instalar as ferramentas**
   - Flutter SDK
   - Android Studio ou VS Code
   - Emulador ou dispositivo físico

2. **Criar primeiro projeto**
   - Comando: `flutter create meu_app`
   - Explorar a estrutura de pastas

3. **Praticar widgets**
   - Criar telas simples
   - Combinar diferentes widgets
   - Testar layouts variados

4. **Aprofundar conhecimentos**
   - State Management
   - Navegação entre telas
   - Consumo de APIs

---

## Slide 19: Referências complementares

### Onde aprender mais?

**Documentação Oficial:**
- https://flutter.dev/docs
- https://docs.flutter.dev

**Curso Completo (Gratuito):**
- Playlist no YouTube: "Curso de Flutter e Dart"
- Canal: Polimorfismo
- GitHub: https://github.com/polimorfismo/curso-flutter-e-dart

**Comunidade:**
- Discord do curso
- Stack Overflow
- Grupos no Facebook e Telegram

**Créditos:**
- Conteúdo baseado na aula do Professor Carlos Duarte
- Curso gratuito de Flutter e Dart disponível no YouTube

---

## Slide 20: Atividade Prática

### Mãos à obra!

**Tarefa:** Criar uma tela de perfil simples

**Requisitos:**
- Usar `Scaffold` como base
- Adicionar `AppBar` com título
- Incluir `Container` com padding
- Usar `Column` para organizar
- Adicionar `Row` com ícone e texto
- Inserir pelo menos 3 widgets `Text`
- Adicionar 1 widget `Icon`
- (Opcional) Incluir `Image.network`
