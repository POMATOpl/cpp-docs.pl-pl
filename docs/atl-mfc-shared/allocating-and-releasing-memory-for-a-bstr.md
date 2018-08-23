---
title: Alokowanie i zwalnianie pamięci dla BSTR | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- bstr
dev_langs:
- C++
helpviewer_keywords:
- BSTRs, memory allocation
- memory deallocation, string memory
- memory [C++], releasing
- memory allocation, BSTRs
- memory deallocation, BSTR memory
- strings [C++], releasing
ms.assetid: 98041e29-3442-4a02-b425-7a4a13e9cc84
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 355d89a3cb5817cc64512ae885a075bf44ee2a86
ms.sourcegitcommit: b92ca0b74f0b00372709e81333885750ba91f90e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/16/2018
ms.locfileid: "42464570"
---
# <a name="allocating-and-releasing-memory-for-a-bstr"></a>Alokowanie i zwalnianie pamięci dla BSTR
Po utworzeniu `BSTR`s i przekazywać je między obiektami COM, możesz należy zadbać o traktowanie pamięci używają w celu uniknięcia przecieków pamięci. Gdy `BSTR` pozostaje w obrębie interfejsu, należy zwolnić jego pamięci po wykonaniu tych czynności z nim. Jednak gdy `BSTR` przebiegach poza interfejsem, odbierająca obiekt przyjmuje odpowiedzialność za jego zarządzanie pamięcią.  
  
 Ogólnie rzecz biorąc, reguły, przydzielanie i zwalnianie pamięci przydzielonej dla `BSTR`są takie same, w następujący sposób:  
  
-   Gdy zostanie wywołana w funkcji, która oczekuje `BSTR` argument, należy przydzielić pamięci dla `BSTR` przed wywołaniem i zwolnij go później. Na przykład:  
  
     [!code-cpp[NVC_ATLMFC_Utilities#192](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_1.cpp)]  
  
     [!code-cpp[NVC_ATLMFC_Utilities#193](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_2.cpp)]  
  
-   Gdy zostanie wywołana w funkcji, która zwraca `BSTR`, ciąg należy zwolnić samodzielnie. Na przykład:  
  
     [!code-cpp[NVC_ATLMFC_Utilities#194](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_3.cpp)]  
  
     [!code-cpp[NVC_ATLMFC_Utilities#195](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_4.cpp)]  
  
-   Podczas implementacji funkcji, która zwraca `BSTR`, Przydziel ciągu, ale nie zwolnienia. Odbieranie funkcja zwalnia pamięć. Na przykład:  
  
     [!code-cpp[NVC_ATLMFC_Utilities#196](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_5.cpp)]  
  
## <a name="see-also"></a>Zobacz też  
 [Ciągi (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)   
 [CStringT::AllocSysString](../atl-mfc-shared/reference/cstringt-class.md#allocsysstring)   
 [SysAllocString](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-sysallocstring)   
 [SysFreeString](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-sysfreestring)

