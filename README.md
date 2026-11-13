# Prime Conecta V3 — Administração e contas individuais

Aplicativo demonstrativo Android (Expo SDK 54). A base de colaboradores começa **vazia**, exceto pelo acesso administrativo inicial solicitado.

## Acesso inicial

- Usuário: `Admin`
- Senha: `admin123`

**Atenção:** essa é uma credencial de demonstração, conhecida e fraca. Altere a senha em **Perfil** assim que entrar. Não use dados reais ou confidenciais nesta versão. O armazenamento é local e o hash SHA-256 simples não é adequado como solução completa de autenticação em produção. Para uso real entre celulares, substituir por autenticação segura em servidor (ex.: Supabase Auth) e regras de acesso no banco.

## Recursos

- Login individual com sessão local, sem personagens pré-cadastrados.
- Gerência/Admin: cadastramento, edição, desativação e liberação de login dos colaboradores; definição de usuário, senha, departamento e perfil.
- Encarregado: cadastro e edição de colaboradores do próprio setor, sem definir credenciais; gerência libera os logins.
- Colaborador: visualiza demandas do setor e as suas, sem acesso administrativo.
- Cadastro de demandas, início, envio à validação, conclusão, reabertura, histórico e tempo em execução.
- Tela **Operação** e retorno ao Início pelo menu inferior.
- Passagem de turno, painel gerencial, departamentos e mudança de senha.
- Desativação preserva histórico e tarefas, sem apagar os registros.

## Instalar em projeto Expo existente

**Faça backup**. Extraia o ZIP. Copie o conteúdo da pasta `Prime_Conecta_V3` para sua pasta `Prime_Conecta_Android_Demo`, **preservando seu `app.json`, `eas.json` e `.git` existentes**. Os arquivos `App.tsx`, `package.json`, `tsconfig.json`, `assets/` e `.gitignore` podem ser substituídos. Não substitua `app.json` ou `eas.json` se já estão vinculados ao seu projeto EAS.

```powershell
npm.cmd install
npx.cmd expo install --fix
npx.cmd expo start --clear
```

Para APK, depois de testar no Expo Go:

```powershell
npx.cmd eas-cli build -p android --profile preview
```

Se aparecer falha do Git na sua instalação, em **uma mesma janela** de PowerShell:

```powershell
$env:EAS_NO_VCS="1"
npx.cmd eas-cli build -p android --profile preview
```

## Importante

Esta versão **não sincroniza dados entre dispositivos**. Cada Android terá seu próprio armazenamento e seus próprios colaboradores, tarefas e senhas. Para operação multiusuário real, é necessária uma API, autenticação gerenciada no servidor, regras por função, sincronização, auditoria e backups.

A versão V2 usava uma chave local diferente; os dados de demonstração da V2 não são importados automaticamente. Esta V3 inicia sem colaboradores e sem tarefas cadastradas, conforme solicitado.
