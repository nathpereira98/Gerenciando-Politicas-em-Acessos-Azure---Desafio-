# Gerenciando-Politicas-em-Acessos-Azure---Desafio-
Desafio DIO - Gerenciando Politicas em Acessos Azure

## Entendimento: 
- **RBAC (Role-Based Access Control)**: diferença entre papéis integrados e roles customizadas; atribuição de papéis em diferentes escopos (subscription, resource group, resource).  
- **Microsoft Entra ID**: gerenciamento de identidades, aplicações, service principals e princípios de autenticação.  
- **Autenticação Multifator (MFA)** e **Acesso Condicional**: políticas que condicionam o acesso (local, risco do sign-in, dispositivo).  
- **PIM (Privileged Identity Management)**: concessão de privilégios just-in-time e monitoramento de elevações.  
- **Managed Identities**: identidades gerenciadas para recursos que acessam outros serviços sem expor credenciais.  
- **Azure Policy**: aplicar regras (ex.: exigir tags, restringir SKUs ou regiões) para reforçar governança de acesso e implantação.  
- **Principle of Least Privilege**: conceder apenas o mínimo necessário e revisar permissões periodicamente.  
- **Auditoria e logs**: habilitar Activity Logs, Audit Logs e enviar diagnósticos para Log Analytics para rastrear alterações e acessos.

## Boas práticas resumidas:
- Usar **RBAC** em vez de compartilhar credenciais.  
- Preferir **roles integrados** quando possível; criar custom roles somente se necessário.  
- Aplicar **MFA** para contas privilegiadas e políticas de Acesso Condicional para cenários de risco.  
- Usar **PIM** para elevar privilégios temporariamente (just-in-time).  
- Aproveitar **Managed Identities** para aplicações e automações.  
- Implementar **Azure Policy** para padronizar e bloquear implantações não conformes.  
- Revisar assignments regularmente e usar **Access Reviews** para cleanup.  
- Habilitar logs e alertas para detectar mudanças críticas em roles/policies.

## Exemplos práticos estudados (comandos de referência)
Criar uma role customizada (arquivo `customRole.json`) e registrá-la:
```bash
az role definition create --role-definition ./customRole.json
