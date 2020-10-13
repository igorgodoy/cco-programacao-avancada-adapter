# Programação Avançada

Atividade padrão de projeto - **Adapter**.

## Conteúdos

1. [Classificação](https://github.com/igorgodoy/cco-programacao-avancada-adapter#classifica%C3%A7%C3%A3o)
2. [Intenção](https://github.com/igorgodoy/cco-programacao-avancada-adapter#inten%C3%A7%C3%A3o)
3. [Motivação](https://github.com/igorgodoy/cco-programacao-avancada-adapter#motiva%C3%A7%C3%A3o)
4. [Aplicação](https://github.com/igorgodoy/cco-programacao-avancada-adapter#aplica%C3%A7%C3%A3o)
5. [Estrutura](https://github.com/igorgodoy/cco-programacao-avancada-adapter#estrutura)
6. [Participantes](https://github.com/igorgodoy/cco-programacao-avancada-adapter#participantes)
7. [Implementação](https://github.com/igorgodoy/cco-programacao-avancada-adapter#implementa%C3%A7%C3%A3o)

## Adapter

### Classificação

- O **Adapter** define uma estrutura que permite isolar partes do Software. Normalmente utilizado em sistemas legados para comunicação com outro software em particular, integração de bibliotecas para padronização de um meio de acesso. O adapter torna transparente o módulo a ser integrado, ou seja, age como intermediador, funcionando como uma ponte entre duas interfaces incompatíveis.

### Intenção

- Facilitar a adaptação de determinado módulo a ser integrado com um software em particular. Normalmente interfaces incompatíveis para que consigam, desta forma, trabalharem juntas.

### Motivação

- Padronizar a comunicação entre módulos, sistemas e/ou bibliotécas á qualquer software em particular.

### Aplicação

- Comumente utilizado em situações as quais se faz necessária a integração de dois ou mais módulos em um software onde, ao menos um destes módulos, encontra-se com código legado e precisa ser adaptado.

### Estrutura

- Este [diagrama](https://refactoring.guru/images/patterns/diagrams/adapter/structure-object-adapter.png) uma estrutura elaborada baseada nos padrões do **Adapter**.

### Participantes

- *Target*: Define o interface do domínio usada pelo cliente;
- *Client*: Usa o objeto da interface Target conforme definido;
- *Adaptee*: Define uma interface ou contrato existente que precisa ser adaptado;
- *Adapter*: É quem adapta a interface do Adeptee ao Target usado pela aplicação;

### Implementação

[Implementação](https://github.com/igorgodoy/cco-programacao-avancada-adapter/tree/main/example) onde temos uma interface MediaPlayer e uma classe concreta AudioPlayer implementando a interface MediaPlayer. AudioPlayer pode reproduzir arquivos de áudio no formato mp3 por padrão.

Em contrapartida, temos outra interface AdvancedMediaPlayer e classes concretas implementando a interface AdvancedMediaPlayer. Essas classes podem reproduzir arquivos de formato vlc e mp4.

Queremos fazer o AudioPlayer tocar outros formatos também. Para conseguir isso, criamos uma classe de adaptador MediaAdapter que implementa a interface MediaPlayer e usa objetos AdvancedMediaPlayer para reproduzir o formato necessário.

AudioPlayer usa a classe do adaptador MediaAdapter passando o tipo de áudio desejado sem saber a classe real que pode reproduzir o formato desejado. AdapterPatternDemo, nossa classe de demonstração usará a classe AudioPlayer para reproduzir vários formatos..
