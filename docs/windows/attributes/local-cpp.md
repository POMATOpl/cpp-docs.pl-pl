---
description: 'Dowiedz się więcej na temat: Local (C++)'
title: Local (atrybut C++ COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.local
helpviewer_keywords:
- local attribute
ms.assetid: 35cdd668-bd8e-492a-b7b8-263e7b662437
ms.openlocfilehash: 7fa1366b78576224f8fcc0d91392fe1fc6cb8af9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327508"
---
# <a name="local-c"></a>local (C++)

W przypadku użycia w nagłówku interfejsu, umożliwia użycie kompilatora MIDL jako generatora nagłówka. W przypadku użycia w pojedynczej funkcji określa procedurę lokalną, dla której nie są generowane żadne wycinki.

## <a name="syntax"></a>Składnia

```cpp
[local]
```

## <a name="remarks"></a>Uwagi

**Lokalny** atrybut C++ ma taką samą funkcjonalność jak [lokalny](/windows/win32/Midl/local) atrybut MIDL.

## <a name="example"></a>Przykład

Zobacz [call_as](call-as.md) , aby zapoznać się z przykładem użycia **lokalnego**.

## <a name="requirements"></a>Wymagania

| Kontekst atrybutu | Wartość |
|-|-|
|**Dotyczy**|**interfejs**, metoda interfejsu|
|**Powtarzalność**|Nie|
|**Wymagane atrybuty**|Brak|
|**Nieprawidłowe atrybuty**|`dispinterface`|

Aby uzyskać więcej informacji, zobacz [konteksty atrybutów](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Zobacz też

[Atrybuty IDL](idl-attributes.md)<br/>
[Atrybuty interfejsu](interface-attributes.md)<br/>
[Atrybuty metody](method-attributes.md)<br/>
[call_as](call-as.md)
