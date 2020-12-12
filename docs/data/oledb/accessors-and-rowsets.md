---
description: 'Dowiedz się więcej o: metody dostępu i zestawy wierszy'
title: Metody dostępu i zestawy wierszy
ms.date: 11/19/2018
helpviewer_keywords:
- accessors [C++]
- OLE DB consumer templates, rowset support
- OLE DB consumer templates, accessors
- rowsets [C++], accessing
- bulk rowsets
- CAccessorRowset class, accessor types
- single rowsets
- CArrayRowset class, accessors
- CBulkRowset class, accessors
- array rowsets
- CAccessorBase class
- CRowset class, accessors and rowsets
- accessors [C++], rowsets
- rowsets [C++], supported types
ms.assetid: edc9c8b3-1a2d-4c2d-869f-7e058c631042
ms.openlocfilehash: 5bda7957f808319de596edf51b6cb3e378c14254
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97246113"
---
# <a name="accessors-and-rowsets"></a>Metody dostępu i zestawy wierszy

Aby ustawić i pobrać dane, OLE DB szablony używają akcesora i zestawu wierszy za pomocą klasy [CAccessorRowset](../../data/oledb/caccessorrowset-class.md) . Ta klasa może obsługiwać wiele metod dostępu różnych typów.

## <a name="accessor-types"></a>Typy metod dostępu

Wszystkie metody dostępu pochodzą z [CAccessorBase](../../data/oledb/caccessorbase-class.md). `CAccessorBase` zawiera powiązanie parametrów i kolumn.

Na poniższej ilustracji przedstawiono typy metod dostępu.

![Typy metod dostępu](../../data/oledb/media/vcaccessortypes.gif "Typy metod dostępu")<br/>
Klasy akcesora

- [CAccessor](../../data/oledb/caccessor-class.md) Użyj tej metody dostępu, jeśli znasz strukturę źródła bazy danych w czasie projektowania. `CAccessor` statycznie wiąże rekord bazy danych zawierający bufor ze źródłem danych.

- [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) Użyj tej metody dostępu, jeśli nie znasz struktury bazy danych w czasie projektowania. `CDynamicAccessor` wywołuje `IColumnsInfo::GetColumnInfo` , aby uzyskać informacje o kolumnie bazy danych. Tworzy akcesor i zarządza nim, a bufor.

- [CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md) Ta metoda dostępu umożliwia obsługę nieznanych typów poleceń. Podczas przygotowywania poleceń program `CDynamicParameterAccessor` może uzyskać informacje o parametrach z `ICommandWithParameters` interfejsu, jeśli dostawca obsługuje `ICommandWithParameters` .

- [CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md), [CDynamicStringAccessorA —](../../data/oledb/cdynamicstringaccessora-class.md)i [CDynamicStringAccessorW —](../../data/oledb/cdynamicstringaccessorw-class.md) używają tych klas, gdy nie masz wiedzy o schemacie bazy danych. `CDynamicStringAccessorA` Pobiera dane jako ciągi ANSI; `CDynamicStringAccessorW` Pobiera dane jako ciągi Unicode.

- [CManualAccessor](../../data/oledb/cmanualaccessor-class.md) Za pomocą tej klasy można użyć dowolnego typu danych, który ma być używany, jeśli dostawca może skonwertować typ. Obsługuje zarówno kolumny wynikowe, jak i parametry polecenia.

Poniższa tabela zawiera podsumowanie obsługi typów akcesorów OLE DB szablonu.

|Typ metody dostępu|Dynamiczny|Obsługuje parametry|Buffer|Wiele metod dostępu|
|-------------------|-------------|--------------------|------------|------------------------|
|`CAccessor`|Nie|Tak|Użytkownik|Tak|
|`CDynamicAccessor`|Tak|Nie|Szablony OLE DB|Nie|
|`CDynamicParameterAccessor`|Tak|Tak|Szablony OLE DB|Nie|
|`CDynamicStringAccessor[A,W]`|Tak|Nie|Szablony OLE DB|Nie|
|`CManualAccessor`|Tak|Tak|Użytkownik|Tak|

## <a name="rowset-types"></a>Typy zestawów wierszy

Szablony OLE DB obsługują trzy rodzaje zestawów wierszy (patrz Poprzednia ilustracja): pojedyncze zestawy wierszy (zaimplementowane przez [CRowset](../../data/oledb/crowset-class.md)), zbiorcze zestawy wierszy (zaimplementowane przez [CBulkRowset](../../data/oledb/cbulkrowset-class.md)) i zestawy wierszy tablicy (zaimplementowane przez [CArrayRowset](../../data/oledb/carrayrowset-class.md)). Pojedynczy zestaw wierszy Pobiera dojście pojedynczego wiersza, gdy `MoveNext` jest wywoływana. Zestawy wierszy zbiorczych mogą pobierać uchwyty wielu wierszy. Zestawy wierszy tablic są zestawami wierszy, do których można uzyskać dostęp za pomocą składni tablicy.

Na poniższej ilustracji przedstawiono typy zestawów wierszy.

![Ilustracja zestawu wierszy](../../data/oledb/media/vcrowsettypes.gif "Ilustracja zestawu wierszy")<br/>
Klasy zestawu wierszy

[Zestawy wierszy schematu](../../data/oledb/obtaining-metadata-with-schema-rowsets.md) nie uzyskują dostępu do danych w magazynie danych, ale zamiast tego uzyskują dostęp do informacji o magazynie danych o nazwie Metadata. Zestawy wierszy schematu są zwykle używane w sytuacjach, w których struktura bazy danych nie jest znana w czasie kompilacji i musi być uzyskana w czasie wykonywania.

## <a name="see-also"></a>Zobacz też

[OLE DB Szablony konsumentów](../../data/oledb/ole-db-consumer-templates-cpp.md)
