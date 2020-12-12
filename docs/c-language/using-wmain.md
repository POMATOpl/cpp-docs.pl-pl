---
description: 'Dowiedz się więcej na temat: korzystanie z wmain'
title: wmain — korzystanie
ms.date: 11/04/2016
helpviewer_keywords:
- wmain function
ms.assetid: d0300812-adc4-40c6-bba3-b2da25468c80
ms.openlocfilehash: 575637700924876ffb3b54a4ea23dc2b62e5feb6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97198937"
---
# <a name="using-wmain"></a>wmain — korzystanie

**Specyficzne dla firmy Microsoft**

W modelu programowania Unicode można zdefiniować wersję funkcji **Main** o szerokim znaku. Użyj **wmain** zamiast **Main** , jeśli chcesz napisać kod przenośny, który jest zgodny z modelem programowania Unicode.

## <a name="syntax"></a>Składnia

```
wmain( int argc, wchar_t *argv[ ], wchar_t *envp[ ] )
```

## <a name="remarks"></a>Uwagi

Należy zadeklarować formalne parametry do **wmain** przy użyciu podobnego formatu do **głównego**. Następnie można przekazywać argumenty o szerokim znaku oraz, opcjonalnie, wskaźnik środowiska do programu. `argv`Parametry i `envp` do **wmain** są typu `wchar_t*` . Na przykład:

Jeśli program używa funkcji **Main** , środowisko znaków wielobajtowych jest tworzone przez bibliotekę wykonawczą podczas uruchamiania programu. Dwubajtowa kopia środowiska jest tworzona tylko wtedy, gdy jest to konieczne (na przykład przez wywołanie `_wgetenv` `_wputenv` funkcji lub). Podczas pierwszego wywołania do `_wputenv` lub pierwszego wywołania, `_wgetenv` Jeśli środowisko MBCS już istnieje, jest tworzone odpowiednie środowisko ciągu znaków dwubajtowych, a następnie wskazywane przez `_wenviron` zmienną globalną, która jest wersja zmiennej globalnej o szerokim znaku `_environ` . W tym momencie dwie kopie środowiska (MBCS i Unicode) istnieją jednocześnie i są obsługiwane przez system operacyjny przez cały czas trwania programu.

Podobnie, jeśli program używa funkcji **wmain** , środowisko o szerokim znaku jest tworzone przy uruchamianiu programu i jest wskazywane przez `_wenviron` zmienną globalną. Środowisko MBCS (ASCII) jest tworzone podczas pierwszego wywołania do `_putenv` lub `getenv` , i jest wskazywane przez `_environ` zmienną globalną.

Aby uzyskać więcej informacji [na temat środowiska MBCS, zobacz](../c-runtime-library/internationalization.md) informacje o liczbie *porządkowej w dokumentacji dotyczącej biblioteki wykonawczej.*

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Funkcja Main i wykonywanie programu](../c-language/main-function-and-program-execution.md)
