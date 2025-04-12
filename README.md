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

# Run Spectral
      - uses: stoplightio/spectral-action@latest

- name: Install Global Dependencies
        if: steps.cache.outputs.cache-hit != 'true'
        run: npm -g install @stoplight/prism-cli newman

Usamos o http mocking prism que subirá as rotas para o teste do exemplo do contrato
 prism mock assets/api-docs/bets-api.yaml 
 
3 - Postman

4 - ArgoCD

Contains code for Bets Application (demo purpose)

## Big Picture
![Big Picture](img/bets.png)

## Language
**Golang**