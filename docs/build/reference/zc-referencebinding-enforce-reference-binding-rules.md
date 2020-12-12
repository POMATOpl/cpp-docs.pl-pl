---
description: 'Dowiedz się więcej o:/Zc: referencebinding (Wymuszanie reguł powiązania odwołań)'
title: /Zc:referenceBinding (Wymuszanie zasad powiązania odwołań)
ms.date: 03/06/2018
f1_keywords:
- referenceBinding
- /Zc:referenceBinding
helpviewer_keywords:
- -Zc compiler options (C++)
- referenceBinding
- Enforce reference binding rules
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 0c6cfaac-9c2a-41a3-aa94-64ca8ef261fc
ms.openlocfilehash: 7d094a2ec3ec680c463a7a756e70e02b9c40c07c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97269162"
---
# <a name="zcreferencebinding-enforce-reference-binding-rules"></a>/Zc:referenceBinding (Wymuszanie zasad powiązania odwołań)

Gdy określona jest opcja **/Zc: referencebinding** , kompilator nie zezwala na odwołanie niestałe lvalue, które ma być powiązane z elementem tymczasowym.

## <a name="syntax"></a>Składnia

> **/Zc: referencebinding**[ **-** ]

## <a name="remarks"></a>Uwagi

Jeśli **/Zc: referencebinding** jest określony, kompilator postępuje zgodnie z sekcją 8.5.3 standardu c++ 11: nie zezwala na wyrażenia, które powiążą typ tymczasowy zdefiniowany przez użytkownika z niestałym odwołaniem lvalue. Domyślnie, lub jeśli **/Zc: referencebinding-** jest określony, kompilator zezwala na takie wyrażenia jako rozszerzenie Microsoft, ale wydawane jest ostrzeżenie poziomu 4. W celu zapewnienia bezpieczeństwa kodu, przenośności i zgodności zalecamy użycie **/Zc: referencebinding**.

Opcja **/Zc: referencebinding** jest domyślnie wyłączona. Opcja kompilatora [/permissive-](permissive-standards-conformance.md) niejawnie ustawia tę opcję, ale można ją zastąpić za pomocą **/Zc: referencebinding-**.

## <a name="example"></a>Przykład

Ten przykład pokazuje rozszerzenie firmy Microsoft, które umożliwia określenie tymczasowego typu zdefiniowanego przez użytkownika do powiązania z niestałym odwołaniem lvalue.

```cpp
// zcreferencebinding.cpp
struct S {
};

void f(S&) {
}

S g() {
    return S{};
}

int main() {
    S& s = g();         // warning C4239 at /W4
    const S& cs = g();  // okay, bound to const ref
    f(g());             // Extension: error C2664 only if /Zc:referenceBinding
}
```

Aby uzyskać więcej informacji na temat problemów ze zgodnością w Visual C++, zobacz [niestandardowe zachowanie](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz   >  stronę właściwości konfiguracja wiersza polecenia **C/C++**  >   .

1. Zmodyfikuj właściwość **Opcje dodatkowe** , aby uwzględnić **/Zc: referencebinding** , a następnie wybierz **OK**.

## <a name="see-also"></a>Zobacz też

[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)<br/>
[/Zc (Zgodność)](zc-conformance.md)<br/>
