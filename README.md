# **IMC-Check - Sistema de Acompanhamento de Índice de Massa Corporal**

 📋 **Sobre o Projeto**

O **IMC-Check** é uma aplicação web desenvolvida para auxiliar usuários no acompanhamento do seu Índice de Massa Corporal (IMC), permitindo o registro de peso, altura, atividades físicas e metas pessoais de saúde. A aplicação calcula automaticamente o IMC e fornece classificação conforme os padrões da Organização Mundial da Saúde (OMS).

 🎯 **Objetivos**
- Fornecer uma ferramenta acessível para monitoramento da saúde corporal
- Calcular e classificar o IMC automaticamente
- Permitir estabelecimento e acompanhamento de metas de peso
- Registrar atividades físicas realizadas
- Oferecer relatórios visuais do progresso do usuário

 ✨ **Funcionalidades Principais**

 🔐 **Autenticação e Perfil**
- Cadastro de novos usuários com dados completos
- Sistema de login com sessões seguras
- Perfil personalizado com informações de saúde

 📊 **Cálculo e Acompanhamento do IMC**
- Registro periódico de peso
- Cálculo automático do IMC
- Classificação conforme padrões da OMS
- Histórico completo de evolução

 🎯 **Gestão de Metas**
- Definição de metas de peso com data objetivo
- Acompanhamento visual do progresso
- Sistema de apenas uma meta ativa por usuário
- Comparação entre resultados e metas

 🏃 **Atividades Físicas**
- Registro de tipo, data e duração de atividades
- Histórico organizado de exercícios
- Relatórios de frequência e consistência

 📈 **Relatórios e Dashboard**
- Visualização em tabela de todos os registros
- Indicadores visuais de progresso
- Interface responsiva e intuitiva

 🛠️ **Tecnologias Utilizadas**

 **Backend**
- **Python 3.8+** - Linguagem principal
- **Flask** - Microframework web
- **SQLAlchemy** - ORM para banco de dados
- **MySQL** - Banco de dados relacional
- **Jinja2** - Motor de templates

 **Frontend**
- **HTML5** - Estrutura das páginas
- **CSS3** - Estilização com variáveis CSS
- **JavaScript** - Interatividade básica
- **Bootstrap** - Componentes responsivos (opcional)

 **Ferramentas de Desenvolvimento**
- **Git** - Controle de versão
- **Pip** - Gerenciador de pacotes Python
- **Virtualenv** - Ambientes virtuais isolados

 📁 **Estrutura do Projeto**

```
imc-check/
│
├── app.py                      # Aplicação principal Flask
├── requirements.txt            # Dependências do projeto
├── README.md                   # Este arquivo
│
├── static/                     # Arquivos estáticos
│   ├── assets/
│   │   ├── css/
│   │   │   └── styles.css      # Estilos personalizados
│   │   └── images/
│   │       └── logo.svg        # Logo do sistema
│   └── (outros arquivos estáticos)
│
└── templates/                  # Templates HTML
    ├── base.html              # Template base com navbar
    ├── index.html             # Página inicial/dashboard
    ├── login.html             # Página de login
    ├── register.html          # Página de cadastro
    ├── metas.html             # Gestão de metas
    ├── registros.html         # Registro de pesos
    ├── atividades.html        # Registro de atividades
    ├── acompanhamento.html    # Acompanhamento de progresso
    └── relatorio_atividades.html # Relatório de atividades
```

 ⚙️ **Pré-requisitos**

 **Sistema Operacional**
- Windows 10/11, macOS 10.14+, ou Linux (Ubuntu 18.04+)

 **Software Necessário**
