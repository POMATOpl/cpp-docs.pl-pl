---
description: 'Dowiedz się więcej: Obsługa konsolidatora dla Delay-Loaded bibliotek DLL'
title: Obsługa konsolidatora dla bibliotek DLL załadowanych z opóźnieniem
ms.date: 11/04/2016
helpviewer_keywords:
- delayed loading of DLLs, linker support
ms.assetid: b2d7e449-2809-42b1-9c90-2c0ca5e31a14
ms.openlocfilehash: 6bf4527d14c7313874f162f0597114132b1a81cb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190968"
---
# <a name="linker-support-for-delay-loaded-dlls"></a>Obsługa konsolidatora dla bibliotek DLL załadowanych z opóźnieniem

Konsolidator MSVC obsługuje teraz opóźnione ładowanie bibliotek DLL. Pozwala to na zwolnienie z konieczności używania funkcji **LoadLibrary** i **GetProcAddress** w Windows SDK Functions w celu zaimplementowania opóźnionego ładowania biblioteki DLL.

Przed Visual C++ 6,0, jedynym sposobem ładowania biblioteki DLL w czasie wykonywania była użycie funkcji **LoadLibrary** i **GetProcAddress**; system operacyjny załaduje plik DLL, gdy plik wykonywalny lub DLL, przy użyciu którego został załadowany.

Począwszy od Visual C++ 6,0, podczas niejawnego łączenia z biblioteką DLL, konsolidator udostępnia opcje opóźnienia ładowania biblioteki DLL do momentu wywołania przez program funkcji w tej bibliotece DLL.

Aplikacja może opóźnić ładowanie biblioteki DLL przy użyciu opcji konsolidatora [/DELAYLOAD (Opóźnij Załaduj import)](delayload-delay-load-import.md) z funkcją pomocnika (domyślna implementacja udostępniona przez Visual C++). Funkcja pomocnika będzie ładować bibliotekę DLL w czasie wykonywania przez wywołanie funkcji **LoadLibrary** i **GetProcAddress** .

Należy rozważyć opóźnienie ładowania biblioteki DLL, jeśli:

- Program może nie wywołać funkcji w bibliotece DLL.

- Funkcja w bibliotece DLL może nie zostać wywołana do momentu opóźnienia wykonywania programu.

Opóźnione ładowanie biblioteki DLL można określić podczas kompilowania. EXE lub. Projekt DLL. Z. Projekt DLL, który opóźnia ładowanie co najmniej jednej biblioteki DLL, nie powinien sam wywołać punktu wejścia załadowanego z opóźnieniem w DllMain.

W poniższych tematach opisano opóźnienia ładowania bibliotek DLL:

- [Określanie bibliotek DLL do opóźnionego ładowania](specifying-dlls-to-delay-load.md)

- [Jawne zwalnianie Delay-Loaded DLL](explicitly-unloading-a-delay-loaded-dll.md)

- [Ładowanie wszystkich importów dla Delay-Loaded DLL](loading-all-imports-for-a-delay-loaded-dll.md)

- [Importowanie powiązań](binding-imports.md)

- [Obsługa błędów i powiadomienia](error-handling-and-notification.md)

- [Dumping Delay-Loaded Importy](dumping-delay-loaded-imports.md)

- [Ograniczenia dotyczące opóźnień ładowania bibliotek DLL](constraints-of-delay-loading-dlls.md)

- [Zrozumienie funkcji pomocnika](understanding-the-helper-function.md)

- [Opracowywanie własnej funkcji pomocnika](developing-your-own-helper-function.md)

## <a name="see-also"></a>Zobacz też

[Tworzenie bibliotek DLL C/C++ w programie Visual Studio](../dlls-in-visual-cpp.md)<br/>
[Dokumentacja konsolidatora MSVC](linking.md)
