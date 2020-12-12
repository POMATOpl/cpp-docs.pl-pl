---
description: 'Dowiedz się więcej o: semantyki CString'
title: Semantyka CString
ms.date: 11/04/2016
helpviewer_keywords:
- semantics in Cstring
- CString objects, assignment semantics
- assignment statements, assigning CString objects
ms.assetid: d4023480-526f-499a-85f6-324b4de5b85f
ms.openlocfilehash: 7c6dde91e7f87908c0c6bc2d49ff455eb79f6eb3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167048"
---
# <a name="cstring-semantics"></a>Semantyka CString

Mimo że obiekty [CString](../atl-mfc-shared/reference/cstringt-class.md) są obiektami dynamicznymi, które mogą rosnąć, działają jak wbudowane typy pierwotne i proste klasy. Każdy `CString` obiekt reprezentuje unikatową wartość. `CString` obiekty powinny być uważane za rzeczywiste ciągi, a nie jako wskaźniki do ciągów.

Można przypisać jeden `CString` obiekt do innego. Jednak po zmodyfikowaniu jednego z tych dwóch `CString` obiektów inny `CString` obiekt nie jest modyfikowany, jak pokazano na poniższym przykładzie:

[!code-cpp[NVC_ATLMFC_Utilities#188](../atl-mfc-shared/codesnippet/cpp/cstring-semantics_1.cpp)]

Zwróć uwagę na przykład, że dwa `CString` obiekty są uważane za równe, ponieważ reprezentują ten sam ciąg znaków. `CString`Klasa przeciąża operator równości ( `==` ) w celu porównania dwóch `CString` obiektów na podstawie ich wartości (zawartości), a nie ich tożsamości (adresu).

## <a name="see-also"></a>Zobacz też

[Ciągi (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)
