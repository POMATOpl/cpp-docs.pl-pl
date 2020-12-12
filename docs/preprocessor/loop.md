---
description: 'Dowiedz się więcej na temat: pragma pętli'
title: loop, pragma
ms.date: 08/29/2019
f1_keywords:
- loop_CPP
- vc-pragma.loop
ms.assetid: 6d5bb428-cead-47e7-941d-7513bbb162c7
ms.openlocfilehash: b54d62a6c9a29a4688453992ad9647d9bc21afd1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167464"
---
# <a name="loop-pragma"></a>loop, pragma

Kontroluje, w jaki sposób kod pętli ma być brany pod uwagę przez funkcję autoparalelizacji, lub wyklucza pętlę z rozważenia przez funkcję autowektoryzator.

## <a name="syntax"></a>Składnia

> **pętla #pragma (hint_parallel (** *n* **))**\
> **Pętla #pragma (no_vector)**\
> **Pętla #pragma (ivdep)**

### <a name="parameters"></a>Parametry

**hint_parallel (** *n* **)**\
Wskazówka dla kompilatora, że ta pętla powinna być równoległa dla *n* wątków, gdzie *n* to dodatnia litera całkowita lub zero. Jeśli *n* to zero, Maksymalna liczba wątków jest używana w czasie wykonywania. Jest to Wskazówka dla kompilatora, a nie polecenia. Nie ma gwarancji, że pętla zostanie równoległa. Jeśli pętla zawiera zależności danych lub problemy strukturalne, nie będzie ona równoległa. Na przykład nie jest równoległy, jeśli przechowuje wartość skalarną, która jest używana poza treścią pętli.

Kompilator ignoruje tę opcję, jeśli nie określono przełącznika kompilatora [/Qpar](../build/reference/qpar-auto-parallelizer.md) .

**no_vector**\
Domyślnie funkcja autowektoryzator próbuje vectorize wszystkie pętle, z których może korzystać. Określ tę pragmę, aby wyłączyć funkcję autowektoryzator dla pętli, która następuje poniżej.

**ivdep**\
Wskazówka kompilatora do ignorowania zależności wektora dla tej pętli.

## <a name="remarks"></a>Uwagi

Aby użyć dyrektywy pragma **pętli** , umieść ją bezpośrednio przed, a nie w, definicję pętli. Pragma obowiązuje dla zakresu pętli, która następuje po niej. Można zastosować wiele pragmów do pętli w dowolnej kolejności, ale każdy z nich musi być każdy w oddzielnej instrukcji pragma.

## <a name="see-also"></a>Zobacz też

[Autoprzetwarzanie równoległe i autowektoryzacji](../parallel/auto-parallelization-and-auto-vectorization.md)\
[Dyrektywy pragma i słowo kluczowe __pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
