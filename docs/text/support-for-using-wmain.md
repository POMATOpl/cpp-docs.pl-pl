---
description: 'Dowiedz się więcej na temat: obsługa używania wmain'
title: Obsługa używania funkcji wmain
ms.date: 11/04/2016
f1_keywords:
- wWinMain
helpviewer_keywords:
- wide characters [C++], wmain function
- wWinMain function
- wmain function
ms.assetid: 41213c41-668c-40a4-8a1e-77d9eded720d
ms.openlocfilehash: b6a954ab62c9bc675bd2b71275d615b3ee4c1376
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335746"
---
# <a name="support-for-using-wmain"></a>Obsługa używania funkcji wmain

Visual C++ obsługuje definiowanie funkcji **wmain** i przekazywanie argumentów szerokich znaków do aplikacji Unicode. Można zadeklarować formalne parametry do **wmain** przy użyciu formatu podobnego do `main` . Następnie można przekazywać argumenty o szerokim znaku oraz, opcjonalnie, wskaźnik środowiska do programu. `argv`Parametry i `envp` do **wmain** są typu `wchar_t*` . Na przykład:

```cpp
wmain( int argc, wchar_t *argv[ ], wchar_t *envp[ ] )
```

> [!NOTE]
> Aplikacje w formacie Unicode MFC używają `wWinMain` jako punktu wejścia. W tym przypadku `CWinApp::m_lpCmdLine` jest to ciąg Unicode. Upewnij się, że ustawiono `wWinMainCRTStartup` przy użyciu opcji konsolidatora [/entry](../build/reference/entry-entry-point-symbol.md) .

Jeśli program używa funkcji **Main** , środowisko znaków wielobajtowych jest tworzone przez bibliotekę wykonawczą podczas uruchamiania programu. Dwubajtowa kopia środowiska jest tworzona tylko wtedy, gdy jest to konieczne (na przykład przez wywołanie `_wgetenv` `_wputenv` funkcji lub). Podczas pierwszego wywołania do `_wputenv` lub pierwszego wywołania, `_wgetenv` Jeśli środowisko MBCS już istnieje, jest tworzony odpowiadające mu środowisko ciągu znaków. Środowisko jest wskazywane przez `_wenviron` zmienną globalną, która jest wersją znaków dwubajtowych `_environ` zmiennej globalnej. W tym momencie dwie kopie środowiska (MBCS i Unicode) istnieją jednocześnie i są obsługiwane przez system czasu wykonywania przez cały czas trwania programu.

Podobnie, jeśli program używa funkcji **wmain** , środowisko o szerokim znaku jest tworzone przy uruchamianiu programu i jest wskazywane przez `_wenviron` zmienną globalną. Środowisko MBCS (ASCII) jest tworzone podczas pierwszego wywołania do `_putenv` lub `getenv` i jest wskazywane przez `_environ` zmienną globalną.

## <a name="see-also"></a>Zobacz też

[Obsługa formatu Unicode](../text/support-for-unicode.md)<br/>
[Podsumowanie programowania Unicode](../text/unicode-programming-summary.md)<br/>
[WinMain, funkcja](/windows/win32/api/winbase/nf-winbase-winmain)
