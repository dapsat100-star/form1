# Relatório Técnico – Streamlit (Auto-Upload)

## Rodando localmente
```bash
pip install -r requirements.txt
streamlit run app.py
```

## Upload Automático
Marque as opções na barra lateral:
- **Google Drive (usar st.secrets)**
- **GitHub (usar st.secrets)**

Quando você clicar em **Atualizar prévia**, o app:
1. Salva o rascunho local (se autosave estiver ativo)
2. Gera MD, PDF e DOCX
3. Envia automaticamente os 4 arquivos (.json, .md, .pdf, .docx) para Drive/GitHub

## Configurar `st.secrets`
Crie `.streamlit/secrets.toml` com:

```toml
[gcp_service_account]
type = "service_account"
project_id = "SEU_PROJECT_ID"
private_key_id = "SUA_PRIVATE_KEY_ID"
private_key = """-----BEGIN PRIVATE KEY-----
COLE_AQUI_EXATAMENTE COM QUEBRAS DE LINHA
-----END PRIVATE KEY-----
"""
client_email = "NOME@SEU-PROJETO.iam.gserviceaccount.com"
client_id = "SEU_CLIENT_ID"
token_uri = "https://oauth2.googleapis.com/token"

[drive]
folder_id = "ID_DA_PASTA_NO_DRIVE"

[github]
token = "ghp_SEU_TOKEN"
repo = "usuario/repositorio"
branch = "main"
base_path = "reports"
```
