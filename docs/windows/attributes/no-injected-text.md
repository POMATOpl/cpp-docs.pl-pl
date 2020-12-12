---
description: 'Dowiedz się więcej na temat: no_injected_text'
title: no_injected_text (atrybut C++ COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.no_injected_text
helpviewer_keywords:
- no_injected_text attribute
ms.assetid: 5256f808-e41e-4f4a-9ea5-e447919f5696
ms.openlocfilehash: 3d6b4b77055b6706256b25b0b722034e0275ec19
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327468"
---
# <a name="no_injected_text"></a>no_injected_text

Uniemożliwia kompilatorowi wstrzyknięcie kodu w wyniku użycia atrybutów.

## <a name="syntax"></a>Składnia

```cpp
[ no_injected_text(boolean) ];
```

### <a name="parameters"></a>Parametry

*typu*<br/>
(Opcjonalnie) **`true`** Jeśli nie chcesz, aby kod został wstrzyknięty, **`false`** Zezwól na wstrzyknięcie kodu. **`true`** jest wartością domyślną.

## <a name="remarks"></a>Uwagi

Typowym zastosowaniem atrybutu **No_injected_text** C++ jest opcja kompilatora [/FX](../../build/reference/fx-merge-injected-code.md) , która wstawia atrybut **No_injected_text** do pliku. MRG.

## <a name="requirements"></a>Wymagania

| Kontekst atrybutu | Wartość |
|-|-|
|**Dotyczy**|Dowolne miejsce|
|**Powtarzalność**|Nie|
|**Wymagane atrybuty**|Brak|
|**Nieprawidłowe atrybuty**|Brak|

Aby uzyskać więcej informacji na temat kontekstów atrybutów, zobacz [konteksty atrybutów](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Zobacz też

[Atrybuty kompilatora](compiler-attributes.md)
