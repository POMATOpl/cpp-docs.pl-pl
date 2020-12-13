---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4274'
title: Ostrzeżenie kompilatora (poziom 1) C4274
ms.date: 11/04/2016
f1_keywords:
- C4274
helpviewer_keywords:
- C4274
ms.assetid: 5a948680-7ed1-469f-978d-ae99d154e161
ms.openlocfilehash: aa1f6d3b07c7d788d9e47955c4bb51930522b7a3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340102"
---
# <a name="compiler-warning-level-1-c4274"></a>Ostrzeżenie kompilatora (poziom 1) C4274

\#ident zignorowano; Zapoznaj się z dokumentacją #pragma comment (exestr, "String")

`#ident`Dyrektywa, która wstawia określony przez użytkownika ciąg w obiekcie lub pliku wykonywalnym, jest przestarzała. W związku z tym kompilator ignoruje dyrektywę.

> [!CAUTION]
> Ostrzeżenie C4274 zaleca #pragma użycie dyrektywy [comment (exestr, "String")](../../preprocessor/comment-c-cpp.md) . Jednakże to zalecenie jest przestarzałe i zostanie zmienione w przyszłych wydaniach kompilatora. Jeśli używasz `#pragma` dyrektywy, narzędzie konsolidatora (LINK.exe) ignoruje rekord komentarza utworzony przez dyrektywę i wystawia ostrzeżenie [lnk4229 narzędzi konsolidatora](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md). Zamiast `#ident` dyrektywy zalecamy użycie w aplikacji ciągu zasobu w wersji pliku.

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Usuń dyrektywę `#ident "` *String* `"` .

## <a name="see-also"></a>Zobacz też

[komentarz (C/C++)](../../preprocessor/comment-c-cpp.md)<br/>
[Ostrzeżenie narzędzi konsolidatora LNK4229 narzędzi KONSOLIDATORA](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)<br/>
[Praca z plikami zasobów](../../windows/working-with-resource-files.md)
