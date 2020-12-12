---
description: 'Dowiedz się więcej na temat: łączenie z CRT w projekcie ATL'
title: Tworzenie linków do CRT w projekcie ATL
ms.date: 11/04/2016
helpviewer_keywords:
- CRT, linking with ATL
- WinMainCRTStartup method
- DllMainCRTStartup method
- wWinMainCRTStartup method
- ATL, C Run-Time library (CRT)
ms.assetid: 650957ae-362c-4ecf-8b03-5d49138e8b5b
ms.openlocfilehash: e54301332d9a83546e41ab42169f06d305bbc6a2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97147631"
---
# <a name="linking-to-the-crt-in-your-atl-project"></a>Tworzenie linków do CRT w projekcie ATL

[Biblioteki C Run-Time](../c-runtime-library/crt-library-features.md) (CRT) udostępniają wiele użytecznych funkcji, które znacznie ułatwiają programowanie podczas projektowania ATL. Wszystkie projekty ATL łączą się z biblioteką CRT. Zalety i wady metody łączenia można zobaczyć w obszarze [zalety i kompromisy metody używanej do łączenia się z CRT](../atl/benefits-and-tradeoffs-of-the-method-used-to-link-to-the-crt.md).

## <a name="effects-of-linking-to-the-crt-on-your-program-image"></a>Efekty łączenia się z CRT na obrazie programu

Jeśli statycznie łączy się z CRT, kod z CRT jest umieszczany w obrazie wykonywalnym i nie trzeba mieć w systemie biblioteki CRT, aby uruchomić obraz. Jeśli dynamicznie utworzysz linki do CRT, odwołania do kodu w bibliotece DLL CRT są umieszczane w obrazie, ale nie sam kod. Aby obraz był uruchamiany w danym systemie, plik CRT DLL musi być obecny w tym systemie. Nawet w przypadku dynamicznego łączenia z CRT może się okazać, że kod może być statycznie połączony (na przykład `DllMainCRTStartup` ).

Podczas łączenia obrazu można jawnie lub niejawnie określić punkt wejścia, do którego będzie wywoływana system operacyjny po załadowaniu obrazu. W przypadku biblioteki DLL domyślny punkt wejścia to `DllMainCRTStartup` . W przypadku pliku EXE jest to `WinMainCRTStartup` . Można przesłonić wartość domyślną przy użyciu opcji konsolidatora/ENTRY. CRT zawiera implementację dla `DllMainCRTStartup` , `WinMainCRTStartup` i `wWinMainCRTStartup` (punkt wejścia Unicode dla exe). Te punkty wejścia dostarczone przez CRT konstruktory wywołań dla obiektów globalnych i inicjują inne struktury danych, które są używane przez niektóre funkcje CRT. Ten kod uruchamiający dodaje informacje o 25K do obrazu, jeśli jest połączony statycznie. Jeśli jest połączony dynamicznie, większość kodu znajduje się w bibliotece DLL, więc rozmiar obrazu pozostaje mały.

Aby uzyskać więcej informacji, zobacz temat konsolidatora [/entry (symbol punktu wejścia)](../build/reference/entry-entry-point-symbol.md).

## <a name="optimization-options"></a>Opcje optymalizacji

Korzystając z opcji konsolidatora/OPT: NOWIN98, można dodatkowo ograniczyć domyślny formant ATL o 10 tys. koszt wydłużenia czasu ładowania w systemach Windows 98. Aby uzyskać więcej informacji na temat opcji łączenia, zobacz [/opt (optymalizacje)](../build/reference/opt-optimizations.md).

## <a name="see-also"></a>Zobacz też

[Programowanie za pomocą kodu ATL i języka C Run-Time](../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[Zachowanie biblioteki wykonawczej DLL i Visual C++](../build/run-time-library-behavior.md)
