---
description: 'Dowiedz się więcej na temat: atrybut HelpContext'
title: atrybut HelpContext (atrybut C++ COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.helpcontext
helpviewer_keywords:
- helpcontext attribute
ms.assetid: 6fbb022d-a4b7-4989-a02f-7f18a9b0ad96
ms.openlocfilehash: cfedec2f7650490dd266331e6853ba47265aa4ec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335716"
---
# <a name="helpcontext"></a>helpcontext

Określa identyfikator kontekstu, który umożliwia użytkownikowi wyświetlanie informacji o tym elemencie w pliku **pomocy** .

## <a name="syntax"></a>Składnia

```cpp
[ helpcontext(id) ]
```

### <a name="parameters"></a>Parametry

*id*<br/>
Identyfikator kontekstu tematu pomocy. Zobacz [Pomoc HTML: Context-Sensitive pomocy dla programów](../../mfc/html-help-context-sensitive-help-for-your-programs.md) , aby uzyskać więcej informacji na temat identyfikatorów kontekstu.

## <a name="remarks"></a>Uwagi

Atrybut **atrybut HelpContext** C++ ma takie same funkcje jak atrybut [atrybut HelpContext](/windows/win32/Midl/helpcontext) MIDL.

## <a name="example"></a>Przykład

Zobacz przykład dla elementu [DefaultValue](defaultvalue.md) , aby zapoznać się z przykładem korzystania z **atrybut HelpContext**.

## <a name="requirements"></a>Wymagania

| Kontekst atrybutu | Wartość |
|-|-|
|**Dotyczy**|**interfejs**, **`typedef`** , **`class`** , metoda, właściwość|
|**Powtarzalność**|Nie|
|**Wymagane atrybuty**|Brak|
|**Nieprawidłowe atrybuty**|Brak|

Aby uzyskać więcej informacji, zobacz [konteksty atrybutów](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Zobacz też

[Atrybuty IDL](idl-attributes.md)<br/>
[Atrybuty interfejsu](interface-attributes.md)<br/>
[Atrybuty klasy](class-attributes.md)<br/>
[Atrybuty metody](method-attributes.md)<br/>
[Atrybuty typedef, enum, Union i struct](typedef-enum-union-and-struct-attributes.md)<br/>
[helpfile](helpfile.md)<br/>
[helpstring](helpstring.md)
