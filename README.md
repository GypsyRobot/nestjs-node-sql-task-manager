## Backend de um gerenciador de tarefas usando NestJS e PostgreSQL

Passos:
yarn global add cross-env (windows somente)

yarn start:dev

subindo para o heroku:
cria o app no site do heroku
yarn global add heroku
heroku -v
heroku login
heroku addons:create heroku-postgresql:hobby-dev -a NOME-DO-SEU-APP-NO-HEROKU
heroku git:remote -a NOME-DO-SEU-APP-NO-HEROKU
heroku config:set NPM_CONFIG_PRODUCTION=false
heroku config:set NODE_ENV=production
heroku config:set STAGE=prod

heroku config:set DB_HOST=O QUE VOCE PEGOU NO SEU SERVER POSTGRESQL NO HEROKU
repete a linha de cima pra cada variavel de ambiente, igual no .env.stage.dev
gerar senha do JWT_SECRET no passwordgenerator.net base64 com somente numero e letra pra passar de boa pelo cli/terminal

git add .
git commit -m "going live MF!"
git push -f heroku HEAD:master
heroku logs --tail
