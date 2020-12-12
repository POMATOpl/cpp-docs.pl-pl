---
description: 'Dowiedz się więcej na temat: strict_gs_check pragma'
title: strict_gs_check, pragma
ms.date: 08/29/2019
f1_keywords:
- strict_gs_check
- strict_gs_check_CPP
helpviewer_keywords:
- strict_gs_check pragma
ms.assetid: decfec81-c916-42e0-a07f-8cc26df6a7ce
ms.openlocfilehash: 3fa1600bba59077ff66bfb0184bdd3ca4fe0e326
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97197312"
---
# <a name="strict_gs_check-pragma"></a>strict_gs_check, pragma

Ta pragma zapewnia ulepszone sprawdzanie zabezpieczeń.

## <a name="syntax"></a>Składnia

> **#pragma strict_gs_check (** [ **push,** ] { **on**  |  **off** } **)**\
> **#pragma strict_gs_check (pop)**

## <a name="remarks"></a>Uwagi

Instruuje kompilator, aby wstawia losowo plik cookie w stosie funkcji, aby ułatwić wykrycie niektórych kategorii przepełnienia buforu opartego na stosie. Domyślnie `/GS` Opcja kompilatora (sprawdzanie zabezpieczeń bufora) nie wstawia pliku cookie dla wszystkich funkcji. Aby uzyskać więcej informacji, zobacz [/GS (sprawdzanie zabezpieczeń bufora)](../build/reference/gs-buffer-security-check.md).

Kompiluj przy użyciu, `/GS` Aby włączyć **strict_gs_check**.

Użyj tej dyrektywy pragma w modułach kodu, które są narażone na potencjalnie szkodliwe dane. **strict_gs_check** jest agresywną pragmą i jest stosowana do funkcji, które mogą nie wymagać tej obrony, ale jest zoptymalizowana, aby zminimalizować jej wpływ na wydajność wynikowej aplikacji.

Nawet w przypadku korzystania z tej dyrektywy pragma należy dążyć do pisania bezpiecznego kodu. Oznacza to, że kod nie ma przekroczeń buforu. **strict_gs_check** może chronić aplikację przed przekroczeniem buforów, które pozostaną w kodzie.

## <a name="example"></a>Przykład

W tym przykładzie przepełnienie buforu występuje, gdy kopiujemy tablicę do tablicy lokalnej. Podczas kompilowania tego kodu przy użyciu programu `/GS` żaden plik cookie nie zostanie wstawiony w stosie, ponieważ typ danych tablicy jest wskaźnikiem. Dodanie **strict_gs_check** pragma wymusza umieszczenie pliku cookie stosu w stosie funkcji.

```cpp
// pragma_strict_gs_check.cpp
// compile with: /c

#pragma strict_gs_check(on)

void ** ReverseArray(void **pData,
                     size_t cData)
{
    // **_ This buffer is subject to being overrun!! _*_
    void _pReversed[20];

    // Reverse the array into a temporary buffer
    for (size_t j = 0, i = cData; i ; --i, ++j)
        // *** Possible buffer overrun!! ***
            pReversed[j] = pData[i];

    // Copy temporary buffer back into input/output buffer
    for (size_t i = 0; i < cData ; ++i)
        pData[i] = pReversed[i];

    return pData;
}
```

## <a name="see-also"></a>Zobacz też

[Dyrektywy pragma i słowo kluczowe __pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)\
[/GS (Sprawdzanie zabezpieczeń buforu)](../build/reference/gs-buffer-security-check.md)
