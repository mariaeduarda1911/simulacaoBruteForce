# Trabalho Prático — Simulação de Ataque Brute Force

**Objetivo**

Demonstrar entendimento do ataque *brute force* em ambiente de desenvolvimento controlado e documentar medidas de defesa. Este repositório contém apenas material didático e documentação — **não** há código malicioso executável.

## Aviso importante
* TODOS os experimentos foram realizados **localmente** em ambiente isolado (máquinas virtuais).
* Este material tem finalidade **educacional** e de pesquisa. A autora não apoia uso malicioso.

## Ambiente de testes
* Plataformas: máquinas virtuais (VMs).
* Sistema de ataque: Kali Linux (VM).
* Sistema alvo: Metasploitable (VM) configurada apenas para fins de teste.
* Rede: ambiente isolado (rede interna da VM), sem acesso à rede de produção ou à internet pública.

## Ferramentas utilizadas
* **Medusa** — ferramenta de força bruta para serviços de rede.
* Ferramentas auxiliares presentes no Kali Linux (para monitoramento e análise).

## Como testei 
> Importante: este resumo é **descritivo** — não contém comandos ambiente-dependentes nem instruções para executar ataques em sistemas alheios.
1. Preparei duas VMs em rede isolada: uma rodando Kali Linux (atacante) e outra rodando Metasploitable (alvo).
2. Certifiquei-me de que a rede era restrita às VMs e que não havia rota para a internet ou outras máquinas da rede local.
3. Realizei varredura e identificação dos serviços expostos no alvo (apenas para fins de aprendizado e com as permissões apropriadas).
4. Executei simulações de brute force controladas contra contas de teste do sistema alvo usando Medusa, monitorando uso de recursos e logs.


## Medidas de defesa e mitigação

As medidas abaixo são boas práticas gerais para mitigar ataques de força bruta:

1. **Política de bloqueio por tentativas** — bloquear ou retardar contas/IPs após N tentativas falhas.
2. **Autenticação multifator (MFA)** — exigir um segundo fator além da senha.
3. **Senhas fortes e políticas de senha** — obrigar senhas com comprimento e complexidade mínimos.
4. **Rate limiting** — limitar taxa de tentativas por IP/usuário em endpoints de autenticação.
5. **Captchas** — usar quando apropriado para limitar automação simples.
6. **Monitoramento e alertas** — detectar padrões de tentativas de autenticação e gerar alertas.
7. **Whitelist/Blacklist** — quando aplicável, restringir acessos por rede.
8. **Hashing e hardening de armazenamento de credenciais** — usar algoritmos seguros para armazenar senhas (bcrypt/argon2) e aplicar salting.
9. **Proteções em camada de aplicação e infra** — WAF, firewalls, sistemas de detecção de intrusão.
10. **Educação e conscientização** — treinar usuários sobre criação de senhas e phishing.

## Estrutura do repositório
* `README.md` — este documento principal.
* `medusa_kali/` — pasta contendo todo o material relacionado aos testes realizados com Medusa.
  * `imagens/` — screenshots e evidências.
  * `scripts.txt` — anotações e alguns exemplos não-executáveis (sem comandos que automatizem ataques).
