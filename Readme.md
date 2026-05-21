Este projeto implementa um sistema robótico programável que utiliza uma interface de teclado estilo telefone para gravar sequências de movimentos, monitoradas por um display Nokia 5110 e feedback por voz.

# 🚀 Funcionalidades - Programação por Teclado: 

Use a tecla `*` para iniciar a gravação e números para definir a rota. - Sensor de Presença: O ultrassom HC-SR04 monitora obstáculos ou movimentos frontais. - Feedback por Voz: O módulo ISD1820 reproduz um áudio pré-gravado ao detectar presença. - Interface Visual: LCD Nokia 5110 exibe o log de comandos e status dos sensores em tempo real.

# 🔌 Conexões Críticas - ISD1820: 

Conectado ao pino `A5` para disparo automático. - Teclado: Mapeado em pinos digitais e analógicos para otimização de espaço no Nano. - L293D: Controla a tração dos motores através das saídas PWM.

# 🛠️ Instruções de Uso 1.

Grave sua mensagem de voz pressionando o botão físico no módulo ISD1820. 2. No Arduino, pressione `*` para entrar em modo de programação. 3. Digite a sequência (ex: 2 para frente, 8 para trás). 4. Pressione `#` para o robô executar a memória. 5. Se algo cruzar o caminho do sensor ( < 20cm), o áudio será disparado

### Dica Profissional:

O LCD Nokia 5110 opera em 3.3V. Certifique-se de usar resistores de 10k em série ou um conversor de nível lógico entre os pinos do Nano (5V) e o LCD para não danificar o display. O módulo ISD1820 pode ser alimentado diretamente pelos 5V do Arduino, mas o disparo pelo pino analógico (`A5`) como digital é seguro e eficiente.

Este é um projeto com um propósito social e técnico muito claro. Abaixo, estruturei o arquivo `README.md` com o rigor de um miniartigo técnico, destacando o papel do Trash Bot no evento Arduino Day e a importância da conscientização contra a Dengue.


# 🧹Trash Bot: Robô Recepcionista e Agente de Saúde 🤖

## Resumo

O Trash Bot é um sistema robótico autônomo e interativo desenvolvido para o Arduino Day. Sua missão principal foi atuar como um robô recepcionista com um viés socioambiental: promover a conscientização sobre o descarte correto de resíduos sólidos. O projeto utiliza a tecnologia para mitigar a proliferação do mosquito *Aedes aegypti*, combatendo o acúmulo de lixo em residências, principal foco de criadouros da Dengue.


## 1. Introdução e Contexto

No cenário do Arduino Day, o Trash Bot serviu como uma demonstração prática de como a computação física pode ser aplicada a problemas de saúde pública. Ao detectar a presença de visitantes, o robô interage através de mensagens de voz e interface visual, alertando sobre os perigos de recipientes que acumulam água e ensinando como eliminá-los.

## 2. Hardware e Arquitetura de Sensores

Para cumprir sua função de recepcionista e educador, o robô foi equipado com uma arquitetura de sensores que permite percepção espacial e interação humano-máquina (HMI).

### 2.1 Percepção Espacial (Ultrassom HC-SR04)

O sensor ultrassônico funciona através da emissão de ondas mecânicas de alta frequência. O tempo de retorno (eco) é processado pelo Arduino Nano para calcular a distância de objetos frontais.

* Funcionalidade: Detecção de presença para iniciar a interação. * Capacidade: Alcance de 2cm a 400cm, com precisão de aproximadamente 3mm.

### 2.2 Telemetria Ambiental (DHT22 ou NTC)

Utilizado para monitorar as condições térmicas do ambiente onde o robô está operando.

* Funcionalidade: Dados ambientais exibidos no display, correlacionando altas temperaturas com o aumento da atividade reprodutiva do mosquito. * Capacidade: Alta precisão para monitoramento de microclimas residenciais.

### 2.3 Interface de Voz (ISD1820)

Diferente de sistemas puramente visuais, o módulo ISD1820 permite uma comunicação auditiva direta.

* Funcionalidade: Reprodução de alertas educativos pré-gravados (“Não deixe água acumulada!”, “Lixo no lixo!”). * Capacidade: Gravações de até 10 segundos com acionamento via pulso lógico.

### 2.4 Visualização e Entrada de Dados (Nokia 5110 & Teclado)

* LCD Nokia 5110: Utilizado para fornecer feedback visual e logs de sistema (temperatura, distância e status). * Teclado Matricial: Permite que o operador programe rotas de patrulhamento específicas dentro do ambiente da recepção.

## 3. Especificações Técnicas (Lista de Materiais)

* Microcontrolador: Arduino Nano (ATmega328P). * Driver de Potência: Shield Motor L293D (Ponte H). * Locomoção: 2 Motores DC com redução (Chassi 2WD). * Interface de Entrada: Teclado Matricial 4×4. * Sensores: Ultrassom HC-SR04 e DHT22. * Áudio: Módulo ISD1820 + Alto-falante 8Ω 0.5W. * Display: LCD Nokia 5110 (PCD8544).

## 4. Metodologia de Programação

O software foi desenvolvido em C++, estruturado em uma máquina de estados finitos (FSM). O modo “Gravação” captura os inputs do teclado matricial e armazena os vetores de movimento na RAM, enquanto o modo “Execução” utiliza esses dados em conjunto com as leituras do sensor ultrassônico para evitar colisões durante o patrulhamento educativo.

## 5. Conclusão

O Trash Bot demonstrou ser uma ferramenta eficaz de engajamento durante o Arduino Day. A união entre automação e conscientização social prova que a robótica não se limita a tarefas industriais, sendo capaz de educar e salvar vidas através da prevenção de doenças como a Dengue.

## 📚 Referências

1. BANZI, M. *Getting Started with Arduino*. O'Reilly Media, 2011.
2. DATASHEET HC-SR04. *Ultrasonic Sensor Module*. Disponível em: [Documentação técnica].
3. DALLAS SEMICONDUCTOR. *DS18B20 Programmable Resolution 1-Wire Digital Thermometer*.
4. ORGANIZAÇÃO MUNDIAL DA SAÚDE (OMS). *Prevenção e Controle da Dengue*. 2024.


*Projeto desenvolvido por Jose Joaquim Brandão Neto e apresentado no Arduino Day.*
