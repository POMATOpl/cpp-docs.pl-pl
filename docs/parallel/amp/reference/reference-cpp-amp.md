---
description: 'Dowiedz się więcej na temat: Reference (C++ AMP)'
title: Odwołanie (C++ AMP)
ms.date: 11/04/2016
f1_keywords:
- amp/Concurrency::Reference (C++ AMP)
helpviewer_keywords:
- C++ Accelerated Massive Parallelism, reference
ms.assetid: 372a8aed-8a53-48c9-996f-9c3cf09c9fa8
ms.openlocfilehash: 043522d7524078c3c7fec956021fdd7a86347169
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327627"
---
# <a name="reference-c-amp"></a>Odwołanie (C++ AMP)

Ta sekcja zawiera informacje referencyjne dotyczące środowiska uruchomieniowego C++ Accelerated Massive Parallelism (C++ AMP).

> [!NOTE]
> Standard języka C++ rezerwuje użycie identyfikatorów, które zaczynają się od znaku podkreślenia ( `_` ) dla implementacji takich jak biblioteki. Nie należy używać nazw zaczynających się od znaku podkreślenia w kodzie. Zachowanie elementów kodu, których nazwy są zgodne z tą konwencją, nie jest gwarantowane i może ulec zmianie w przyszłych wydaniach. Z tego powodu takie elementy kodu zostały pominięte w tej dokumentacji.

## <a name="in-this-section"></a>W tej sekcji

[Przestrzeń nazw współbieżności (C++ AMP)](concurrency-namespace-cpp-amp.md)<br/>
Dostarcza klasy i funkcje, które umożliwiają przyspieszenie kodu C++ na urządzeniach równoległych danych.

[Concurrency::direct3d — Przestrzeń nazw](concurrency-direct3d-namespace.md)<br/>
Udostępnia funkcje, które obsługują współdziałanie D3D. Pozwala bezproblemowo korzystać z zasobów D3D do obliczeń w kodzie AMP i używania zasobów utworzonych w AMP w kodzie D3D, bez tworzenia nadmiarowych kopii pośrednich. Za pomocą C++ AMP można stopniowo przyspieszyć sekcje aplikacji DirectX intensywnie korzystających z mocy obliczeniowej i korzystać z interfejsu API D3D na danych wyprodukowanych z obliczeń AMP.

[Concurrency::fast_math — Przestrzeń nazw](concurrency-fast-math-namespace.md)<br/>
Funkcje w `fast_math` przestrzeni nazw nie są zgodne z C99. Udostępniane są tylko wersje o pojedynczej precyzji każdej funkcji. Te funkcje korzystają z funkcji wewnętrznych DirectX, które są szybsze niż odpowiednie funkcje w `precise_math` przestrzeni nazw i nie wymagają rozszerzonej podwójnej precyzji wsparcia dla akceleratora, ale są mniej dokładne. Istnieją dwie wersje każdej funkcji dla zgodności na poziomie źródła z kodem C99; Obie wersje pobierają i zwracają wartości pojedynczej precyzji.

[Concurrency::graphics — Przestrzeń nazw](concurrency-graphics-namespace.md)<br/>
Zawiera typy i funkcje, które są przeznaczone do programowania grafiki.

[Współbieżność::p recise_math przestrzeni nazw](concurrency-precise-math-namespace.md)<br/>
Funkcje w `precise_math` przestrzeni nazw są zgodne z C99. Dostępne są zarówno wersje o pojedynczej precyzji, jak i podwójnej precyzji każdej funkcji. Te funkcje — obejmuje funkcje o pojedynczej precyzji — wymagają rozszerzonej obsługi podwójnej precyzji dla akceleratora.

## <a name="related-sections"></a>Sekcje pokrewne

[C++ AMP (C++ Accelerated Massive Parallelism)](../../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)<br/>
C++ AMP przyspiesza wykonywanie kodu C++ przez skorzystanie z zalet sprzętu równoległego danych, który jest powszechnie obecny jako procesor graficzny (GPU) na dyskretnej karcie graficznej.
