# Casa Financeira V2

Sistema web simples para controle financeiro doméstico, preparado para uso no celular e para publicação no GitHub Pages.

## O que esta versão já faz
- lançamentos manuais de receitas e despesas
- separação por Pix, débito, crédito e dinheiro
- separação por você, esposa ou casa
- controle de compras parceladas
- metas de gasto e economia do mês
- exportação em CSV
- backup e restauração em JSON
- importação de extratos em CSV, OFX e JSON
- instalação como app no celular (PWA)
- sincronização entre dois celulares quando configurado com Firebase

## Limitações importantes
- PDF: esta versão aceita PDF para anexar e revisar manualmente, mas não faz leitura automática confiável de qualquer banco.
- WhatsApp: esta versão foi preparada para usar extratos do banco/cartão no lugar das fotos do WhatsApp.
- Anexos: nesta base inicial, o nome do arquivo do comprovante fica salvo no lançamento. Depois dá para evoluir para Firebase Storage.

## Como publicar no GitHub Pages
1. Crie um repositório novo no GitHub.
2. Envie todos os arquivos desta pasta.
3. Vá em Settings > Pages.
4. Escolha Deploy from a branch > main / root.
5. Salve e aguarde o link.

## Como ativar a sincronização com Firebase
1. Crie um projeto no Firebase.
2. Adicione um app Web.
3. Ative o Firestore.
4. Copie `firebase-config.example.js` para `firebase-config.js` e preencha com suas chaves.
5. Envie o novo arquivo para o repositório.

## Regra inicial simples do Firestore para teste
```txt
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /financeiro/{document=**} {
      allow read, write: if true;
    }
  }
}
```

## Próximas melhorias possíveis
- leitura avançada de PDFs específicos do seu banco
- guardar comprovantes reais em nuvem
- tela de faturas por cartão
- categorias personalizadas
- gráfico mensal
- fechamento e vencimento de cartão
