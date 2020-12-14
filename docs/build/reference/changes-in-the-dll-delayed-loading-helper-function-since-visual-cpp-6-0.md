---
description: 'Dowiedz się więcej na temat: zmiany w funkcji pomocnika opóźnionego ładowania bibliotek DLL od Visual C++ 6,0'
title: Zmiany w funkcjach pomocnika opóźnionego załadunku bibliotek DLL po Visual C++ 6.0
ms.date: 11/04/2016
helpviewer_keywords:
- delayed loading of DLLs, what's changed
- PFromRva method
- __delayLoadHelper2 function
- helper functions, what's changed
ms.assetid: 99f0be69-105d-49ba-8dd5-3be7939c0c72
ms.openlocfilehash: 0141467aab0b804cf82d21c15510d8f9941853a6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182492"
---
# <a name="changes-in-the-dll-delayed-loading-helper-function-since-visual-c-60"></a>Zmiany w funkcjach pomocnika opóźnionego załadunku bibliotek DLL po Visual C++ 6.0

Jeśli masz wiele wersji Visual C++ na komputerze lub jeśli zdefiniowano własną funkcję pomocnika, może to mieć wpływ na zmiany wprowadzone w funkcji pomocnika opóźnionego załadowania biblioteki DLL. Na przykład:

- **__delayLoadHelper** jest teraz **__delayLoadHelper2**

- **__pfnDliNotifyHook** jest teraz **__pfnDliNotifyHook2**

- **__pfnDliFailureHook** jest teraz **__pfnDliFailureHook2**

- **__FUnloadDelayLoadedDLL** jest teraz **__FUnloadDelayLoadedDLL2**

> [!NOTE]
> Jeśli używasz domyślnej funkcji pomocnika, te zmiany nie wpłyną na Ciebie. Nie ma żadnych zmian dotyczących sposobu wywoływania konsolidatora.

## <a name="multiple-versions-of-visual-c"></a>Wiele wersji Visual C++

Jeśli masz wiele wersji Visual C++ na komputerze, upewnij się, że konsolidator pasuje do delayimp. lib. Jeśli wystąpi niezgodność, otrzymasz raportowanie błędów konsolidatora albo `___delayLoadHelper2@8` `___delayLoadHelper@8` jako nierozpoznany symbol zewnętrzny. Dawna sugeruje nowy konsolidator przy użyciu starego delayimp. lib, a drugi oznacza stary konsolidator przy użyciu nowej delayimp. lib.

Jeśli wystąpi błąd konsolidatora, uruchom [polecenia DUMPBIN/LINKERMEMBER](linkermember.md): 1 w Delayimp. lib, który powinien zawierać funkcję pomocnika, aby zobaczyć, która funkcja pomocnika jest zdefiniowana. Funkcja pomocnika może być również zdefiniowana w pliku obiektu; Uruchom [polecenia DUMPBIN/Symbols](symbols.md) i Wyszukaj `delayLoadHelper(2)` .

Jeśli wiesz, że masz Visual C++ konsolidatora 6,0, a następnie:

- Uruchom polecenia DUMPBIN w pliku lib lub obj pomocnika opóźnionego ładowania, aby określić, czy definiuje **__delayLoadHelper2**. Jeśli nie, łącze zakończy się niepowodzeniem.

- Zdefiniuj **__delayLoadHelper** w pliku lib lub obj pomocnika ładowania opóźnienia.

## <a name="user-defined-helper-function"></a>User-Defined funkcja pomocnika

Jeśli zdefiniowano własną funkcję pomocnika i korzystasz z bieżącej wersji Visual C++, wykonaj następujące czynności:

- Zmień nazwę funkcji pomocnika na **__delayLoadHelper2**.

- Ponieważ wskaźniki w deskryptorze opóźnienia (ImgDelayDescr w Delayimp. h) zostały zmienione z adresów bezwzględnych (VAs) na adresy względne (RVA), aby działały zgodnie z oczekiwaniami w programach 32 i 64-bitowych, należy przekonwertować te elementy z powrotem na wskaźniki. Wprowadzono nową funkcję: PFromRva, która znajduje się w Delayhlp. cpp. Można użyć tej funkcji dla każdego pola w deskryptorze, aby przekonwertować je z powrotem na wskaźniki 32-lub 64-bitowe. Domyślna funkcja pomocnika ładowania opóźnienia nadal jest dobrym szablonem do użycia jako przykładu.

## <a name="load-all-imports-for-a-delay-loaded-dll"></a>Załaduj wszystkie Importy dla Delay-Loaded DLL

Konsolidator może załadować wszystkie importy z biblioteki DLL, która została określona do załadowania opóźnienia. Aby uzyskać więcej informacji [, zobacz Ładowanie wszystkich importów dla Delay-Loaded dll](loading-all-imports-for-a-delay-loaded-dll.md) .

## <a name="see-also"></a>Zobacz też

[Zrozumienie funkcji pomocnika](understanding-the-helper-function.md)
