# Rubin

**O critério de um grande produtor, dentro do seu Claude.**

A IA resolveu o problema de criar. Ela te dá dez nomes, cinco ofertas, três roteiros, e diz que todos estão ótimos. O que falta agora é alguém que saiba escolher.

O Rubin é uma skill para o Claude inspirada no jeito de trabalhar do produtor Rick Rubin, que produziu Johnny Cash, Adele, Red Hot Chili Peppers e Beastie Boys e ficou conhecido por escutar uma obra até descobrir o que ela quer ser, e então tirar tudo que está no caminho.

Você manda `/rubin` e ele:

- **escuta** o que a sua obra está tentando ser (às vezes não é o que você acha);
- acha **o que está vivo** nela, e protege isso;
- toma **no máximo três decisões**, as que mais mudam o resultado (não uma lista de 20 correções);
- vai além de cortar: troca a ordem, vai ao oposto, muda o formato, manda recomeçar ou diz que **está pronta, não mexe**;
- **escolhe** entre opções e diz por que cada uma das outras cai;
- devolve a versão aplicada, na sua voz, ou um experimento para testar em cinco minutos;
- termina com **uma pergunta** que te obriga a decidir.

E ele não se mete onde não foi chamado. **Só entra quando você manda `/rubin`.** No resto do tempo, o Claude trabalha do jeito de sempre.

---

## O que dá pra fazer com ele

### 1. Matar ou salvar uma ideia de negócio antes de gastar seis meses nela
```
/rubin Quero criar um SaaS de agendamento para clínicas de estética, com IA que responde no WhatsApp, prontuário, financeiro e programa de fidelidade.
```
Ele acha a única parte que ninguém mais tem, aponta o que está ali porque "todo mundo tem", e te dá o menor teste que mostra se vale construir.

### 2. Escolher o nome do produto entre 15 opções
```
/rubin Opções de nome pro meu curso de finanças para autônomos: [cola a lista]
```
Escolhe um. Diz em uma linha por que cada outro cai: genérico, difícil de soletrar, preso a uma moda, parece banco.

### 3. Desmontar a oferta antes do lançamento
```
/rubin [cola a página de vendas ou a descrição da oferta]
```
Ele olha os bônus, a garantia, o desconto e a urgência e te diz o que está ali por força da oferta e o que está ali por medo dela não se sustentar sozinha.

### 4. Olhar a primeira tela do seu site, app ou landing page
```
/rubin [anexa o print]
```
O que o olho vê primeiro, o que deveria ver, o que dá para tirar, e por que o seu título serve para qualquer empresa do mundo.

### 5. Escolher a thumbnail ou a capa que para o dedo
```
/rubin Qual dessas três thumbs? [anexa as imagens]
```
Ele julga no tamanho real em que a imagem vai ser vista, não em tela cheia.

### 6. Cortar o roteiro do vídeo, da aula ou da palestra
```
/rubin [cola o roteiro]
```
Marca o primeiro ponto em que a pessoa sairia do vídeo e diz o que fazer com tudo que vem antes dele.

### 7. Revisar o deck de investimento ou a apresentação de vendas
```
/rubin [anexa o PDF]
```
Qual é a única coisa que a sala tem que lembrar amanhã, e quais slides competem com ela.

### 8. Achar a aposta do seu plano de lançamento ou da estratégia do trimestre
```
/rubin [cola o plano]
```
Se tudo é prioridade, nada é. Ele acha a aposta central, o que está no plano só porque "todo mundo faz", e a decisão difícil que o plano está evitando.

### 9. Melhorar um prompt, um agente ou outra skill
```
/rubin [cola o prompt]
```
Instrução demais dilui a que importa. Ele mostra o que cortar, o que falta de exemplo e onde as regras estão ali por medo.

### 10. Montar o portfólio
```
/rubin Olha a pasta /portfolio e me diz quais trabalhos ficam.
```
As três peças que mostram quem você é, o fio que liga as melhores e o que dilui o resto.

### 11. Ouvir a letra da música, o poema ou o capítulo do livro
```
/rubin [cola a letra]
```
Onde arrepia, onde desliga, o que está ali por técnica e o que está ali por verdade.

### 12. Decidir entre caminhos
```
/rubin Tô entre abrir uma turma nova do curso, lançar um produto barato ou fechar a agenda de consultoria. [contexto]
```
Ele não devolve "depende". Escolhe um caminho, explica, e te faz a pergunta que você está evitando.

E se você mandar só `/rubin`, sem nada, ele olha a última coisa que foi criada na conversa.

---

## Como ele responde

