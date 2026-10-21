<div align="center">

# ⚽🧤 Simulador de Pênaltis: Goleiro Robótico & Lançador Automatizado
### *Physical Penalty & Free-Kick Simulator with Automated Ball Launcher and Robotic Goalkeeper*

<!-- Badges de Tecnologias e Hardware -->
[![Arduino / ESP32](https://img.shields.io/badge/Microcontrolador-ESP32%20%7C%20Arduino-00979D?style=for-the-badge&logo=arduino&logoColor=white)](https://arduino.cc)
[![C++](https://img.shields.io/badge/Linguagem-C%2B%2B-00599C?style=for-the-badge&logo=cplusplus&logoColor=white)](https://isocpp.org)
[![3D Printing](https://img.shields.io/badge/Manufatura-Impress%C3%A3o%203D%20(FDM)-FF6F00?style=for-the-badge&logo=makerbot&logoColor=white)](https://en.wikipedia.org/wiki/3D_printing)
[![Mecatrônica](https://img.shields.io/badge/Engenharia-Mecatr%C3%B4nica%20%26%20Controle-0B2D4D?style=for-the-badge)](https://github.com)
[![Status](https://img.shields.io/badge/Status-Em%20Desenvolvimento-238636?style=for-the-badge)](https://github.com)

<br/>

<!-- Typing SVG dinâmico -->
<a href="https://github.com/DenverCoder1/readme-typing-svg">
  <img src="https://readme-typing-svg.demolab.com/?lines=Simula%C3%A7%C3%A3o+Mecatr%C3%B4nica+de+P%C3%AAnaltis+e+Faltas;Lan%C3%A7ador+de+Bolas+com+Ajuste+de+Pot%C3%AAncia+e+%C3%82ngulo;Goleiro+Rob%C3%B3tico+com+Movimenta%C3%A7%C3%A3o+Linear+e+Angular;Estrutura+Modular+em+Impress%C3%A3o+3D&font=Fira%20Code&center=true&width=650&height=35&color=88e788&vCenter=true&pause=800&size=16" alt="Typing SVG" />
</a>

<p align="center">
  Sistema eletromecânico e interativo que reproduz dinâmicas reais de cobrança de pênaltis e faltas com controle automatizado de lançamento e defesa.
</p>

</div>

---

<!-- ==================== ILUSTRAÇÃO CONCEITUAL DO PROJETO ==================== -->
<p align="center">
  <img src="https://github.com/DiegoTarcisio/fix-readme/raw/main/assets/images.jpg" alt="Conceito do Projeto - Goleiro e Lançador de Bola" width="250" style="border-radius: 12px;" />
  <br/>
  <sub><i>Esboço conceitual do sistema: posicionamento do lançador motorizado e curso de defesa do goleiro robótico na trave.</i></sub>
</p>

---

<!-- ==================== SOBRE O PROJETO ==================== -->
<details open>
  <summary><b>📌 Sobre o Projeto</b></summary><br/>

  <p align="justify">
    O projeto consiste em uma <b>arena mecatrônica de futebol em escala física</b>, desenvolvida para simular a disputa clássica entre cobrador e goleiro em cobranças de pênaltis e faltas.
  </p>
  <p align="justify">
    O sistema é composto por dois subsistemas sincronizados: um <b>Lançador Mecânico de Bolas</b> (capaz de variar velocidade, elevação e direção do chute) e um <b>Goleiro Robótico</b> posicionado sobre um trilho linear sob o travessão, capaz de se deslocar lateralmente e executar movimentos de bloqueio angular.
  </p>

  <b>Objetivos Principais:</b>
  <ul>
    <li><b>Automação e Repetibilidade:</b> Testar trajetórias e forças de chute de maneira calibrada e programável.</li>
    <li><b>Interação e Gamificação:</b> Permitir modos de disputa contra o robô (humano vs. máquina ou máquina vs. máquina).</li>
    <li><b>Prototipagem Integrada:</b> Combinar modelagem CAD 3D, controle de motores via PWM/Step e eletrônica embarcada.</li>
  </ul>
</details>

<br/>

<!-- ==================== ARQUITETURA E SUBSISTEMAS ==================== -->
<details open>
  <summary><b>⚙️ Subsistemas Mecânicos & Arquitetura</b></summary><br/>

  ```mermaid
  graph TD
    subgraph Módulo Lançador
      A[Interface de Controle / Botões] --> B[Ajuste de Ângulo e Potência]
      B --> C[Motor de Lançamento / Rodas de Tração]
      C --> D[Disparo da Bola]
    end

    subgraph Módulo Goleiro Robótico
      E[Microcontrolador ESP32 / Arduino] --> F[Motor de Passo / DC - Eixo X]
      E --> G[Servomotor - Braços e Salto]
      F --> H[Movimento Linear no Trilho da Trave]
      G --> I[Defesa do Goleiro]
    end

    D -.->|Trajetória do Chute| I
