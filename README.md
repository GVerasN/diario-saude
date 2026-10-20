# Diário de Saúde

Painel pessoal para registrar peso, medidas, sono, passos e treinos, e acompanhar o plano alimentar.
O site fica no **GitHub Pages** e os dados ficam no **Firebase** (Firestore), protegidos por login Google.

## Arquivos

| Arquivo | O que é |
|---|---|
| `index.html` | O site inteiro: visual, gráficos e lógica. |
| `firebase-config.js` | Endereço do projeto no Firebase. É público por design; não é senha. |
| `firestore.rules` | Regras de segurança: só o dono da conta lê e grava os próprios dados. Cópia de referência do que está no console do Firebase. |
| `manifest.webmanifest` + `icon.svg` | Permitem "Adicionar à tela inicial" no celular, como um app. |
| `.gitignore` | Lista de arquivos que o Git ignora (backups com dados pessoais). |

## Onde ficam os dados

No Firestore, em `users/{seu-id}`: o documento guarda o perfil; as subcoleções `logs` (um documento por data) e `ajustes` guardam o resto.
Nada pessoal fica no código. Use **Ajustes e perfil → Exportar backup** de vez em quando.

## Git em 3 comandos

Rodados dentro desta pasta, no terminal:

```powershell
git add .                         # separa as mudanças que vão entrar na próxima versão
git commit -m "o que mudou"       # salva uma versão com uma descrição
git push                          # envia ao GitHub; o site atualiza em ~1 minuto
```

Outros úteis: `git status` (o que mudou desde a última versão) e `git log --oneline` (histórico de versões).
