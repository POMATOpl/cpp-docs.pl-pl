---
description: 'Dowiedz się więcej: interfejsy obiektu sesji'
title: Interfejsy obiektu sesji
ms.date: 11/19/2018
helpviewer_keywords:
- session objects [OLE DB]
- session objects [OLE DB], interfaces
- OLE DB provider templates, object interfaces
- interfaces, session object
- interfaces, list of
ms.assetid: ac01a958-6dde-4bd7-8b63-94459e488335
ms.openlocfilehash: dc4f5644258b0ced4c97a5cda6de1b69abb8c2f1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286582"
---
# <a name="session-object-interfaces"></a>Interfejsy obiektu sesji

W poniższej tabeli przedstawiono obowiązkowe i opcjonalne interfejsy zdefiniowane przez OLE DB dla obiektu sesji.

|Interfejs|Wymagane?|Zaimplementowane przez OLE DB szablony?|
|---------------|---------------|--------------------------------------|
|[IGetDataSource](/previous-versions/windows/desktop/ms709721(v=vs.85))|Obowiązkowy|Tak|
|[IOpenRowset](/previous-versions/windows/desktop/ms716946(v=vs.85))|Obowiązkowy|Tak|
|[ISessionProperties](/previous-versions/windows/desktop/ms713721(v=vs.85))|Obowiązkowy|Tak|
|[IAlterIndex](/previous-versions/windows/desktop/ms714943(v=vs.85))|Opcjonalne|Nie|
|[IAlterTable](/previous-versions/windows/desktop/ms719764(v=vs.85))|Opcjonalne|Nie|
|[IBindResource](/previous-versions/windows/desktop/ms714936(v=vs.85))|Opcjonalne|Nie|
|[ICreateRow](/previous-versions/windows/desktop/ms716832(v=vs.85))|Opcjonalne|Nie|
|[IDBCreateCommand](/previous-versions/windows/desktop/ms711625(v=vs.85))|Opcjonalne|Tak|
|[IDBSchemaRowset](/previous-versions/windows/desktop/ms713686(v=vs.85))|Opcjonalne|Tak|
|[IIndexDefinition](/previous-versions/windows/desktop/ms711593(v=vs.85))|Opcjonalne|Nie|
|[ISupportErrorInfo](/previous-versions/windows/desktop/ms715816(v=vs.85))|Opcjonalne|Tak|
|[ITableCreation](/previous-versions/windows/desktop/ms713639(v=vs.85))|Opcjonalne|Nie|
|[ITableDefinition](/previous-versions/windows/desktop/ms714277(v=vs.85))|Opcjonalne|Nie|
|[ITableDefinitionWithConstraints](/previous-versions/windows/desktop/ms720947(v=vs.85))|Opcjonalne|Nie|
|[ITransaction](/previous-versions/windows/desktop/ms723053(v=vs.85))|Opcjonalne|Nie|
|[ITransactionJoin](/previous-versions/windows/desktop/ms718071(v=vs.85))|Opcjonalne|Nie|
|[ITransactionLocal](/previous-versions/windows/desktop/ms714893(v=vs.85))|Opcjonalne|Nie|
|[ITransactionObject](/previous-versions/windows/desktop/ms713659(v=vs.85))|Opcjonalne|Nie|

Obiekt Session tworzy obiekt zestawu wierszy. Jeśli dostawca obsługuje polecenia, sesja tworzy również obiekt Command ( `CCommand` , implementując OLE DB `TCommand` ). Obiekt Command implementuje `ICommand` interfejs i używa `ICommand::Execute` metody do wykonywania poleceń na zestawie wierszy, jak pokazano na poniższej ilustracji.

![Diagram koncepcyjny dostawcy](../../data/oledb/media/vc4u551.gif "Diagram koncepcyjny dostawcy")

## <a name="see-also"></a>Zobacz też

[Architektura szablonu dostawcy OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
