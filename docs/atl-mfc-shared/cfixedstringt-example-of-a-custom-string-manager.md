---
description: 'Dowiedz się więcej na temat: CFixedStringT: przykład niestandardowego menedżera ciągów'
title: 'CFixedStringT: przykład niestandardowego menedżera ciągów'
ms.date: 11/04/2016
helpviewer_keywords:
- CFixedStringT class, using a custom string manager
ms.assetid: 1cf11fd7-51b8-4b94-87af-02bc25f47dd6
ms.openlocfilehash: c9af2530500ad5972c01d063116e7ac981109493
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142509"
---
# <a name="cfixedstringt-example-of-a-custom-string-manager"></a>CFixedStringT: przykład niestandardowego menedżera ciągów

Biblioteka ATL implementuje jeden przykład niestandardowego menedżera ciągów używanego przez klasę [CFixedStringT](../atl-mfc-shared/reference/cfixedstringt-class.md)o nazwie **CFixedStringMgr**. `CFixedStringT` pochodzi od [CStringT](../atl-mfc-shared/reference/cstringt-class.md) i implementuje ciąg, który alokuje dane znakowe jako część `CFixedStringT` samego obiektu, tak długo, jak ciąg jest krótszy niż długość określona przez `t_nChars` parametr szablonu `CFixedStringT` . W tym podejściu ciąg nie wymaga sterty, chyba że długość ciągu przekracza rozmiar stałego buforu. Ponieważ program nie `CFixedStringT` zawsze używa sterty do przydzielenia danych ciągu, nie może użyć `CAtlStringMgr` jej jako Menedżera ciągów. Używa niestandardowego menedżera ciągów ( `CFixedStringMgr` ), implementując Interfejs [IAtlStringMgr](../atl-mfc-shared/reference/iatlstringmgr-class.md) . Ten interfejs został omówiony w [implementacji niestandardowego menedżera ciągów (Metoda zaawansowana)](../atl-mfc-shared/implementation-of-a-custom-string-manager-advanced-method.md).

Konstruktor dla `CFixedStringMgr` Pobiera trzy parametry:

- *pData:* Wskaźnik do stałej struktury, `CStringData` która ma zostać użyta.

- *nchar:* Maksymalna liczba znaków, jaką `CStringData` może zawierać struktura.

- *pMgr:* Wskaźnik do `IAtlStringMgr` interfejsu "Menedżer ciągu kopii zapasowej".

Konstruktor przechowuje wartości *pData* i *pMgr* w odpowiednich zmiennych składowych ( `m_pData` i `m_pMgr` ). Następnie ustawia długość buforu na zero, dostępną długość równą maksymalnemu rozmiarowi stałego buforu i liczbę odwołań do-1. Wartość licznika odwołań wskazuje, że bufor jest zablokowany i aby można było użyć tego wystąpienia `CFixedStringMgr` jako Menedżera ciągów.

Oznaczenie bufora jako zablokowanego uniemożliwia innym `CStringT` wystąpieniem przechowywanie udostępnionego odwołania do buforu. Jeśli inne `CStringT` wystąpienia mogły udostępnić bufor, może być możliwe usunięcie buforu zawartego w `CFixedStringT` usłudze, gdy inne ciągi nadal używają buforu.

`CFixedStringMgr` jest pełną implementacją `IAtlStringMgr` interfejsu. Implementacja każdej metody jest omawiana osobno.

## <a name="implementation-of-cfixedstringmgrallocate"></a>Implementacja elementu CFixedStringMgr:: Allocate

Implementacja `CFixedStringMgr::Allocate` pierwszego sprawdzenia do sprawdzenia, czy żądany rozmiar ciągu jest mniejszy niż lub równy rozmiarowi stałego buforu (przechowywanego w `m_pData` elemencie członkowskim). Jeśli stały bufor jest wystarczająco duży, program `CFixedStringMgr` zablokuje stały bufor o długości zero. O ile długość ciągu nie rośnie niż rozmiar stałego buforu, `CStringT` nie będzie konieczne ponowne przydzielenie buforu.

