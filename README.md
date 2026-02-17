# 🚀 BNC Manager | Vocabulary & Anki Deck Builder

Um sistema web *client-side* projetado para acelerar a aquisição de vocabulário avançado em inglês. Ele utiliza a lista de frequência **BNC (British National Corpus) de 6.318 palavras** e integra-se diretamente com IAs (ChatGPT/Gemini) e o Anki.

Este projeto não é para iniciantes casuais; é uma ferramenta de **Engenharia de Dados Educacional** feita para *Power Users* e autodidatas que desejam alcançar a fluência máxima otimizando o tempo de estudo.

---

## 🎯 O Problema que este Software Resolve

Aplicativos tradicionais (como Duolingo) são otimizados para retenção de usuários, não para eficiência absoluta. O BNC Manager inverte essa lógica: o objetivo é "zerar" a lista o mais rápido possível e abandonar o sistema.

Em vez de criar um *flashcard* para cada palavra isolada (o que geraria 6.000 cartões no Anki), o sistema usa uma abordagem de **Combo de I+1**. Ele junta palavras desconhecidas e gera *prompts* automáticos para que a IA crie frases de alto contexto, permitindo que você aprenda 3 a 4 palavras novas por frase.

---

## ⚡ Principais Funcionalidades

* **📊 Gestão de Frequência:** As 6.318 palavras mais comuns do inglês, ordenadas da mais frequente para a mais rara.
* **🤖 AI Combo Generator:** Copia automaticamente as palavras faltantes para a área de transferência já embutidas em um *prompt* otimizado para gerar frases de contexto no ChatGPT/Gemini.
* **🎓 Sistema de Triagem (Triage):**
    * **Já Sabia (Cinza):** Pula palavras conhecidas para não poluir o Anki.
    * **Difícil (Vermelho):** Marca palavras que precisam de revisão extra.
    * **Fácil (Verde):** Marca palavras absorvidas rapidamente.
* **📤 Exportação Inteligente (Anki):** Gera arquivos `.txt` formatados diretamente para importação no Anki (`Frase (Inglês) | Tradução (Português)`). Permite exportar o log total ou *apenas as frases com palavras difíceis*.
* **☁️ Serverless Cloud Sync:** Não possui banco de dados tradicional. Utiliza a API do GitHub para salvar e sincronizar seu progresso (`.json`) diretamente no repositório, garantindo *anti-overwrite* (proteção contra perda de dados entre dispositivos diferentes).

---

## 🛠️ Tecnologias Utilizadas

* **Frontend:** HTML5, CSS3, Vanilla JavaScript (ES6+).
* **Armazenamento Local:** `localStorage` (Cache rápido).
* **Armazenamento em Nuvem:** GitHub REST API (Upload/Download dinâmico de JSON).
* **Áudio:** Web Speech API (TTS nativo do navegador).
* **Arquitetura:** 100% Client-Side. Custo zero de servidor.

---

## ⚙️ Como Configurar a Sincronização na Nuvem (GitHub Sync)

Para usar o sistema em vários computadores sem perder o progresso:

1.  Gere um **Personal Access Token (PAT)** no seu GitHub:
    * Vá em *Settings > Developer settings > Personal access tokens (Tokens classic)*.
    * Clique em *Generate new token*.
    * Marque a permissão **`repo`** (Full control of private repositories).
    * Gere e copie o token (começa com `ghp_...`).
2.  Abra o BNC Manager no navegador.
3.  Clique no botão **⚙️ (Engrenagem)** no topo da tela.
4.  Preencha os dados:
    * **Token:** Seu token `ghp_...`
    * **Dono:** Seu *username* do GitHub.
    * **Repositório:** O nome deste repositório.
    * **Caminho:** `bnc_backup.json` (ou o nome do arquivo que desejar).
5.  Clique em **Salvar**. Agora você pode usar os botões **☁️ Puxar** e **☁️ Enviar** para manter seu progresso sincronizado.

---

## 📖 Fluxo de Estudo Recomendado (Workflow)

1.  Abra a aba **🎯 Sem Frase**.
2.  Clique em **🗑️ Já sei (Pular)** para palavras óbvias (ex: *time, year, people*).
3.  Quando encontrar palavras desconhecidas, clique em **🤖 Combo (2 palavras)**.
4.  Cole o texto no ChatGPT/Gemini para gerar a frase.
5.  Clique em **➕ Cadastrar**, cole a frase em inglês e a tradução.
6.  Marque a palavra como **🔴 Difícil** se achar o significado complexo.
7.  No final da sessão, clique em **📤 Salvar Seleção & Avançar** e depois em **📥 Baixar (Log)**.
8.  Importe o `.txt` gerado no Anki.
9.  Clique em **☁️ Enviar** para salvar seu progresso no GitHub.

---

*Desenvolvido para automatizar o aprendizado de idiomas.*
