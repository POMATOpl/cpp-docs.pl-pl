---
description: 'Dowiedz się więcej na temat: safebuffers'
title: safebuffers
ms.date: 11/04/2016
f1_keywords:
- safebuffers_cpp
helpviewer_keywords:
- __declspec keyword (C++), safebuffers
- safebuffers __declspec keyword
ms.assetid: 0b0dce14-4523-44d2-8070-5dd0fdabc618
ms.openlocfilehash: 8fefa12ffcbd81d58f4f5002e27751f03d7c1cb9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319355"
---
# <a name="safebuffers"></a>safebuffers

**Specyficzne dla firmy Microsoft**

Informuje kompilator, aby nie wstawiać sprawdzeń zabezpieczeń przepełnienia buforu dla funkcji.

## <a name="syntax"></a>Składnia

```
__declspec( safebuffers )
```

## <a name="remarks"></a>Uwagi

Opcja kompilatora **/GS** powoduje, że kompilator testuje przekroczenia buforu przez wstawianie kontroli zabezpieczeń na stosie. Typy struktur danych, które kwalifikują się do kontroli zabezpieczeń, są opisane w [/GS (sprawdzanie zabezpieczeń bufora)](../build/reference/gs-buffer-security-check.md). Aby uzyskać więcej informacji na temat wykrywania przepełnienia buforu, zobacz [funkcje zabezpieczeń w programie MSVC](https://devblogs.microsoft.com/cppblog/security-features-in-microsoft-visual-c/).

Przegląd kodu lub zewnętrzna analiza eksperta może pomóc w ustaleniu, czy funkcja jest zabezpieczona przed przepełnieniem buforu. W takim przypadku można pominąć sprawdzanie zabezpieczeń dla funkcji, stosując **`__declspec(safebuffers)`** słowo kluczowe do deklaracji funkcji.

> [!CAUTION]
> Sprawdzenia zabezpieczeń buforu zapewniają istotną ochronę i mają niewielki wpływ na wydajność. Dlatego zaleca się, aby nie pomijać ich poza rzadkimi przypadkami, gdy wydajność funkcji odgrywa krytyczną rolę i wiadomo, że funkcja jest bezpieczna.

## <a name="inline-functions"></a>Funkcje śródwierszowe

*Funkcja podstawowa* może użyć słowa kluczowego nakreślania, aby wstawić kopię *funkcji pomocniczej*. [](inline-functions-cpp.md) Jeśli **`__declspec(safebuffers)`** słowo kluczowe jest stosowane do funkcji, wykrywanie przepełnienia buforu jest pomijane dla tej funkcji. Niepodkreślanie ma jednak wpływ na **`__declspec(safebuffers)`** słowo kluczowe w następujący sposób.

Załóżmy, że opcja kompilatora **/GS** jest określona dla obu funkcji, ale funkcja podstawowa określa **`__declspec(safebuffers)`** słowo kluczowe. Struktury danych w funkcji pomocniczej uprawniają ją do sprawdzania zabezpieczeń i funkcja nie pomija tych sprawdzeń. W takim przypadku:

- Określ słowo kluczowe [__forceinline](inline-functions-cpp.md) w funkcji pomocniczej, aby wymusić, aby kompilator mógł być wbudowany w funkcję bez względu na optymalizacje kompilatora.

- Ponieważ funkcja pomocnicza kwalifikuje się do sprawdzenia zabezpieczeń, sprawdzanie zabezpieczeń jest również stosowane do podstawowej funkcji, mimo że określa **`__declspec(safebuffers)`** słowo kluczowe.

## <a name="example"></a>Przykład

Poniższy kod pokazuje, jak używać **`__declspec(safebuffers)`** słowa kluczowego.

```cpp
// compile with: /c /GS
typedef struct {
    int x[20];
} BUFFER;
static int checkBuffers() {
    BUFFER cb;
    // Use the buffer...
    return 0;
};
static __declspec(safebuffers)
    int noCheckBuffers() {
    BUFFER ncb;
    // Use the buffer...
    return 0;
}
int wmain() {
    checkBuffers();
    noCheckBuffers();
    return 0;
}
```

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[__declspec](../cpp/declspec.md)<br/>
[Słowa kluczowe](../cpp/keywords-cpp.md)<br/>
[inline, __inline, \_ _forceinline](inline-functions-cpp.md)<br/>
[strict_gs_check](../preprocessor/strict-gs-check.md)