```
Escuta.          O que isso quer ser, e se já é.
Veredito.        Pronta / Quase / Enterrada / Recomeça / Fico com a N.
O que está vivo. O que proteger, e por quê.
As decisões.     De uma a três, no lugar exato, com o que se ganha.
Experimento.     A direção que ninguém pediu, testável em minutos.
A versão.        Aplicada, na sua voz, sem inventar nada.
A pergunta.      Uma só.
```

Por baixo disso, ele usa:
- **12 testes** (ausência, primeira ideia, verdade ou pose, energia, a coisa que só você faria, régua da grandeza, uma coisa só, ordem, medo, acidente bom, para quem é a obra, pronta);
- **11 movimentos** (subtrair, trocar a ordem, ir ao oposto, exagerar o que está vivo, tirar a rede, ser mais específico, mudar o formato, voltar, recomeçar, não mexer, esperar);
- **critério específico para 13 tipos de obra** (ideia, gancho, roteiro, oferta, nome, visual, produto, apresentação, prompt, plano, texto longo, música e portfólio).

Tudo está em [`rubin/references`](rubin/references).

---

## Como instalar

### Opção 1: Claude Code (terminal, VS Code ou a aba Code do app)

**Windows (PowerShell):**
```powershell
git clone https://github.com/brun0gpt/rubin "$env:TEMP\rubin"; New-Item -ItemType Directory -Force "$env:USERPROFILE\.claude\skills" | Out-Null; Copy-Item -Recurse -Force "$env:TEMP\rubin\rubin" "$env:USERPROFILE\.claude\skills\"
```

**Mac ou Linux:**
```bash
git clone https://github.com/brun0gpt/rubin /tmp/rubin && mkdir -p ~/.claude/skills && cp -r /tmp/rubin/rubin ~/.claude/skills/
```

Sem git? Clique em **Code → Download ZIP** aqui no GitHub, descompacte e copie a pasta `rubin` para dentro de `~/.claude/skills/` (no Windows: `C:\Users\SEU_USUARIO\.claude\skills\`).

Abra uma conversa nova e digite `/rubin`. Ele aparece no menu.

### Opção 2: Claude no navegador ou no app (claude.ai)

1. Baixe o [`rubin.zip`](rubin.zip).
2. No Claude, vá em **Configurações → Capacidades → Skills** e clique em **Enviar skill**.
3. Escolha o `rubin.zip`.

No claude.ai, a skill pode ser chamada pelo nome. Se o `/rubin` não aparecer no menu, escreva *"usa o Rubin nisso"* junto com o que você quer que ele olhe.

### Opção 3: Codex (OpenAI)

**Windows (PowerShell):**
```powershell
git clone https://github.com/brun0gpt/rubin "$env:TEMP\rubin"; New-Item -ItemType Directory -Force "$env:USERPROFILE\.agents\skills" | Out-Null; Copy-Item -Recurse -Force "$env:TEMP\rubin\rubin" "$env:USERPROFILE\.agents\skills\"
```

**Mac ou Linux:**
```bash
git clone https://github.com/brun0gpt/rubin /tmp/rubin && mkdir -p ~/.agents/skills && cp -r /tmp/rubin/rubin ~/.agents/skills/
```

No Codex, chame com `$rubin` (ou digite `/skills` e escolha o Rubin). A pasta já vem com `agents/openai.yaml` configurado para ele só entrar quando você chamar.

### Opção 4: Antigravity (Google)

**Windows (PowerShell):**
```powershell
git clone https://github.com/brun0gpt/rubin "$env:TEMP\rubin"; New-Item -ItemType Directory -Force "$env:USERPROFILE\.gemini\config\skills" | Out-Null; Copy-Item -Recurse -Force "$env:TEMP\rubin\rubin" "$env:USERPROFILE\.gemini\config\skills\"
```

**Mac ou Linux:**
```bash
git clone https://github.com/brun0gpt/rubin /tmp/rubin && mkdir -p ~/.gemini/config/skills && cp -r /tmp/rubin/rubin ~/.gemini/config/skills/
```

No Antigravity, digite `/rubin` na caixa de mensagem. Se estiver usando o terminal (CLI) aberto, rode `/skills reload` depois de instalar. Lá não existe opção para a skill só entrar quando chamada, então o agente pode usar o Rubin sozinho quando achar que o pedido combina com ele.

### Atualizar

Rode o mesmo comando de instalação de novo. Ele substitui a pasta antiga.

---

## O que ele não é

- Ele não é o Rick Rubin e não fala por ele. Não imita o jeito dele falar e não atribui frases a ele.
- Gosto é uma leitura, não uma lei. Ele decide com convicção, e quem assina a obra continua sendo você.
- Ele não inventa fatos, números nem histórias na versão que devolve.

Esta skill é inspirada na abordagem criativa de Rick Rubin. Não é afiliada a ele nem aprovada por ele.

---

Feito por [@brun0gpt](https://instagram.com/brun0gpt). Licença MIT.
