---
description: 'Dowiedz się więcej na temat: cpp_quote'
title: cpp_quote (atrybut C++ COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.cpp_quote
helpviewer_keywords:
- cpp_quote attribute
ms.assetid: f75327ff-42bd-498b-9177-7ffa25427e1f
ms.openlocfilehash: fe8424fd16cb75e320f8c1a1f8e3e444cf2185ea
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333175"
---
# <a name="cpp_quote"></a>cpp_quote

Emituje określony ciąg bez znaków cudzysłowu do wygenerowanego pliku IDL.

## <a name="syntax"></a>Składnia

```cpp
[ cpp_quote("statement") ];
```

### <a name="parameters"></a>Parametry

*Merge*<br/>
Instrukcja języka C.

## <a name="remarks"></a>Uwagi

Atrybut **cpp_quote** C++ jest przydatny, jeśli chcesz umieścić dyrektywę preprocesora w pliku. idl.

Można również użyć **cpp_quote** i wygenerować plik h jako część kompilacji MIDL. Na przykład jeśli masz plik nagłówka C++, który używa atrybutów C++ IDL, ale nie można użyć tego pliku do pewnego zadania, można skompilować go w celu utworzenia pliku MIDL. h, który powinien być w stanie używać.

Atrybut **cpp_quote** ma taką samą funkcjonalność jak atrybut [cpp_quote](/windows/win32/Midl/cpp-quote) MIDL.

## <a name="example"></a>Przykład

Zobacz przykład dla [podwójnego](dual.md) przykładu użycia **cpp_quote**.

## <a name="requirements"></a>Wymagania

| Kontekst atrybutu | Wartość |
|-|-|
|**Dotyczy**|Dowolne miejsce|
|**Powtarzalność**|Nie|
|**Wymagane atrybuty**|Brak|
|**Nieprawidłowe atrybuty**|Brak|

Aby uzyskać więcej informacji na temat kontekstów atrybutów, zobacz [konteksty atrybutów](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Zobacz też

[Atrybuty IDL](idl-attributes.md)<br/>
[Atrybuty autonomiczne](stand-alone-attributes.md)
