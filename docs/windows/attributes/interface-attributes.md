---
description: 'Dowiedz się więcej o: atrybuty interfejsu'
title: Atrybuty interfejsu (C++ COM)
ms.date: 10/02/2018
helpviewer_keywords:
- attributes [C++/CLI], reference topics
- interface attributes
ms.assetid: 27fcdfee-abce-4585-8b53-ee31635356e8
ms.openlocfilehash: 4a2584f6d0ad73427c9460cd5ddafb92d11db9b0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118332"
---
# <a name="interface-attributes"></a>Atrybuty interfejsu

Następujące atrybuty dotyczą słowa kluczowego [Interface (lub __interface)](../../cpp/interface.md) języka C++.

|Atrybut|Opis|
|---------------|-----------------|
|[async_uuid](async-uuid.md)|Określa identyfikator UUID, który kieruje kompilator MIDL do definiowania synchronicznych i asynchronicznych wersji interfejsu COM.|
|[celnej](custom-cpp.md)|Umożliwia zdefiniowanie własnych atrybutów.|
|[dispinterface](dispinterface.md)|Umieszcza interfejs w pliku. idl jako interfejs wysyłania.|
|[obsługi](dual.md)|Umieszcza interfejs w pliku. idl jako podwójny interfejs.|
|[wywozu](export.md)|Powoduje, że struktura danych zostanie umieszczona w pliku IDL.|
|[helpcontext](helpcontext.md)|Określa identyfikator kontekstu, który umożliwia użytkownikowi wyświetlanie informacji o tym elemencie w pliku pomocy.|
|[helpfile](helpfile.md)|Ustawia nazwę pliku pomocy dla biblioteki typów.|
|[helpstring](helpstring.md)|Określa ciąg znaków, który jest używany do opisania elementu, do którego ma zastosowanie.|
|[helpstringcontext](helpstringcontext.md)|Określa identyfikator tematu pomocy w pliku HLP lub chm.|
|[helpstringdll](helpstringdll.md)|Określa nazwę biblioteki DLL, która ma być używana do przeszukiwania ciągu dokumentu (lokalizacja).|
|[ukryte](hidden.md)|Wskazuje, że element istnieje, ale nie powinien być wyświetlany w przeglądarce zorientowanej na użytkownika.|
|[library_block](library-block.md)|Umieszcza konstrukcję w bloku biblioteki pliku IDL.|
|[LAN](local-cpp.md)|Umożliwia użycie kompilatora MIDL jako generatora nagłówka, gdy jest używany w nagłówku interfejsu. W przypadku użycia w pojedynczej funkcji określa procedurę lokalną, dla której nie są generowane żadne wycinki.|
|[nonextensible](nonextensible.md)|Określa, że `IDispatch` implementacja zawiera tylko właściwości i metody wymienione w opisie interfejsu i nie można go rozszerzyć z dodatkowymi elementami członkowskimi w czasie wykonywania. Ten atrybut jest prawidłowy tylko w [podwójnym](dual.md) interfejsie.|
|[odl](odl.md)|Identyfikuje interfejs jako interfejs ODL (Object Description Language).|
|[Stream](object-cpp.md)|Identyfikuje niestandardowy interfejs.|
|[oleautomation](oleautomation.md)|Wskazuje, że interfejs jest zgodny z automatyzacją.|
|[pointer_default](pointer-default.md)|Określa domyślny atrybut wskaźnika dla wszystkich wskaźników oprócz wskaźników najwyższego poziomu, które są wyświetlane na listach parametrów.|
|[ptr](ptr.md)|Wyznacza wskaźnik jako pełny wskaźnik.|
|[podlega](restricted.md)|Określa, które elementy członkowskie biblioteki nie mogą być wywoływane arbitralnie.|
|[uuid](uuid-cpp-attributes.md)|Zapewnia unikatowy identyfikator biblioteki|

Aby zdefiniować interfejs, należy przestrzegać następujących zasad:

- Domyślna konwencja wywoływania to [__stdcall](../../cpp/stdcall.md).

- Identyfikator GUID jest dostarczany dla Ciebie, jeśli nie zostanie podany.

- Nie są dozwolone żadne przeciążone metody.

Jeśli nie określisz atrybutu [UUID](uuid-cpp-attributes.md) i używasz tej samej nazwy interfejsu w różnych projektach atrybutów, generowany jest ten sam identyfikator GUID.

## <a name="see-also"></a>Zobacz też

[Atrybuty według użycia](attributes-by-usage.md)
