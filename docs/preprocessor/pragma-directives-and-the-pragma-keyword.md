---
title: Dyrektywy pragma i słowo kluczowe __pragma
description: Opisuje dyrektywy pragma dostępnych w programach Microsoft Visual C i C++ (MSVC)
ms.date: 10/30/2020
f1_keywords:
- '#pragma'
helpviewer_keywords:
- '#pragma directives, C/C++'
- __pragma keyword
- pragma directives, C/C++
- pragmas, C/C++
- preprocessor
- pragmas
- preprocessor, pragmas
- pragma directives (#pragma)
ms.assetid: 9867b438-ac64-4e10-973f-c3955209873f
ms.openlocfilehash: 784cd413b6b81033c9e49b22d979ece72e5ee101
ms.sourcegitcommit: 3f0c1dcdcce25865d1a1022bcc5b9eec79f69025
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/09/2020
ms.locfileid: "94381548"
---
# <a name="pragma-directives-and-the-__pragma-keyword"></a>Dyrektywy pragma i słowo kluczowe __pragma

Dyrektywy pragma określają funkcje kompilatora specyficzne dla maszyny lub systemu operacyjnego. Słowo kluczowe **__pragma** , które jest specyficzne dla kompilatora Microsoft, umożliwia kod dyrektywy pragma w definicjach makr.

## <a name="syntax"></a>Składnia

> **#`pragma`***token — ciąg*\
> **`__pragma(`***token — ciąg* **`)`** dwa wiodące podkreślenia — ciąg rozszerzenia określony przez firmę Microsoft **`_Pragma(`** *— Literal* **`)`** //C99

## <a name="remarks"></a>Uwagi

Każda implementacja języków C i C++ obsługuje pewne funkcje, które są unikatowe dla komputera lub systemu operacyjnego hosta. Niektóre programy, na przykład, muszą mieć precyzyjną kontrolę nad lokalizacją danych w pamięci lub kontrolować sposób, w jaki niektóre funkcje odbierają parametry. Dyrektywy **#pragma** oferują sposób, w jaki każdy kompilator oferuje funkcje specyficzne dla maszyn i systemu operacyjnego, zachowując ogólną zgodność z językiem C i C++.

Dyrektywy pragma są specyficzne dla maszyny lub systemu operacyjnego według definicji i są zwykle różne dla każdego kompilatora. Dyrektywy pragma mogą być używane w dyrektywach warunkowych, aby zapewnić nową funkcję preprocesora lub dostarczyć do kompilatora informacje zdefiniowane przez implementację.

*Token-String* to seria znaków reprezentująca konkretną instrukcję i argumenty kompilatora, jeśli istnieją. Numer ( **#** ) musi być pierwszym znakiem niebiałym w wierszu zawierającym pragmę. Znaki odstępu mogą oddzielić znak numeru i słowo "pragma". Poniżej **#pragma** Napisz dowolny tekst, który tłumaczy może analizować jako wstępnie przetworzony tokeny. Argument **#pragma** podlega rozwinięciu makra.

*Literał ciągu* jest danymi wejściowymi `_Pragma` . Cudzysłowy zewnętrzne i spacje wiodące/końcowe są usuwane. `\"` jest zastępowany `"` i `\\` jest zastępowany przez `\` .

Kompilator generuje ostrzeżenie, gdy znajdzie pragma, że nie rozpoznaje i kontynuuje Kompilowanie.

Kompilatory Microsoft C i C++ rozpoznają następujące dyrektywy pragma:

:::row:::
   :::column span="":::
      [`alloc_text`](../preprocessor/alloc-text.md)\
      [`auto_inline`](../preprocessor/auto-inline.md)\
      [`bss_seg`](../preprocessor/bss-seg.md)\
      [`check_stack`](../preprocessor/check-stack.md)\
      [`code_seg`](../preprocessor/code-seg.md)\
      [`comment`](../preprocessor/comment-c-cpp.md)\
      [`component`](../preprocessor/component.md)\
      [`conform`](../preprocessor/conform.md)<sup>1</sup>\
      [`const_seg`](../preprocessor/const-seg.md)\
      [`data_seg`](../preprocessor/data-seg.md)\
      [`deprecated`](../preprocessor/deprecated-c-cpp.md)
   :::column-end:::
   :::column span="":::
      [`detect_mismatch`](../preprocessor/detect-mismatch.md)\
      [`fenv_access`](../preprocessor/fenv-access.md)\
      [`float_control`](../preprocessor/float-control.md)\
      [`fp_contract`](../preprocessor/fp-contract.md)\
      [`function`](../preprocessor/function-c-cpp.md)\
      [`hdrstop`](../preprocessor/hdrstop.md)\
      [`include_alias`](../preprocessor/include-alias.md)\
      [`init_seg`](../preprocessor/init-seg.md)<sup>1</sup>\
      [`inline_depth`](../preprocessor/inline-depth.md)\
      [`inline_recursion`](../preprocessor/inline-recursion.md)
   :::column-end:::
   :::column span="":::
      [`intrinsic`](../preprocessor/intrinsic.md)\
      [`loop`](../preprocessor/loop.md)<sup>1</sup>\
      [`make_public`](../preprocessor/make-public.md)\
      [`managed`](../preprocessor/managed-unmanaged.md)\
      [`message`](../preprocessor/message.md)\
      [`omp`](../preprocessor/omp.md)\
      [`once`](../preprocessor/once.md)\
      [`optimize`](../preprocessor/optimize.md)\
      [`pack`](../preprocessor/pack.md)\
      [`pointers_to_members`](../preprocessor/pointers-to-members.md)<sup>1</sup>
   :::column-end:::
   :::column span="":::
      [`pop_macro`](../preprocessor/pop-macro.md)\
      [`push_macro`](../preprocessor/push-macro.md)\
      [`region`, endregion](../preprocessor/region-endregion.md)\
      [`runtime_checks`](../preprocessor/runtime-checks.md)\
      [`section`](../preprocessor/section.md)\
      [`setlocale`](../preprocessor/setlocale.md)\
      [`strict_gs_check`](../preprocessor/strict-gs-check.md)\
      [`unmanaged`](../preprocessor/managed-unmanaged.md)\
      [`vtordisp`](../preprocessor/vtordisp.md)<sup>1</sup>\
      [`warning`](../preprocessor/warning.md)
   :::column-end:::
:::row-end:::

<sup>1</sup> obsługiwane tylko przez kompilator języka C++.

## <a name="pragmas-and-compiler-options"></a>Dyrektywy pragma i opcje kompilatora

Niektóre dyrektywy pragma zapewniają te same funkcje co opcje kompilatora. W przypadku napotkania dyrektywy pragma w kodzie źródłowym zastępuje ona zachowanie określone przez opcję kompilatora. Na przykład jeśli określono [/ZP8](../build/reference/zp-struct-member-alignment.md), można zastąpić to ustawienie kompilatora dla określonych sekcji kodu z [pakietem](../preprocessor/pack.md):

```cmd
cl /Zp8 some_file.cpp
```

```cpp
// some_file.cpp - packing is 8
// ...
#pragma pack(push, 1) - packing is now 1
// ...
#pragma pack(pop) - packing is 8 again
// ...
```

## <a name="the-__pragma-keyword"></a>Słowo kluczowe __pragma ()

Kompilator obsługuje także słowo kluczowe specyficzne dla firmy Microsoft **`__pragma`** , które ma takie same funkcje jak w przypadku **`#pragma`** dyrektywy. Różnica polega na tym, że **`__pragma`** słowo kluczowe jest możliwe do użycia w definicji makra. **`#pragma`** Dyrektywa nie można użyć w definicji makra, ponieważ kompilator interpretuje znak cyfry ("#") w dyrektywie jako [operator tworzenia ciągu (#)](../preprocessor/stringizing-operator-hash.md).

Poniższy przykład kodu demonstruje, jak **`__pragma`** słowo kluczowe może być używane w makrze. Ten kod jest pochodzący z nagłówka *MFCDUAL. h* w próbce ACDUAL w "Przykłady obsługi kompilatora com":

```cpp
#define CATCH_ALL_DUAL \
CATCH(COleException, e) \
{ \
_hr = e->m_sc; \
} \
AND_CATCH_ALL(e) \
{ \
__pragma(warning(push)) \
__pragma(warning(disable:6246)) /*disable _ctlState prefast warning*/ \
AFX_MANAGE_STATE(pThis->m_pModuleState); \
__pragma(warning(pop)) \
_hr = DualHandleException(_riidSource, e); \
} \
END_CATCH_ALL \
return _hr; \
```

## <a name="the-_pragma-preprocessing-operator-c99-c11"></a>`_Pragma`Operator przetwarzania wstępnego (C99, c++ 11)

`_Pragma` jest podobny do słowa kluczowego specyficznego dla firmy Microsoft [`__pragma`](#the-__pragma-keyword) , z wyjątkiem tego, że jest on częścią standardu. Została wprowadzona dla języka C w C99. Język C++ został wprowadzony w języku C++ 11.

 Umożliwia umieszczenie pragm do definicji makra. Ma jeden wiodący znak podkreślenia `_` zamiast dwóch wiodących podkreśleń, `__` które ma słowo kluczowe specyficzne dla firmy Microsoft, a pierwsza litera jest Wielka litera.

Literał ciągu powinien być to, co w przeciwnym razie należy umieścić po *`#pragma`* instrukcji. Na przykład:

```c
#pragma message("the #pragma way")
_Pragma ("message( \"the _Pragma way\")") 
```

Znaki cudzysłowu i ukośniki odwrotne powinny zostać zmienione, jak pokazano powyżej. Ciąg pragma, który nie został rozpoznany, jest ignorowany.

Poniższy przykład kodu demonstruje, jak **`_Pragma`** słowo kluczowe może być używane w makro podobnej do potwierdzeń, gdy nie chcesz otrzymywać ostrzeżenia, gdy wyrażenie warunku ma być stałe. 

Definicja makra używa idiom do/while (0) dla makr wielu instrukcji, aby można było jej używać tak, jakby była jedną instrukcją. Aby uzyskać więcej informacji, zobacz [wielowierszowe makro języka C](https://stackoverflow.com/questions/1067226/c-multi-line-macro-do-while0-vs-scope-block) na Stack Overflow. Instrukcja _Pragma ma zastosowanie tylko do wiersza kodu, który następuje po nim.

```C
// Compile with /W4

#include <stdio.h>
#include <stdlib.h>

#define MY_ASSERT(BOOL_EXPRESSION) \
    do { \
        _Pragma("warning(suppress: 4127)") /* C4127 conditional expression is constant */  \
        if (!(BOOL_EXPRESSION)) {   \
            printf("MY_ASSERT FAILED: \"" #BOOL_EXPRESSION "\" on %s(%d)", __FILE__, __LINE__); \
            exit(-1); \
        } \
    } while (0)

int main()
{
    MY_ASSERT(0 && "Note that there is no warning: C4127 conditional expression is constant");

    return 0;
}
```

## <a name="see-also"></a>Zobacz też

[Dokumentacja preprocesora języka C/C++](../preprocessor/c-cpp-preprocessor-reference.md)\
[Dyrektywy pragma języka C](../c-language/c-pragmas.md)\
[Słowa kluczowe](../cpp/keywords-cpp.md)
