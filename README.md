# Bets Application

1 - Github actions - branch main workflow
git checkout -b bugfix/testeworkflow
git add .
git commit -m 'teste workflow'
git push origin bugfix/testeworkflow
aprove pull request branch main 
https://github.com/rrddevops/bets-api/actions/runs/14419663208/job/40440643947

2- Stoplight Spectral Open Source validation contracts json
Exemplo: /home/rodrigo/projetos/bets-api/assets/rules/openapi3.spectral.yaml
  info-contact: error
  operation-tags: error

/home/rodrigo/projetos/bets-api/.github/workflows/api-cycle.yaml
 Run Spectral
      - uses: stoplightio/spectral-action@latest

- name: Install Global Dependencies
        if: steps.cache.outputs.cache-hit != 'true'
        run: npm -g install @stoplight/prism-cli newman

Usamos o http mocking prism que subirá as rotas para o teste do exemplo do contrato
 prism mock assets/api-docs/bets-api.yaml 
 
3 - Postman

Bets - Bets API

❏ Contract Tests / bets
↳ Create Bet
  POST http://127.0.0.1:4010/bets [1:50:56 PM] › [HTTP SERVER] post /bets ℹ  info      Request received
[1:50:56 PM] ›     [NEGOTIATOR] ℹ  info      Request contains an accept header: application/json
[1:50:56 PM] ›     [VALIDATOR] ✔  success   The request passed the validation rules. Looking for the best response
[1:50:56 PM] ›     [NEGOTIATOR] ✔  success   Found a compatible content for application/json
[1:50:56 PM] ›     [NEGOTIATOR] ✔  success   Responding with the requested status code 201
[1:50:56 PM] ›     [NEGOTIATOR] ℹ  info      > Responding with "201"
[201 Created, 418B, 65ms]
  ✓  [POST]::/bets - Status code is 2xx
  ✓  [POST]::/bets - Content-Type is application/json
  ✓  [POST]::/bets - Response has JSON Body
  ✓  [POST]::/bets - Schema is valid

┌─────────────────────────┬──────────────────┬──────────────────┐
│                         │         executed │           failed │
├─────────────────────────┼──────────────────┼──────────────────┤
│              iterations │                1 │                0 │
├─────────────────────────┼──────────────────┼──────────────────┤
│                requests │                1 │                0 │
├─────────────────────────┼──────────────────┼──────────────────┤
│            test-scripts │                1 │                0 │
├─────────────────────────┼──────────────────┼──────────────────┤
│      prerequest-scripts │                0 │                0 │
├─────────────────────────┼──────────────────┼──────────────────┤
│              assertions │                4 │                0 │
├─────────────────────────┴──────────────────┴──────────────────┤
│ total run duration: 140ms                                     │
├───────────────────────────────────────────────────────────────┤
│ total data received: 118B (approx)                            │
├───────────────────────────────────────────────────────────────┤
│ average response time: 65ms [min: 65ms, max: 65ms, s.d.: 0µs] │
└───────────────────────────────────────────────────────────────┘

4 - ArgoCD

Contains code for Bets Application (demo purpose)

## Big Picture
![Big Picture](img/bets.png)

## Language
**Golang**