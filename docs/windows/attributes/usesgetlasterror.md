---
description: 'Dowiedz się więcej na temat: usesgetlasterror'
title: usesgetlasterror (atrybut C++ COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.usesgetlasterror
helpviewer_keywords:
- usesgetlasterror attribute
ms.assetid: d149e33d-35a7-46cb-9137-ae6883d86122
ms.openlocfilehash: f43ae005e2f888f4318900cbde58f449011bd15e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329520"
---
# <a name="usesgetlasterror"></a>usesgetlasterror

Informuje obiekt wywołujący, że jeśli wystąpi błąd podczas wywoływania tej funkcji, wywołujący może następnie wywołać, `GetLastError` Aby pobrać kod błędu.

## <a name="syntax"></a>Składnia

```cpp
[usesgetlasterror]
```

## <a name="remarks"></a>Uwagi

Atrybut **usesgetlasterror** C++ ma takie same funkcje jak atrybut [usesgetlasterror](/windows/win32/Midl/usesgetlasterror) MIDL.

## <a name="example"></a>Przykład

Zobacz przykład [idl_module](idl-module.md) , aby uzyskać przykład użycia **usesgetlasterror**.

## <a name="requirements"></a>Wymagania

| Kontekst atrybutu | Wartość |
|-|-|
|**Dotyczy**|atrybut **modułu**|
|**Powtarzalność**|Nie|
|**Wymagane atrybuty**|Brak|
|**Nieprawidłowe atrybuty**|Brak|

Aby uzyskać więcej informacji na temat kontekstów atrybutów, zobacz [konteksty atrybutów](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Zobacz też

[Atrybuty IDL](idl-attributes.md)
