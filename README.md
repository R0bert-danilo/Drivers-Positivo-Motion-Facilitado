# 💻 Instalador de Drivers Positivo Motion

Olá, sou **Robert Danilo**, e este é o **Instalador de Drivers Positivo Motion**.

## 🧑‍💻 Quem Eu Sou e Objetivo

Eu sou **aluno de Análise e Desenvolvimento de Sistemas (ADS)** e trabalho na área de **Suporte Técnico N3**. Este projeto nasceu da necessidade de otimizar e padronizar a manutenção de hardware, focando em um dos desafios mais comuns no suporte: a instalação e a gestão de drivers em notebooks Positivo Motion.

O objetivo é criar uma solução simples e robusta, baseada em PowerShell, para **automatizar a verificação, extração e instalação em lote** de pacotes de drivers, eliminando erros manuais e reduzindo o tempo de setup pós-formatação. Convido a comunidade a testar e contribuir!

---

## ✨ Visão Geral do Projeto

O Instalador de Drivers é um utilitário de console (CLI) construído em **PowerShell**, focado na instalação de pacotes de drivers (.INF) em sistemas **Windows**. Ele opera com **privilégios de Administrador** para garantir que a ferramenta nativa `PnPUtil` possa registrar e instalar os drivers no sistema operacional.

### Arquitetura e Componentes Chave

| Componente | Função Técnica |
| :--- | :--- |
| **`SetupDrivers.ps1`** | Script principal em PowerShell. Contém a lógica de menu, extração e controle de progresso. |
| **`IniciarSetup.bat`** | Arquivo de inicialização. Sua função é garantir a elevação de privilégio (`RunAs`) antes de chamar o script PowerShell. |
| **`Expand-Archive`** | Comando nativo do PowerShell para descompactar os arquivos de driver (assumindo `.zip`). |
| **`PnPUtil`** | Ferramenta nativa do Windows (`pnputil /add-driver /install /subdirs`). Responsável por instalar os drivers de forma silenciosa e recursiva em cada pacote. |
| **Função `Update-ProgressDisplay`** | Lógica de feedback visual (barra de progresso) para rastrear a execução de cada pacote. |

### Fluxos de Operação

* **Extração e Instalação (Opção 1):** Verifica se o pacote está compactado, extrai-o para uma pasta e, em seguida, instala o driver. Se a pasta já existir, pula a extração.
* **Instalação Apenas (Opção 2):** Útil se os drivers já foram descompactados manualmente. Percorre as pastas e executa apenas o comando de instalação (`PnPUtil`).
* **Feedback Visual:** Exibe uma barra de progresso para cada pacote, detalhando a ação (**EXTRAINDO** ou **INSTALANDO**) e o nome do arquivo.

## ⬇️ Download e Implementação

A implementação é portátil, requerendo apenas os arquivos `.bat`, `.ps1` e seus pacotes de drivers compactados na mesma pasta.

### 🔗 Link de Download (Pacote Completo)

[**BAIXE o Instalador de Drivers Positivo Motion**](https://1024terabox.com/s/1-xA6A1-6e54-KG9DGP2zLA)

### 📋 Instruções Operacionais

1.  **Estrutura:** Certifique-se de que o **`IniciarSetup.bat`**, o **`SetupDrivers.ps1`** e **todos os arquivos de drivers compactados (`.zip`, etc.)** estejam no mesmo diretório.
2.  **Elevação de Privilégio:** Inicie o arquivo **`IniciarSetup.bat`** (não é necessário clicar com o botão direito, o `.bat` já solicitará a elevação de Administrador).
3.  **Seleção de Fluxo:** Utilize o menu interativo:
    * **[1]** para a primeira execução ou instalação completa.
    * **[2]** para reexecutar apenas o passo de instalação.
4.  **Acompanhamento:** Acompanhe a barra de progresso e as mensagens de `[SUCESSO]` ou `[ALERTA]` para cada pacote de driver.

---

## 💻 Instruções de Desenvolvimento (PowerShell)

Para quem deseja clonar o repositório e modificar o código-fonte, o coração do projeto reside no `SetupDrivers.ps1`.

---

## 🧑‍💻 Contribuição (Contributing)

Contribuições são bem-vindas! Se você encontrar bugs, tiver drivers adicionais para modelos Positivo Motion, ou sugestões para otimizar a performance do PowerShell, sinta-se à vontade para abrir uma *Issue* ou enviar um *Pull Request*.

## ✒️ Criador

**Robert Danilo** - Aluno de ADS e Desenvolvedor.
