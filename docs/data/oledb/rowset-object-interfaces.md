---
description: 'Dowiedz się więcej na temat: interfejsy obiektów zestawu wierszy'
title: Interfejsy obiektu zestawu wierszy
ms.date: 10/24/2018
helpviewer_keywords:
- interfaces, OLE DB
- OLE DB, interfaces
- rowset objects [OLE DB]
- OLE DB provider templates, object interfaces
- interfaces, list of
ms.assetid: 0d7a5d48-2fe4-434f-a84b-157c1fdc3494
ms.openlocfilehash: fc7cbb0ee7c15cc7414144334018afc93888da01
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316859"
---
# <a name="rowset-object-interfaces"></a>Interfejsy obiektu zestawu wierszy

W poniższej tabeli przedstawiono obowiązkowe i opcjonalne interfejsy zdefiniowane przez OLE DB dla obiektu zestawu wierszy.

|Interfejs|Wymagane?|Zaimplementowane przez OLE DB szablony?|
|---------------|---------------|--------------------------------------|
|[IAccessor](/previous-versions/windows/desktop/ms719672(v=vs.85))|Obowiązkowy|Tak|
|[IColumnsInfo](/previous-versions/windows/desktop/ms724541(v=vs.85))|Obowiązkowy|Tak|
|[IConvertType](/previous-versions/windows/desktop/ms715926(v=vs.85))|Obowiązkowy|Tak|
|[IRowset](/previous-versions/windows/desktop/ms720986(v=vs.85))|Obowiązkowy|Tak|
|[IRowsetInfo](/previous-versions/windows/desktop/ms724541(v=vs.85))|Obowiązkowy|Tak|
|[IChapteredRowset](/previous-versions/windows/desktop/ms718180(v=vs.85))|Opcjonalne|Nie|
|[IColumnsInfo2](/previous-versions/windows/desktop/ms712953(v=vs.85))|Opcjonalne|Nie|
|[IColumnsRowset](/previous-versions/windows/desktop/ms722657(v=vs.85))|Opcjonalne|Nie|
|[IConnectionPointContainer](/windows/win32/api/ocidl/nn-ocidl-iconnectionpointcontainer)|Opcjonalne|Tak (za poorednictwem biblioteki ATL)|
|[IDBAsynchStatus](/previous-versions/windows/desktop/ms709832(v=vs.85))|Opcjonalne|Nie|
|[IGetRow](/previous-versions/windows/desktop/ms718047(v=vs.85))|Opcjonalne|Nie|
|[IRowsetChange](/previous-versions/windows/desktop/ms715790(v=vs.85))|Opcjonalne|Tak|
|[IRowsetChapterMember](/previous-versions/windows/desktop/ms725430(v=vs.85))|Opcjonalne|Nie|
|[IRowsetCurrentIndex](/previous-versions/windows/desktop/ms709700(v=vs.85))|Opcjonalne|Nie|
|[IRowsetFind](/previous-versions/windows/desktop/ms724221(v=vs.85))|Opcjonalne|Nie|
|[IRowsetIdentity](/previous-versions/windows/desktop/ms715913(v=vs.85))|Opcjonalne (ale wymagane dla dostawców poziomu 0)|Tak|
|[IRowsetIndex](/previous-versions/windows/desktop/ms719604(v=vs.85))|Opcjonalne|Nie|
|[IRowsetLocate](/previous-versions/windows/desktop/ms721190(v=vs.85))|Opcjonalne|Tak|
|[IRowsetRefresh](/previous-versions/windows/desktop/ms714892(v=vs.85))|Opcjonalne|Nie|
|[IRowsetScroll](/previous-versions/windows/desktop/ms712984(v=vs.85))|Opcjonalne|Nie|
|[IRowsetUpdate](/previous-versions/windows/desktop/ms714401(v=vs.85))|Opcjonalne|Tak|
|[IRowsetView](/previous-versions/windows/desktop/ms709755(v=vs.85))|Opcjonalne|Nie|
|[ISupportErrorInfo](/previous-versions/windows/desktop/ms715816(v=vs.85))|Opcjonalne|Tak|
|[IRowsetBookmark](/previous-versions/windows/desktop/ms714246(v=vs.85))|Opcjonalne|Nie|

Wygenerowany przez Kreatora obiekt zestawu wierszy implementuje `IAccessor` , `IRowset` i `IRowsetInfo` przez dziedziczenie. Powoduje `IAccessorImpl` powiązanie obu kolumn wyjściowych. `IRowset`Interfejs obsługuje pobieranie wierszy i danych. `IRowsetInfo`Interfejs obsługuje właściwości zestawu wierszy.

## <a name="see-also"></a>Zobacz też

[Architektura szablonu dostawcy OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
