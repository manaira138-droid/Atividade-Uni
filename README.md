# Prime Conecta — demo Android

Protótipo acadêmico do Manaíra Prime Hotel. Dados e colaboradores fictícios; o aplicativo não usa backend e as tarefas reiniciam ao fechar/reiniciar o aplicativo (estado em memória).

## Rodar no Android com Expo Go (sem APK)

1. Instale **Node.js** no computador.
2. Abra a pasta deste projeto no VS Code e execute `npm install`.
3. Execute `npx expo start`.
4. Instale **Expo Go** no Android e escaneie o QR code (computador e celular na mesma rede).

## Gerar APK instalável

1. Crie uma conta em https://expo.dev/ e instale a CLI: `npm install -g eas-cli`.
2. Faça login com `eas login`.
3. Dentro da pasta, execute `eas build -p android --profile preview`.
4. Se for solicitado, vincule ou crie o projeto Expo e permita gerar a chave Android.
5. Quando a compilação terminar, baixe o APK pelo link do Expo, transfira para o celular e instale-o (autorize a instalação desse arquivo, se necessário).

`eas.json` já está configurado para produzir APK, não AAB.

## Roteiro de apresentação

- Selecione **Recepção** → **+ Nova** → "Reparar fechadura" → local "Quarto 205" → destino **Manutenção** → prioridade **Urgente** → Cadastre.
- Troque o setor para **Manutenção**. Abra a solicitação, toque em **Iniciar tarefa** e depois **Marcar concluída**.
- Troque para **Recepção** para ver o status atualizado.
- Mostre o **Painel** e a contagem por departamento.

### Limitações desta demonstração

- Os perfis são simulados e não há autenticação real.
- Não há sincronização entre celulares. É um protótipo para demonstrar no mesmo aparelho.
- As alterações só existem durante a sessão, sem persistência no dispositivo.
- Não use dados pessoais reais de hóspedes nesta versão.
