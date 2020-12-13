---
description: 'Dowiedz się więcej o programie: przydzielanie i zwalnianie pamięci dla typu BSTR'
title: Przydzielanie i zwalnianie pamięci dla typu BSTR
ms.date: 11/04/2016
f1_keywords:
- bstr
helpviewer_keywords:
- BSTRs, memory allocation
- memory deallocation, string memory
- memory [C++], releasing
- memory allocation, BSTRs
- memory deallocation, BSTR memory
- strings [C++], releasing
ms.assetid: 98041e29-3442-4a02-b425-7a4a13e9cc84
ms.openlocfilehash: 2b027bdc5615578bc785075ae7e8709e2b3a7ea5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142666"
---
# <a name="allocating-and-releasing-memory-for-a-bstr"></a>Przydzielanie i zwalnianie pamięci dla typu BSTR

Podczas tworzenia `BSTR` i przekazywania ich między obiektami com należy zachować ostrożność podczas przetwarzania pamięci, z której korzystają, aby uniknąć przecieków pamięci. Gdy `BSTR` pozostaje w interfejsie, musisz zwolnić jego pamięć, gdy wszystko jest gotowe. Jednak w przypadku wychodzenia `BSTR` z interfejsu, obiekt odbioru jest odpowiedzialny za zarządzanie pamięcią.

Ogólnie rzecz biorąc, reguły przydzielania i zwalniania pamięci przydzieloną dla `BSTR` s są następujące:

- Gdy wywołujesz funkcję, która oczekuje `BSTR` argumentu, należy przydzielić pamięć dla `BSTR` przed wywołaniem i wydać ją później. Na przykład:

   [!code-cpp[NVC_ATLMFC_Utilities#192](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_1.cpp)]

   [!code-cpp[NVC_ATLMFC_Utilities#193](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_2.cpp)]

- Gdy wywołujesz funkcję, która zwraca `BSTR` , musisz samodzielnie zwolnić ten ciąg. Na przykład:

   [!code-cpp[NVC_ATLMFC_Utilities#194](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_3.cpp)]

   [!code-cpp[NVC_ATLMFC_Utilities#195](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_4.cpp)]

- Podczas implementowania funkcji, która zwraca `BSTR` , Przydziel ciąg, ale nie zwalniaj go. Odebrana funkcja zwalnia pamięć. Na przykład:

   [!code-cpp[NVC_ATLMFC_Utilities#196](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_5.cpp)]

## <a name="see-also"></a>Zobacz też

[Ciągi (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[CStringT:: AllocSysString](../atl-mfc-shared/reference/cstringt-class.md#allocsysstring)<br/>
[SysAllocString](/windows/win32/api/oleauto/nf-oleauto-sysallocstring)<br/>
[SysFreeString](/windows/win32/api/oleauto/nf-oleauto-sysfreestring)
