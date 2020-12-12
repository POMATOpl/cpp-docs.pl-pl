---
description: 'Dowiedz się więcej o: implementacji niestandardowego menedżera ciągów (Metoda zaawansowana)'
title: Implementacja niestandardowego menedżera ciągów (Metoda zaawansowana)
ms.date: 11/04/2016
helpviewer_keywords:
- IAtlStringMgr class, using
ms.assetid: 64ab7da9-47c1-4c4a-9cd7-4cc37e7f3f57
ms.openlocfilehash: 042c0759076d14e2fd0cf8dd91e34c4f1d8bb534
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166970"
---
# <a name="implementation-of-a-custom-string-manager-advanced-method"></a>Implementacja niestandardowego menedżera ciągów (Metoda zaawansowana)

W wyspecjalizowanych sytuacjach może zajść potrzeba wdrożenia niestandardowego menedżera ciągów, który wykonuje więcej niż tylko zmianę sterty używanej do przydzielania pamięci. W takiej sytuacji należy ręcznie zaimplementować interfejs [IAtlStringMgr](../atl-mfc-shared/reference/iatlstringmgr-class.md) jako Menedżera ciągów niestandardowych.

Aby to zrobić, należy najpierw zrozumieć, w jaki sposób [CStringT](../atl-mfc-shared/reference/cstringt-class.md) używa tego interfejsu do zarządzania danymi ciągu. Każde wystąpienie `CStringT` ma wskaźnik do struktury [CStringData](../atl-mfc-shared/reference/cstringdata-class.md) . Ta struktura o zmiennej długości zawiera ważne informacje o ciągu (na przykład długość), a także rzeczywiste dane znakowe dla ciągu. Każdy Menedżer ciągów niestandardowych jest odpowiedzialny za przydzielanie i zwalnianie tych struktur na żądanie `CStringT` .

`CStringData`Struktura składa się z czterech pól:

- [pStringMgr](../atl-mfc-shared/reference/cstringdata-class.md#pstringmgr) To pole wskazuje `IAtlStringMgr` interfejs używany do zarządzania tymi danymi ciągu. Gdy `CStringT` trzeba ponownie przydzielić lub zwolnić bufor ciągów, wywołuje on ponownie przydzielone lub bezpłatne metody tego interfejsu, przekazując `CStringData` strukturę jako parametr. Podczas alokowania `CStringData` struktury w Menedżerze ciągów należy ustawić to pole, aby wskazywało na niestandardowego menedżera ciągów.

- [nDataLength](../atl-mfc-shared/reference/cstringdata-class.md#ndatalength) To pole zawiera bieżącą długość logiczną ciągu przechowywanego w buforze wykluczającą kończącą się wartość null. `CStringT` aktualizuje to pole po zmianie długości ciągu. Podczas alokowania `CStringData` struktury Menedżer ciągów musi ustawić wartość zero. W przypadku ponownej alokacji `CStringData` struktury Menedżer ciągów niestandardowych musi pozostawić to pole bez zmian.

- [nAllocLength](../atl-mfc-shared/reference/cstringdata-class.md#nalloclength) To pole zawiera maksymalną liczbę znaków (z wyłączeniem końcowej wartości null), które mogą być przechowywane w tym buforze ciągów bez ich ponownej alokacji. Gdy `CStringT` program musi zwiększyć długość logiczną ciągu, najpierw sprawdza to pole, aby upewnić się, że w buforze jest wystarczająca ilość miejsca. Jeśli sprawdzenie nie powiedzie się, program `CStringT` wywołuje niestandardowego menedżera ciągów, aby ponownie przydzielić bufor. Podczas alokowania lub ponownej alokacji `CStringData` struktury należy ustawić to pole na co najmniej liczbę znaków żądaną w parametrze *nchar* do [IAtlStringMgr:: Allocate](../atl-mfc-shared/reference/iatlstringmgr-class.md#allocate) lub [IAtlStringMgr:: Reallocate](../atl-mfc-shared/reference/iatlstringmgr-class.md#reallocate). Jeśli w buforze jest więcej miejsca niż jest to wymagane, można ustawić tę wartość, aby odzwierciedlała rzeczywistą ilość dostępnego miejsca. Pozwala to `CStringT` na powiększanie ciągu w celu wypełnienia całego przydzielonego miejsca przed wywołaniem go do Menedżera ciągów w celu ponownego przydzielenia buforu.

- [nRefs](../atl-mfc-shared/reference/cstringdata-class.md#nrefs) To pole zawiera bieżącą liczbę odwołań buforu ciągów. Jeśli wartość jest równa, to pojedyncze wystąpienie `CStringT` jest używane w buforze. Ponadto wystąpienie może odczytywać i modyfikować zawartość bufora. Jeśli wartość jest większa niż jeden, wiele wystąpień `CStringT` może korzystać z bufora. Ponieważ bufor znaków jest współużytkowany, `CStringT` wystąpienia mogą odczytywać tylko zawartość bufora. Aby zmodyfikować zawartość, `CStringT` najpierw tworzy kopię buforu. Jeśli wartość jest ujemna, tylko jedno wystąpienie `CStringT` jest używane w buforze. W takim przypadku bufor jest uznawany za zablokowany. Gdy `CStringT` wystąpienie korzysta z zablokowanego buforu, żadne inne wystąpienia programu `CStringT` mogą współużytkować bufor. Zamiast tego te wystąpienia tworzą kopię buforu przed manipulowaniem zawartością. Ponadto `CStringT` wystąpienie z zablokowanym buforem nie próbuje udostępnić buforu dowolnego `CStringT` przypisanego do niego wystąpienia. W takim przypadku `CStringT` wystąpienie kopiuje drugi ciąg do zablokowanego buforu.

   Podczas alokowania `CStringData` struktury należy ustawić to pole, aby odzwierciedlić typ udostępniania, który jest dozwolony dla buforu. W przypadku większości implementacji należy ustawić tę wartość na jeden. Pozwala to na typowe zachowanie funkcji kopiowania na zapisywanie. Jeśli jednak Menedżer ciągów nie obsługuje udostępniania buforu ciągów, ustaw to pole na stan zablokowany. Wymusza to `CStringT` użycie tego buforu tylko dla wystąpienia `CStringT` , w którym został przydzielony.

## <a name="see-also"></a>Zobacz też

[Zarządzanie pamięcią za pomocą CStringT](../atl-mfc-shared/memory-management-with-cstringt.md)
