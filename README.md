# ponto_automate

Script de automação para registro de ponto no Tangerino (Solides) via Selenium.

## Funcionamento

O script cobre dois momentos do dia:

**Saída para almoço** — registra a saída, aguarda 72 minutos e registra o retorno automaticamente.

**Saída ao fim do expediente** — registra apenas uma vez e encerra. O critério é o horário: se `datetime.now().hour >= 17`, o segundo registro é ignorado.

## Requisitos

- Python 3.8+
- Google Chrome em `/opt/google/chrome/google-chrome`
- ChromeDriver compatível com a versão do Chrome instalada

```bash
pip install selenium
```

## Configuração

Edite as credenciais no topo do script:

```python
COD_EMPREGADOR = 'ABCDEF'
PIN            = '123456'
EMAIL          = 'seuemail@seuprovedor.com'
```

Não versione essas variáveis. O código já tem `getpass()` comentado como alternativa, ou use variáveis de ambiente.

## Uso

```bash
jupyter notebook ponto_automate.ipynb
```

Execute antes de sair para o almoço ou ao encerrar o expediente.
