---
description: 'Dowiedz się więcej o programie: Definiowanie procedur składowanych'
title: Definiowanie procedur składowanych
ms.date: 10/24/2018
helpviewer_keywords:
- stored procedures, syntax
- OLE DB, stored procedures
- stored procedures, defining
- stored procedures, OLE DB
ms.assetid: 54949b81-3275-4dd9-96e4-3eda1ed755f2
ms.openlocfilehash: 52527da031093d82c9d74be5807a5de26f3ee091
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97317691"
---
# <a name="defining-stored-procedures"></a>Definiowanie procedur składowanych

Przed wywołaniem procedury składowanej należy najpierw ją zdefiniować przy użyciu makra [DEFINE_COMMAND](./macros-and-global-functions-for-ole-db-consumer-templates.md#define_command) . Podczas definiowania polecenia należy zauważyć, że parametry ze znakiem zapytania (?) jako znacznik parametru:

```cpp
DEFINE_COMMAND_EX(CMySProcAccessor, _T("{INSERT {name, phone} INTO shippers (?,?)}"))
```

Składnia (użycie nawiasów klamrowych itd.) użyta w przykładach kodu w tym temacie jest specyficzna dla SQL Server. Składnia, która jest używana w procedurach składowanych, może się różnić w zależności od używanego dostawcy.

Następnie w polu Mapa parametru Określ parametry, które zostały użyte w poleceniu, aby wyświetlić listę parametrów w kolejności, w jakiej występują w poleceniu:

```cpp
BEGIN_PARAM_MAP(CMySProcAccessor)
   SET_PARAM_TYPE(DBPARAMIO_INPUT)
   COLUMN_ENTRY(1, m_Name)   // name corresponds to first '?' param
   SET_PARAM_TYPE(DBPARAMIO_INPUT)
   COLUMN_ENTRY(2, m_Phone)  // phone corresponds to second '?' param
END_PARAM_MAP()
```

W poprzednim przykładzie zdefiniowano procedurę przechowywaną. Zwykle w celu wydajnego ponownego użycia kodu baza danych zawiera zestaw wstępnie zdefiniowanych procedur przechowywanych z nazwami, takimi jak `Sales by Year` lub `dt_adduserobject` . Definicje można wyświetlić za pomocą Menedżera SQL Server Enterprise. Są one wywoływane w następujący sposób (rozmieszczenie *?* parametry są zależne od interfejsu procedury składowanej:

```cpp
DEFINE_COMMAND_EX(CMySProcAccessor, _T("{CALL \"Sales by Year\" (?,?) }"))
DEFINE_COMMAND_EX(CMySProcAccessor, _T("{CALL dbo.dt_adduserobject (?,?) }"))
```

Następnie zadeklaruj klasę poleceń:

```cpp
class CMySProc : public CCommand<CAccessor<CMySProcAccessor>>
```

Na koniec Wywołaj procedurę składowaną w `OpenRowset` następujący sposób:

```cpp
CSession m_session;

HRESULT OpenRowset()
{
   return CCommand<CAccessor<CMySProcAccessor>>::Open(m_session);
}
```

Należy również pamiętać, że można zdefiniować procedurę przechowywaną przy użyciu atrybutu bazy danych [db_command](../../windows/attributes/db-command.md) w następujący sposób:

```cpp
db_command("{ ? = CALL dbo.dt_adduserobject }")
```

## <a name="see-also"></a>Zobacz też

[Korzystanie z procedur składowanych](../../data/oledb/using-stored-procedures.md)
