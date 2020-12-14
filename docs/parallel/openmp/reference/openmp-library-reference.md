---
description: 'Dowiedz się więcej na temat: Dokumentacja biblioteki OpenMP'
title: Odwołanie do biblioteki OpenMP
ms.date: 12/02/2019
ms.assetid: a25188c6-edde-43d0-84b5-780e797b08fc
ms.openlocfilehash: fa1f654835afef94b0e00f52bebb0b7300d205be
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342364"
---
# <a name="openmp-library-reference"></a>Odwołanie do biblioteki OpenMP

Oferuje linki do konstrukcji używanych w interfejsie API OpenMP.

Visual C++ implementacja standardu OpenMP obejmuje następujące konstrukcje.

|Konstrukcja|Opis|
|---------------|-----------------|
|[Dyrektyw](openmp-directives.md)|Zawiera łącza do dyrektyw używanych w interfejsie API OpenMP.|
|[Klauzule](openmp-clauses.md)|Zawiera łącza do klauzul używanych w interfejsie API OpenMP.|
|[Funkcje](openmp-functions.md)|Zawiera łącza do funkcji używanych w interfejsie API OpenMP.|
|[Zmienne środowiskowe](openmp-environment-variables.md)|Oferuje linki do zmiennych środowiskowych używanych w interfejsie API OpenMP.|

Funkcje biblioteki wykonawczej OpenMP Visual C++ są zawarte w następujących bibliotekach.

|Biblioteka wykonawcza OpenMP|Właściwości|
|------------------------------|---------------------|
|VCOMP. LIB|Wielowątkowy, dynamiczny link (Biblioteka importowana dla VCOMP140.DLL).|
|VCOMPD. LIB|Wielowątkowy, dynamiczny link (Biblioteka importowana dla VCOMP140D.DLL) (Debugowanie)|

Jeśli _DEBUG jest zdefiniowany w kompilacji i jeśli `#include <omp.h>` znajduje się w kodzie źródłowym, VCOMPD. LIB będzie domyślną lib, w przeciwnym razie VCOMP. Zostanie użyta Biblioteka LIB.

Możesz użyć [/NODEFAULTLIB (Ignoruj biblioteki)](../../../build/reference/nodefaultlib-ignore-libraries.md) , aby usunąć domyślną lib i jawnie połączyć z dowolnie wybraną lib.

Biblioteki OpenMP są w Visual C++ katalog redystrybucyjny i muszą być dystrybuowane z aplikacjami, które używają OpenMP.

## <a name="see-also"></a>Zobacz też

[OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)
