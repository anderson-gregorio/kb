# (SQL Server) Dica - Como utilizar Loops com While?

```sql
DECLARE @Iteration INT

SET @Iteration = 1

WHILE @Iteration <= 10
BEGIN
    PRINT @Iteration
    SET @Iteration = @Iteration + 1
END

```

Link de Referência;

[http://www.blackwasp.co.uk/SQLWhile.aspx](http://www.blackwasp.co.uk/SQLWhile.aspx)