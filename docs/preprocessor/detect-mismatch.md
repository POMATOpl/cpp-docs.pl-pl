---
description: 'Dowiedz się więcej na temat: detect_mismatch pragma'
title: detect_mismatch, pragma
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.detect_mismatch
- detect_mismatch_CPP
helpviewer_keywords:
- pragmas, detect_mismatch
- detect_mismatch pragma
ms.assetid: ddb13ac9-0e2f-40ce-be69-7e44c04f5a12
ms.openlocfilehash: e57ffac731409fb14b61d35f780ee19094108655
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97300739"
---
# <a name="detect_mismatch-pragma"></a>detect_mismatch, pragma

Umieszcza rekord w obiekcie. Konsolidator sprawdza te rekordy pod kątem potencjalnych niezgodności.

## <a name="syntax"></a>Składnia

> **#pragma detect_mismatch (** "*Nazwa*" **,** "*wartość*" **)**

## <a name="remarks"></a>Uwagi

Po połączeniu projektu konsolidator zgłasza błąd [LNK2038](../error-messages/tool-errors/linker-tools-error-lnk2038.md) , jeśli projekt zawiera dwa obiekty, które mają taką samą *nazwę* , ale każdy z nich ma inną *wartość*. Użyj tej dyrektywy pragma, aby uniemożliwić łączenie niespójnych plików obiektów.

Zarówno *Nazwa* , jak i *wartość* są literałami ciągów i przestrzegają reguł dla literałów ciągów w odniesieniu do znaków ucieczki i łączenia. Uwzględnia wielkość liter i nie może zawierać przecinka, znaku równości, cudzysłowów ani znaku **null** .

## <a name="example"></a>Przykład

W tym przykładzie tworzone są dwa pliki, które mają różne numery wersji dla tej samej etykiety wersji.

```cpp
// pragma_directive_detect_mismatch_a.cpp
#pragma detect_mismatch("myLib_version", "9")
int main ()
{
   return 0;
}

// pragma_directive_detect_mismatch_b.cpp
#pragma detect_mismatch("myLib_version", "1")
```

Jeśli kompilujesz oba te pliki przy użyciu wiersza polecenia `cl pragma_directive_detect_mismatch_a.cpp pragma_directive_detect_mismatch_b.cpp` , zostanie wyświetlony komunikat o błędzie `LNK2038` .

## <a name="see-also"></a>Zobacz też

[Dyrektywy pragma i słowo kluczowe __pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
