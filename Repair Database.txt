#  -----   Checar e reparar erros em banco de dados SQL  -----   #  
#
# Checar os erros da base e retornar todos os erros
#
	DBCC CHECKDB ('vetorh') WITH ALL_ERRORMSGS;
#
# Alterar para single user o banco
#
	ALTER DATABASE vetorh SET SINGLE_USER WITH ROLLBACK IMMEDIATE;
#
# Executa a reparação do banco com os dados
#
	DBCC CheckDB ('vetorh', REPAIR_ALLOW_DATA_LOSS) WITH ALL_ERRORMSGS;
#
# Alterar para multi user o banco
#
	ALTER DATABASE vetorh SET MULTI_USER; 
#
# Checar os erros da base e validar
#
	DBCC CHECKDB ('vetorh') WITH ALL_ERRORMSGS;  
#