Jeśli żądany rozmiar ciągu jest większy niż stały bufor `CFixedStringMgr` przesyła żądanie do Menedżera ciągów kopii zapasowych. Menedżer ciągów kopii zapasowych jest przypuszczalny do przydzielenia buforu ze sterty. Jednak przed zwróceniem tego buforu `CFixedStringMgr` zablokuje bufor i zastępuje wskaźnik Menedżera ciągów buforu wskaźnikiem do `CFixedStringMgr` obiektu. Zapewnia to, że próby przydzielenia lub zwolnienia buforu przez `CStringT` program będą wywoływały `CFixedStringMgr` .

## <a name="implementation-of-cfixedstringmgrreallocate"></a>Implementacja elementu CFixedStringMgr:: Reallocate

Implementacja programu `CFixedStringMgr::ReAllocate` jest bardzo podobna do implementacji programu `Allocate` .

Jeśli bufor jest ponownie przydzielany, a żądany rozmiar buforu jest mniejszy niż stały bufor, alokacja nie zostanie wykonana. Jeśli jednak przydział buforu nie jest stałym buforem, musi być buforem przydzielonym przez Menedżera kopii zapasowych. W takim przypadku do ponownego przydzielenia buforu jest używany Menedżer kopii zapasowych.

Jeśli bufor jest przydzielany ponownie, a nowy rozmiar buforu jest zbyt duży, aby zmieścił się w ramach stałego buforu, `CFixedStringMgr` przydzieli nowy bufor przy użyciu Menedżera kopii zapasowych. Zawartość stałego buforu jest następnie kopiowana do nowego buforu.

## <a name="implementation-of-cfixedstringmgrfree"></a>Implementacja elementu CFixedStringMgr:: Free

Implementacja jest `CFixedStringMgr::Free` zgodna z tym samym wzorcem co `Allocate` i `ReAllocate` . Jeśli zwolniony bufor jest stałym buforem, Metoda ustawia go na zablokowany bufor o zerowej długości. Jeśli zwolniony bufor został przydzielony do Menedżera kopii zapasowych, program `CFixedStringMgr` używa Menedżera kopii zapasowych do zwolnienia.

## <a name="implementation-of-cfixedstringmgrclone"></a>Implementacja elementu CFixedStringMgr:: Clone

Implementacja `CFixedStringMgr::Clone` zawsze zwraca wskaźnik do Menedżera kopii zapasowych, a nie do `CFixedStringMgr` samego siebie. Dzieje się tak, ponieważ każde wystąpienie elementu `CFixedStringMgr` może być skojarzone tylko z jednym wystąpieniem `CStringT` . Wszystkie inne wystąpienia `CStringT` prób klonowania Menedżera powinny otrzymać zamiast niego Menedżera kopii zapasowych. Wynika to z faktu, że Menedżer kopii zapasowych obsługuje udostępnianie.

## <a name="implementation-of-cfixedstringmgrgetnilstring"></a>Implementacja elementu CFixedStringMgr:: GetNilString

Implementacja `CFixedStringMgr::GetNilString` zwraca stały bufor. Ze względu na to, że dla `CFixedStringMgr` i `CStringT` , danego wystąpienia `CStringT` nigdy nie używa więcej niż jednego buforu jednocześnie. W związku z tym w tym samym czasie nigdy nie jest wymagany żaden ciąg i bufor prawdziwy.

Za każdym razem, gdy stały bufor nie jest używany, `CFixedStringMgr` zapewnia, że zostanie zainicjowany z zerową długością. Pozwala to na użycie go jako ciągu Nil. W ramach dodanej premii `nAllocLength` element członkowski stałego buforu jest zawsze ustawiany na pełny rozmiar stałego buforu. Oznacza to, że `CStringT` można zwiększyć ciąg bez wywoływania [IAtlStringMgr:: Reallocate](../atl-mfc-shared/reference/iatlstringmgr-class.md#reallocate), nawet dla ciągu Nil.

## <a name="requirements"></a>Wymagania

**Nagłówek:** CStringT. h

## <a name="see-also"></a>Zobacz też

[Zarządzanie pamięcią za pomocą CStringT](../atl-mfc-shared/memory-management-with-cstringt.md)