1. **Python 3.8 ou superior**
   - [Download Python](https://www.python.org/downloads/)
   - Verifique a instalação: `python --version`

2. **MySQL Server 8.0+**
   - [Download MySQL](https://dev.mysql.com/downloads/)
   - Alternativa: XAMPP (para Windows) ou MAMP (para macOS)

3. **Git** (opcional para versionamento)
   - [Download Git](https://git-scm.com/downloads)

 🚀 **Instalação e Configuração**

 **Passo 1: Clonar o Repositório**
```bash
# Clone o repositório
git clone https://github.com/seu-usuario/imc-check.git

# Navegue até a pasta do projeto
cd imc-check
```

 **Passo 2: Configurar Ambiente Virtual**
```bash
# Criar ambiente virtual
python -m venv venv

# Ativar ambiente virtual

# No Windows:
venv\Scripts\activate

# No macOS/Linux:
source venv/bin/activate

# Verificar se está ativado (deve mostrar 'venv' no início da linha)
(venv) $
```

 **Passo 3: Instalar Dependências**
```bash
# Instalar pacotes necessários
pip install -r requirements.txt

# Se não tiver requirements.txt, instale manualmente:
pip install flask flask-sqlalchemy pymysql python-dotenv
```

 **Passo 4: Configurar Banco de Dados**

 **Opção A: Usando MySQL Workbench ou phpMyAdmin**
1. Abra seu cliente MySQL
2. Crie um novo banco de dados:
   ```sql
   CREATE DATABASE imccheck CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
   ```
3. Crie um usuário (opcional):
   ```sql
   CREATE USER 'imc_user'@'localhost' IDENTIFIED BY 'senha_segura';
   GRANT ALL PRIVILEGES ON imccheck.* TO 'imc_user'@'localhost';
   FLUSH PRIVILEGES;
   ```

 **Opção B: Via Linha de Comando**
```bash
# Conecte ao MySQL
mysql -u root -p

# Execute os comandos SQL acima
```

 **Passo 5: Configurar Variáveis de Ambiente**

Crie um arquivo `.env` na raiz do projeto:

```env
# Configurações do Flask
FLASK_APP=app.py
FLASK_ENV=development
SECRET_KEY=sua_chave_secreta_aqui

# Configurações do Banco de Dados
DATABASE_URL=mysql+pymysql://usuario:senha@localhost:3306/imccheck

# Configurações do Servidor
HOST=127.0.0.1
PORT=5600
```

**Nota:** Substitua `usuario` e `senha` pelas suas credenciais do MySQL.

 **Passo 6: Inicializar o Banco de Dados**

O banco de dados será criado automaticamente na primeira execução. Para forçar a criação das tabelas:

```python
# Em um terminal Python interativo
from app import app, db
with app.app_context():
    db.create_all()
    print("Banco de dados criado com sucesso!")
```

 **Passo 7: Executar a Aplicação**
```bash
# Com ambiente virtual ativado
python app.py

# Ou usando flask run
flask run --host=127.0.0.1 --port=5600
```

 **Passo 8: Acessar a Aplicação**
1. Abra seu navegador
2. Acesse: `http://127.0.0.1:5600`
3. Faça login ou crie uma nova conta

 📖 **Guia de Uso Rápido**

 **Primeiro Acesso**
1. **Criar conta**: Clique em "Criar conta" na página de login
2. **Preencha os dados**: Informe nome, email, login, senha e dados de saúde
3. **Login**: Use suas credenciais para acessar o sistema

 **Definir Meta**
1. Acesse "Metas" no menu
2. Clique em "Lançar meta"
3. Informe a data objetivo e peso desejado
4. Clique em "Salvar meta"

 **Registrar Peso**
1. Acesse "Registros" no menu
2. Informe data e peso atual
3. O sistema calculará automaticamente seu IMC
4. Clique em "Salvar registro"

 **Registrar Atividades**
1. Acesse "Atividades físicas" no menu
2. Informe tipo, data e duração da atividade
3. Clique em "Salvar atividade"

 **Acompanhar Progresso**
1. Acesse "Acompanhamento" no menu
2. Veja todos seus registros em tabela
3. Verifique se está dentro da meta (coluna "Dentro da meta?")
4. Acesse "Relatório" para ver atividades físicas

 🔧 **Configuração para Produção**

 **1. Modificar app.py**
```python
# Alterar configurações de segurança
app.config['SECRET_KEY'] = os.urandom(24)  # Chave aleatória

# Desativar debug mode
if __name__ == '__main__':
    app.run(debug=False)  # Mudar para False em produção
```

 **2. Configurar Servidor Web (ex: Gunicorn)**
```bash
# Instalar Gunicorn
pip install gunicorn

# Executar com Gunicorn
gunicorn -w 4 -b 127.0.0.1:5600 app:app
```

 **3. Configurar Nginx (opcional)**
```nginx
server {
    listen 80;
    server_name seu-dominio.com;
    
    location / {
        proxy_pass http://127.0.0.1:5600;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
    }
}
```

 🐛 **Solução de Problemas Comuns**

 **Erro: "ModuleNotFoundError: No module named 'flask'"**
```bash
# Verifique se o ambiente virtual está ativado
# Reinstale as dependências
pip install -r requirements.txt
```

 **Erro: "Can't connect to MySQL server"**
1. Verifique se o MySQL está rodando
2. Confira usuário e senha no `.env`
3. Teste a conexão:
   ```bash
   mysql -u usuario -p -h localhost imccheck
   ```

 **Erro: "Table doesn't exist"**
```python
# Execute no terminal Python
from app import app, db
with app.app_context():
    db.create_all()
```

 **Aplicação não inicia**
```bash
# Verifique a porta
# A porta 5600 pode estar em uso
# Altere no .env ou app.py

# Limpe cache do navegador
# Tente navegador diferente
```

 📝 **Regras de Negócio Implementadas**

 **Cálculo do IMC**
```
Fórmula: IMC = peso (kg) / [altura (m)]²

Classificação OMS:
- Abaixo de 18.5: Abaixo do peso
- 18.5 a 24.9: Peso normal
- 25.0 a 29.9: Sobrepeso
- 30.0 a 34.9: Obesidade Grau I
- 35.0 a 39.9: Obesidade Grau II
- Acima de 40.0: Obesidade Grau III
```

 **Limitações do Sistema**
- Apenas uma meta ativa por usuário
- Senhas sem criptografia (não use senhas reais em desenvolvimento)
- Sem recuperação de senha
- Interface básica, sem gráficos avançados

 🤝 **Contribuindo**

1. Faça um Fork do projeto
2. Crie uma Branch para sua Feature (`git checkout -b feature/AmazingFeature`)
3. Commit suas mudanças (`git commit -m 'Add some AmazingFeature'`)
4. Push para a Branch (`git push origin feature/AmazingFeature`)
5. Abra um Pull Request

 **Padrões de Código**
- Siga PEP 8 para Python
- Comente funções complexas
- Use nomes descritivos para variáveis e funções
- Teste suas alterações antes de enviar

 📄 **Licença**

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

 👥 **Autores**

- **Natanael Grigorio Ferreira** - Desenvolvedor Backend
- **Geovana Sangalli** - Desenvolvedora Frontend

 🙏 **Agradecimentos**

- Docentes do curso de Análise e Desenvolvimento de Sistemas
- Todos que testaram e forneceram feedback
- Prof Fabino Taguchi

---



**⚠️ AVISO:** Este é um projeto educacional. Não use para monitoramento médico real sem consultar um profissional de saúde.

**Última atualização:** Março 2025

---

<div align="center">
  <sub>Desenvolvido com ❤️ para promover saúde e bem-estar através da tecnologia</sub>
</div>
