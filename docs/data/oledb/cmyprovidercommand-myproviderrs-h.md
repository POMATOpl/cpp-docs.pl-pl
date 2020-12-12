---
description: 'Dowiedz się więcej na temat: CCustomCommand (Customs. H)'
title: CCustomCommand (CustomRS.H)
ms.date: 10/22/2018
f1_keywords:
- cmyprovidercommand
- ccustomcommand
helpviewer_keywords:
- OLE DB providers, wizard-generated files
- CMyProviderCommand class in MyProviderRS.H
- CCustomCommand class in CustomRS.H
ms.assetid: b30b956e-cc91-4cf5-9fe6-f8b1ce9cc2a5
ms.openlocfilehash: 35b0e1a1628920a85343a52ce4a003302468884b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97170506"
---
# <a name="ccustomcommand-customrsh"></a>CCustomCommand (CustomRS.H)

`CCustomCommand`Klasa jest implementacją obiektu polecenia dostawcy. Zawiera implementację `IAccessor` `ICommandText` interfejsów, i `ICommandProperties` . `IAccessor`Interfejs jest taki sam jak w zestawie wierszy. Obiekt Command używa metody dostępu, aby określić powiązania dla parametrów. Obiekt zestawu wierszy używa ich do określania powiązań dla kolumn danych wyjściowych. `ICommandText`Interfejs to przydatny sposób, aby w sposób jednotekstowy określić polecenie. Ten przykład używa `ICommandText` interfejsu później, gdy dodaje kod niestandardowy; zastępuje on również `ICommand::Execute` metodę. `ICommandProperties`Interfejs obsługuje wszystkie właściwości dla obiektów poleceń i zestawów wierszy.

```cpp
// CCustomCommand
class ATL_NO_VTABLE CCustomCommand :
class ATL_NO_VTABLE CCustomCommand :
   public CComObjectRootEx<CComSingleThreadModel>,
   public IAccessorImpl<CCustomCommand>,
   public ICommandTextImpl<CCustomCommand>,
   public ICommandPropertiesImpl<CCustomCommand>,
   public IObjectWithSiteImpl<CCustomCommand>,
   public IConvertTypeImpl<CCustomCommand>,
   public IColumnsInfoImpl<CCustomCommand>
```

`IAccessor`Interfejs zarządza wszystkimi powiązaniami używanymi w poleceniach i zestawach wierszy. Odbiorca wywołuje `IAccessor::CreateAccessor` tablicę `DBBINDING` struktur. Każda `DBBINDING` Struktura zawiera informacje dotyczące sposobu obsługi powiązań kolumn (takich jak typ i długość). Dostawca otrzymuje struktury, a następnie określa, jak powinny być transferowane dane oraz czy są wymagane wszystkie konwersje. `IAccessor`Interfejs jest używany w obiekcie polecenia do obsługi parametrów w poleceniu.

Obiekt Command oferuje również implementację programu `IColumnsInfo` . OLE DB wymaga `IColumnsInfo` interfejsu. Interfejs umożliwia konsumentowi pobieranie informacji o parametrach z polecenia. Obiekt zestawu wierszy używa `IColumnsInfo` interfejsu do zwrócenia informacji o kolumnach wyjściowych do dostawcy.

Dostawca zawiera również interfejs o nazwie `IObjectWithSite` . `IObjectWithSite`Interfejs został zaimplementowany w ATL 2,0 i umożliwia realizatorowi przekazywanie informacji o sobie samym do jego elementu podrzędnego. Obiekt Command używa tych `IObjectWithSite` informacji do poinformowania o tym, kto utworzył wszystkie utworzone obiekty zestawu wierszy.

## <a name="see-also"></a>Zobacz też

[Pliki Wizard-Generated dostawcy](../../data/oledb/provider-wizard-generated-files.md)
