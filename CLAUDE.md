# Diário de Saúde

Painel pessoal de plano alimentar e treino (peso, medidas, sono, passos, treinos).
Site estático no GitHub Pages: https://gverasn.github.io/diario-saude/
Repositório **público**: GVerasN/diario-saude, branch `main`. O Pages publica a partir da raiz da `main`.

## Estrutura
- `index.html`: o site inteiro (visual, gráficos e lógica). Sem build, sem npm.
- `firebase-config.js`: configuração pública do Firebase (não é segredo).
- `firestore.rules`: cópia de referência das regras do console. Se mudar aqui, avise que também precisa publicar no console do Firebase.
- `manifest.webmanifest` + `icon.svg`: instalação como app no celular.

## Dados (Firebase, projeto `diario-saude-79910`)
- Login Google + Firestore (`southamerica-east1`). O domínio gverasn.github.io já está autorizado no Auth.
- `users/{uid}` guarda o perfil; as subcoleções `logs` (um doc por data) e `ajustes`.
- As regras só deixam cada usuário ler e gravar os próprios dados. Não afrouxe as regras.
- Registrar dados no site **não** passa pelo git. O git é só para mudanças no código.
- Ao mudar o formato dos dados, mantenha compatibilidade com os documentos que já existem (não há migração automática).

## Fluxo de trabalho (o projeto é editado em dois PCs)
1. `git pull` antes de editar.
2. Edite e confira localmente, abrindo o `index.html` ou com um servidor simples.
3. `git add .`, `git commit -m "<verbo no presente: o que mudou>"`, `git push`. O site atualiza em ~1 minuto.
- Autor dos commits: GVerasN <92883732+GVerasN@users.noreply.github.com>.
- **Nunca** commite backups com dados pessoais: o `.gitignore` bloqueia `*backup*.json` e `migracao*.json`, e o repo é público.

## Como trabalhar comigo (o usuário)
- Responda em português do Brasil.
- Sou iniciante em git: explique os passos de forma simples.
- Mostre o que vai mudar antes de enviar ao GitHub.
