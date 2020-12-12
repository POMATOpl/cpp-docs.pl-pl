---
description: 'Dowiedz się więcej na temat: Spectre'
title: spectre
ms.date: 01/23/2018
f1_keywords:
- spectre_cpp
- spectre
- nomitigation
helpviewer_keywords:
- __declspec keyword (C++), spectre
- spectre __declspec keyword
ms.openlocfilehash: fc1f56a59dea1eaa3596a6f7a7c0347ab822e302
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113821"
---
# <a name="spectre"></a>spectre

**Specyficzne dla firmy Microsoft**

Instruuje kompilator, aby nie wstawiał Spectre wariantów 1 instrukcji związanych z barierą wykonywania w przypadku funkcji.

## <a name="syntax"></a>Składnia

> **__declspec (Spectre (nołagodzenie))**

## <a name="remarks"></a>Uwagi

Opcja kompilatora [/Qspectre](../build/reference/qspectre.md) powoduje, że kompilator wstawi instrukcje dotyczące bariery wykonywania spekulacyjnych. Są wstawiane, gdy analiza wskazuje, że istnieje luka w zabezpieczeniach Spectre wariant 1. Określone instrukcje są zależne od procesora. Chociaż te instrukcje powinny mieć minimalny wpływ na rozmiar kodu lub wydajność, mogą wystąpić sytuacje, w których kod nie ma wpływu na ten problem i wymaga maksymalnej wydajności.

Analiza ekspertów może określić, że funkcja jest bezpieczna z Spectre wariantów 1. Sprawdź wady pomijania. W takim przypadku można pominąć generowanie kodu ograniczenia w ramach funkcji przez zastosowanie `__declspec(spectre(nomitigation))` do deklaracji funkcji.

> [!CAUTION]
> **/Qspectree** instrukcje dotyczące barierowego wykonywania zapewniają ważną ochronę zabezpieczeń i mają znikomy wpływ na wydajność. Dlatego zaleca się, aby nie pomijać ich poza rzadkimi przypadkami, gdy wydajność funkcji odgrywa krytyczną rolę i wiadomo, że funkcja jest bezpieczna.

## <a name="example"></a>Przykład

Poniższy kod przedstawia sposób korzystania z programu `__declspec(spectre(nomitigation))` .

```cpp
// compile with: /c /Qspectre
static __declspec(spectre(nomitigation))
int noSpectreIssues() {
    // No Spectre variant 1 vulnerability here
    // ...
    return 0;
}

int main() {
    noSpectreIssues();
    return 0;
}
```

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[__declspec](../cpp/declspec.md)<br/>
[Słowa kluczowe](../cpp/keywords-cpp.md)<br/>
[/Qspectre](../build/reference/qspectre.md)
