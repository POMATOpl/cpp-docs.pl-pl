---
description: 'Dowiedz się więcej na temat: Unikanie rywalizacji sterty'
title: Unikanie rywalizacji o sterty
ms.date: 11/04/2016
helpviewer_keywords:
- heap contention
ms.assetid: 797129d7-5f8c-4b0e-8974-bb93217e9ab5
ms.openlocfilehash: c58849bee46dd0d870d1067f17581429339fbc0e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142574"
---
# <a name="avoidance-of-heap-contention"></a>Unikanie rywalizacji o sterty

Domyślnymi menedżerami ciągów udostępnianymi przez MFC i ATL są proste otoki na stosie globalnym. Ta globalna sterta jest w pełni bezpieczna wątkowo, co oznacza, że wiele wątków może przydzielać i zwalniać pamięć z niej jednocześnie bez uszkodzenia sterty. Aby zapewnić bezpieczeństwo wątków, sterta musi serializować dostęp do samego siebie. Jest to zwykle realizowane z sekcją krytyczną lub podobnym mechanizmem blokowania. Za każdym razem, gdy dwa wątki próbują uzyskać dostęp jednocześnie do sterty, jeden wątek jest blokowany do momentu zakończenia żądania innego wątku. W przypadku wielu aplikacji zdarza się to rzadko, a wpływ na wydajność mechanizmu blokowania sterty jest nieznaczny. Jednak w przypadku aplikacji, które często uzyskują dostęp do sterty z wielu wątków rywalizacja o blokadę sterty, może spowodować, że aplikacja będzie działać wolniej niż w przypadku maszyn z wieloma procesorami.

Aplikacje korzystające z [CStringT](../atl-mfc-shared/reference/cstringt-class.md) są szczególnie podatne na rywalizację sterty, ponieważ operacje na `CStringT` obiektach często wymagają ponownej alokacji buforu ciągu.

Jednym ze sposobów na złagodzenie rywalizacji sterty między wątkiem jest przydzielenie przez każdy wątek ciągów z prywatnego, lokalnego sterty wątku. Tak długo, jak ciągi przypisane do alokatora określonego wątku są używane tylko w tym wątku, Alokator nie musi być bezpieczny wątkowo.

## <a name="example"></a>Przykład

Poniższy przykład ilustruje procedurę wątku, która alokuje własną prywatną, niebezpieczną stertę do użycia dla ciągów w tym wątku:

[!code-cpp[NVC_ATLMFC_Utilities#182](../atl-mfc-shared/codesnippet/cpp/avoidance-of-heap-contention_1.cpp)]

## <a name="comments"></a>Komentarze

Można uruchomić wiele wątków przy użyciu tej samej procedury wątku, ale ponieważ każdy wątek ma własne sterty, nie ma rywalizacji między wątkami. Ponadto fakt, że każda sterta nie jest bezpieczna wątkowo, zapewnia wymierny wzrost wydajności nawet wtedy, gdy jest uruchomiona tylko jedna kopia wątku. Jest to wynik sterty, która nie korzysta z kosztownych operacji wykonywanych w celu ochrony przed współbieżnym dostępem.

W przypadku bardziej skomplikowanej procedury wątku może być wygodne przechowywanie wskaźnika do Menedżera ciągów wątku w gnieździe lokalnego magazynu wątków (TLS). Umożliwia to innym funkcjom wywoływanym przez procedurę wątku dostęp do Menedżera ciągów wątku.

## <a name="see-also"></a>Zobacz też

[Zarządzanie pamięcią za pomocą CStringT](../atl-mfc-shared/memory-management-with-cstringt.md)
