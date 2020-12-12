---
description: 'Dowiedz się więcej na temat: Błąd narzędzi konsolidatora LNK1301'
title: Błąd narzędzi konsolidatora LNK1301
ms.date: 11/04/2016
f1_keywords:
- LNK1301
helpviewer_keywords:
- LNK1301
ms.assetid: 760da428-7182-4b25-b20a-de90d4b9a9cd
ms.openlocfilehash: ac282aea62836591c6e30abb3030ef2143a78003
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335954"
---
# <a name="linker-tools-error-lnk1301"></a>Błąd narzędzi konsolidatora LNK1301

Znaleziono moduły CLR LTCG, niezgodne z/LTCG: Parameter

Moduł skompilowany z/CLR i/GL został przekierowany do konsolidatora wraz z jednym z parametrów profilowanych optymalizacji (PGO)/LTCG.

Profilowana Optymalizacja nie jest obsługiwana w przypadku modułów/CLR.

Aby uzyskać więcej informacji, zobacz:

- [/GL (Optymalizacja całego programu)](../../build/reference/gl-whole-program-optimization.md)

- [/LTCG (generowanie kodu w czasie konsolidacji)](../../build/reference/ltcg-link-time-code-generation.md)

- [/CLR (Kompilacja środowiska uruchomieniowego języka wspólnego)](../../build/reference/clr-common-language-runtime-compilation.md)

- [Optymalizacje profilowane](../../build/profile-guided-optimizations.md)

### <a name="to-correct-this-error"></a>Aby poprawić ten błąd

1. Nie Kompiluj z opcją/CLR lub nie łącz z jednym z parametrów PGO na/LTCG.

## <a name="example"></a>Przykład

Poniższy przykład generuje LNK1301:

```cpp
// LNK1301.cpp
// compile with: /clr /GL /link /LTCG:PGI LNK1301.obj
// LNK1301 expected
class MyClass {
public:
   int i;
};
```
