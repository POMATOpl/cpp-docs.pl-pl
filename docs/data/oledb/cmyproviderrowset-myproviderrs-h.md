---
description: 'Dowiedz się więcej na temat: CCustomRowset (Customs. H)'
title: CCustomRowset (CustomRS.H)
ms.date: 10/22/2018
f1_keywords:
- cmyproviderrowset
- ccustomrowset
helpviewer_keywords:
- OLE DB providers, wizard-generated files
- CMyProviderRowset class in MyProviderRS.H
- CCustomRowset class in CustomRS.H
ms.assetid: 7ba1a124-3842-40eb-a36b-302190a1af3a
ms.openlocfilehash: 87025be2a34f8c850bde2be53ab01519968654d3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97170467"
---
# <a name="ccustomrowset-customrsh"></a>CCustomRowset (CustomRS.H)

Kreator generuje wpis dla obiektu zestawu wierszy. W tym przypadku jest on wywoływany `CCustomRowset` . `CCustomRowset`Klasa dziedziczy z klasy dostawcy OLE DB o nazwie `CRowsetImpl` , która implementuje wszystkie niezbędne interfejsy dla obiektu zestawu wierszy. Poniższy kod przedstawia łańcuch dziedziczenia dla `CRowsetImpl` :

```cpp
template <class T, class Storage, class CreatorClass,
   class ArrayType = CAtlArray<Storage>>
class CMyRowsetImpl:
   public CRowsetImpl<T, Storage, CreatorClass, ArrayType,
      CSimpleRow, IRowsetLocateImpl< T >>
```

`CRowsetImpl` używa również `IAccessor` interfejsów i `IColumnsInfo` . Używa tych interfejsów dla pól danych wyjściowych w tabelach. Klasa zawiera również implementację `IRowsetIdentity` , która umożliwia konsumentowi ustalenie, czy dwa wiersze są takie same. `IRowsetInfo`Interfejs implementuje właściwości dla obiektu zestawu wierszy. `IConvertType`Interfejs umożliwia dostawcy Rozwiązywanie różnic między typami danych żądanymi przez konsumenta a tymi używanymi przez dostawcę.

`IRowset`Interfejs faktycznie obsługuje pobieranie danych. Użytkownik najpierw wywołuje metodę o nazwie `GetNextRows` , aby zwrócić dojście do wiersza, znane jako `HROW` . Konsument następnie wywołuje `IRowset::GetData` program, `HROW` Aby pobrać żądane dane.

`CRowsetImpl` Pobiera również kilka parametrów szablonu. Te parametry umożliwiają określenie sposobu, w jaki `CRowsetImpl` Klasa obsługuje dane. `ArrayType`Argument umożliwia określenie, który mechanizm magazynowania jest używany do przechowywania danych wierszy. Parametr *RowClass* określa, jaka Klasa zawiera `HROW` .

Parametr *RowsetInterface* umożliwia również korzystanie z `IRowsetLocate` `IRowsetScroll` interfejsu lub. `IRowsetLocate`Interfejsy i `IRowsetScroll` dziedziczą z `IRowset` . W związku z tym szablony dostawcy OLE DB muszą zapewnić specjalną obsługę tych interfejsów. Jeśli chcesz użyć dowolnego z tych interfejsów, musisz użyć tego parametru.

## <a name="see-also"></a>Zobacz też

[Pliki Wizard-Generated dostawcy](../../data/oledb/provider-wizard-generated-files.md)<br/>
