---
description: 'Dowiedz się więcej na temat: korzystanie z zestawów do zweryfikowania za pomocą SQL Server (C++/CLI)'
title: Używanie zestawów weryfikowalnych z programem SQL Server (C++/CLI)
ms.date: 10/17/2018
helpviewer_keywords:
- verifiable assemblies [C++], with SQL Server
ms.assetid: 5248a60d-aa88-4ff3-b30a-b791c3ea2de9
ms.openlocfilehash: b155fb0360fb373f5931f51de3af557d06858a71
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97204202"
---
# <a name="using-verifiable-assemblies-with-sql-server-ccli"></a>Używanie zestawów weryfikowalnych z programem SQL Server (C++/CLI)

Rozszerzone procedury składowane, spakowane jako biblioteki dołączane dynamicznie (dll), zapewniają sposób rozszerzania funkcji SQL Server za pomocą funkcji opracowanych z Visual C++. Rozszerzone procedury składowane są implementowane jako funkcje w bibliotekach DLL. Oprócz funkcji rozszerzone procedury składowane mogą także definiować [typy zdefiniowane przez użytkownika](../cpp/classes-and-structs-cpp.md) i funkcje agregujące (takie jak sum lub AVG).

Gdy klient wykonuje rozszerzoną procedurę składowaną, SQL Server wyszukuje bibliotekę DLL skojarzoną z rozszerzoną procedurą składowaną i ładuje bibliotekę DLL. SQL Server wywołuje żądaną rozszerzoną procedurę składowaną i wykonuje ją w określonym kontekście zabezpieczeń. Rozszerzona procedura składowana przekazuje zestawy wyników i zwraca parametry z powrotem do serwera.

SQL Server udostępnia rozszerzenia Transact-SQL (T-SQL), aby umożliwić instalowanie zestawów do zweryfikowania w SQL Server. Zestaw uprawnień SQL Server określa kontekst zabezpieczeń z następującymi poziomami zabezpieczeń:

- Tryb nieograniczony: uruchamianie kodu na własne ryzyko; kod nie musi być zweryfikowany jako bezpieczny dla typu.

- Tryb awaryjny: uruchamianie sprawdzanego kodu zapewnienia obsługi; skompilowane z/CLR: Safe.

> [!IMPORTANT]
> Program Visual Studio 2015 jest przestarzały, a program Visual Studio 2017 nie obsługuje opcji **/CLR: Pure** i **/CLR: Safe do bezpiecznego** tworzenia projektów, które są możliwe do zweryfikowania. Jeśli wymagany jest kod do zweryfikowania, zalecamy przetłumaczenie kodu do języka C#.

Aby utworzyć i załadować zestaw możliwy do zweryfikowania do SQL Server, Użyj poleceń Transact-SQL CREATE ASSEMBLY i DROP ASSEMBLY w następujący sposób:

```sql
CREATE ASSEMBLY <assemblyName> FROM <'Assembly UNC Path'> WITH
  PERMISSION_SET <permissions>
DROP ASSEMBLY <assemblyName>
```

PERMISSION_SET polecenie określa kontekst zabezpieczeń i może mieć wartości nieograniczone, bezpieczne lub rozszerzone.

Ponadto można użyć polecenia CREATE FUNCTION, aby powiązać z nazwami metod w klasie:

```sql
CREATE FUNCTION <FunctionName>(<FunctionParams>)
RETURNS returnType
[EXTERNAL NAME <AssemblyName>:<ClassName>::<StaticMethodName>]
```

## <a name="example"></a>Przykład

Poniższy skrypt SQL (na przykład o nazwie "webscript. SQL") ładuje zestaw do SQL Server i udostępnia metodę klasy:

```sql
-- Create assembly without external access
drop assembly stockNoEA
go
create assembly stockNoEA
from
'c:\stockNoEA.dll'
with permission_set safe

-- Create function on assembly with no external access
drop function GetQuoteNoEA
go
create function GetQuoteNoEA(@sym nvarchar(10))
returns real
external name stockNoEA:StockQuotes::GetQuote
go

-- To call the function
select dbo.GetQuoteNoEA('MSFT')
go
```

Skrypty SQL mogą być wykonywane interaktywnie w analizatorze zapytań SQL lub w wierszu polecenia za pomocą narzędzia sqlcmd.exe. Poniższy wiersz polecenia nawiązuje połączenie z serwerem programu SQL Server przy użyciu domyślnej bazy danych, używa zaufanego połączenia, wyświetla obiekt webscript. SQL i wyprowadza MyResult.txt.

```cmd
sqlcmd -S MyServer -E -i myScript.sql -o myResult.txt
```

## <a name="see-also"></a>Zobacz też

[Klasy i struktury](../cpp/classes-and-structs-cpp.md)
