---
description: 'Dowiedz się więcej na temat: ograniczenia dotyczące opóźnień ładowania bibliotek DLL'
title: Ograniczenia bibliotek DLL ładowanych z opóźnieniem
ms.date: 11/04/2016
helpviewer_keywords:
- constraints [C++], delayed loading of DLLs
- delayed loading of DLLs, constraints
- DLLs [C++], constraints
ms.assetid: 0097ff65-550f-4a4e-8ac3-39bf6404f926
ms.openlocfilehash: 45f54ca57b57bc689752a8aa80f4c03bbe096817
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97197013"
---
# <a name="constraints-of-delay-loading-dlls"></a>Ograniczenia bibliotek DLL ładowanych z opóźnieniem

Istnieją ograniczenia dotyczące opóźnień ładowania importów.

- Importowanie danych nie jest obsługiwane. Obejście polega na jawnym obsłudze importu danych przy użyciu `LoadLibrary` (lub `GetModuleHandle` po poznaniu pomocnika ładowania opóźnienia ZAŁADOWAŁ bibliotekę DLL) i `GetProcAddress` .

- Ładowanie z opóźnieniem Kernel32.dll nie jest obsługiwane. Ta biblioteka DLL jest niezbędna do procedury pomocnika ładowania opóźnień w celu wykonania ładowania opóźnienia.

- [Powiązanie](binding-imports.md) punktów wejścia, które są przekazywane, nie jest obsługiwane.

- Opóźnienie ładowania biblioteki DLL może nie skutkować tym samym zachowaniem procesu, jeśli istnieją inicjalizacje poszczególnych procesów w punkcie wejścia biblioteki DLL załadowanej z opóźnieniem. Inne przypadki obejmują statyczny protokół TLS (lokalny magazyn wątków), zadeklarowany przy użyciu [__declspec (wątek)](../../cpp/thread.md), który nie jest obsługiwany podczas ładowania biblioteki DLL za pośrednictwem `LoadLibrary` . Dynamiczny protokół TLS, przy użyciu `TlsAlloc` ,, `TlsFree` `TlsGetValue` , i `TlsSetValue` , jest nadal dostępny do użycia w bibliotekach DLL statycznych lub załadowane z opóźnieniem.

- Statyczne (globalne) wskaźniki funkcji należy ponownie zainicjować dla zaimportowanych funkcji po pierwszym wywołaniu funkcji. Wynika to z faktu, że pierwsze użycie wskaźnika funkcji wskaże thunk.

- Obecnie nie ma możliwości opóźnienia ładowania tylko określonych procedur z biblioteki DLL przy użyciu standardowego mechanizmu importu.

- Niestandardowe Konwencje wywoływania (takie jak używanie kodów warunków w architekturze x86) nie są obsługiwane. Ponadto rejestry zmiennoprzecinkowe nie są zapisywane na żadnej platformie. Jeśli niestandardowa procedura pomocnicza lub procedury podłączania używają typów zmiennoprzecinkowych, muszą one całkowicie zapisywać i przywracać stan zmiennoprzecinkowy na maszynach przy użyciu konwencji wywoływania parametrów zmiennoprzecinkowych. Należy zachować ostrożność podczas ładowania biblioteki DLL CRT, jeśli wywołujesz funkcje CRT, które pobierają parametry zmiennoprzecinkowe na stosie danych liczbowych (NDP) w funkcji pomocy.

## <a name="see-also"></a>Zobacz też

[Obsługa konsolidatora dla Delay-Loaded bibliotek DLL](linker-support-for-delay-loaded-dlls.md)<br/>
[Funkcja LoadLibrary](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryw)<br/>
[GetModuleHandle, funkcja](/windows/win32/api/libloaderapi/nf-libloaderapi-getmodulehandlew)<br/>
[Funkcja GetProcAddress](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress)<br/>
[Funkcja TlsAlloc, funkcja](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsalloc)<br/>
[Funkcja TlsFree, funkcja](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsfree)<br/>
[TlsGetValue, funkcja](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsgetvalue)<br/>
[TlsSetValue, funkcja](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlssetvalue)
