# tlf-universo2019
Exemplos utilizados no workshop do dia 26/06 no Universo TOTVS 2019 sobre TL++ e TLF

----------------
Roteiro de teste
----------------

**1 - Criar base de dados**

	a - Verificar na pasta ROOT que não tenha nenhuma base SQLite existente, se houver, delete.
	b - Subir appserver
	c - Executar a rotina -> UT_generateTables
	
**2 - Cria usuário (POST)**

	a - http://127.0.0.1:9080/rest/universo2019/path/user/ana/user@123/Ana%20Batista/Aninha
	ou
	b - http://127.0.0.1:9080/rest/universo2019/query/user?user=ana&password=user@123&name=Ana%20Batista&nick=Aninha

**3 - Consulta (GET)**

	a - http://127.0.0.1:9080/rest/universo2019/path/user/ana
	ou
	b - http://127.0.0.1:9080/rest/universo2019/query/user?user=ana

**4 - Altera usuário (PUT)**

	a - http://127.0.0.1:9080/rest/universo2019/path/user/ana/Ana%20Camargo/batatinha
	ou
	b - http://127.0.0.1:9080/rest/universo2019/query/user
		com
		{"user":"ana","nick":"batatinha","name":"Ana Camargo"}
	
**5 - Exclui usuário (DELETE)**

	a - http://127.0.0.1:9080/rest/universo2019/path/user/ana
	ou
	b - http://127.0.0.1:9080/rest/universo2019/query/user
		com
		{"user": "ana"}
	
**6 - Exercíco em sala da aula**

	Implementar serviço REST que faça a autenticação de qualquer usuário e senha da base.
	- Usar o endpoint (/universo2019/user/login)
	- Usar método GET
	- Utilizar o modo de passagem de parâmetro a seus gosto ( queryparam | pathparam | json/body )
	- Utilize a função abaixo para autenticar:
		universo2019UserLogin( cUser, cPass )
	- Retornar código 200 para ok ou 500 para usuário e/ou senha inválidos
	- Retornar Mensagem para client. Sugestão em formato JSON.

-------------------------
LOGIN ( exercício final )
-------------------------

	http://127.0.0.1:9080/rest/universo2019/user/login
	{"user":"jose","password":"senha@123"}
