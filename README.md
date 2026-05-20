# ClassUp Turma 22 (Gamificação Escolar)

O **ClassUp** é uma ferramenta de gestão pedagógica e gamificação criada para transformar os combinados de convivência e a participação da sala de aula em uma jornada visual dinâmica e engajadora. 

Inspirado em dinâmicas de RPG e jogos eletrônicos, o sistema transforma o esforço diário dos alunos em pontos que os movem por uma trilha digital em tempo real em direção à meta final.

---

## Objetivos do Projeto
* **Estimular a autonomia:** Focar no acompanhamento e evolução dos alunos, mudando a lógica de "punição" para "conquista".
* **Identidade Coletiva:** Customizado especialmente para a **Turma 22**, contando com a liderança digital dos professores: Tia Rosinha, Teacher Ramon e Tia Judvânia.
* **Reconhecimento:** Ao final de cada ciclo, o sistema gera o pódio dos campeões e permite a impressão automática do *Certificado de Aluno Destaque do Mês*.

---

## Tecnologias Utilizadas
* HTML5 / CSS3 (Variáveis Globais e Animações de Keyframes)
* Tailwind CSS (Via CDN para estilização ágil)
* JavaScript Puro (Vanilla JS com manipulação direta da DOM)
* LocalStorage (Para persistência dos dados diretamente no navegador do professor)

---

## Diário de Bordo & Evolução do Código

### [Dia 1] Versão 1.0.0 (O Protótipo Inicial)
* **Status:** Concluído, mas com limitações de ambiente.
* **O que foi feito:** Toda a estrutura visual em formato de arquivo único, lousa virtual (quadro), painel de comando lateral com botões de atalho, ranking dinâmico e modal de pódio integrado ao sistema de impressão de certificados.
* **Lições Aprendidas / Desafio Encontrado:** Ao rodar o protótipo isoladamente em ferramentas de teste de IA, tudo funcionou perfeitamente. Porém, ao tentar incorporar o código em uma página real de produção utilizando o ecossistema WordPress com **Elementor**, encontramos um conflito técnico. O JavaScript disparava o modal de encerramento do mês antes da hora devido a dados fictícios injetados, e o gerenciamento de overflow do Elementor travou os cliques e ponteiros da página (`pointer-events`).

### [Dia 2] Versão 1.1.0 (Correção de Ambiente & Deploy)
* **Status:** Funcional e em produção!
* **O que foi corrigido:**
  1. Limpeza completa dos dados fictícios pesados que forçavam a abertura automática do modal no primeiro carregamento.
  2. Inicialização segura com os alunos reais da sala (**ENZO, ESTER, CECÍLIA e JOSÉ**) começando do zero (0 pontos).
  3. Ajuste fino de segurança na função `closeModal()`, forçando explicitamente a propriedade `document.body.style.pointerEvents = 'auto'` para anular os bloqueios visuais na página causados pelo construtor de blocos do Elementor.
* **Resultado:** O sistema agora roda perfeitamente em tela cheia na nossa hospedagem oficial, mantendo os dados salvos localmente e pronto para ser projetado em sala de aula!

---

## Como visualizar o histórico do código?
Como utilizamos o Git de forma profissional, você não precisa criar vários arquivos separados (como `index_velho.html` e `index_novo.html`). O próprio Git mantém salvo o histórico!
* Para ver como era o código antigo com erros (Versão 1.0.0), basta clicar na aba **"Commits"** do seu repositório no GitHub e selecionar o commit do primeiro dia.
* O arquivo principal `index.html` agora contém a versão mais atualizada e corrigida para produção.
