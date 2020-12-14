---
description: 'Dowiedz się więcej na temat: zalety przenośności zestawu znaków'
title: Zalety przenośności zestawu znaków
ms.date: 11/04/2016
helpviewer_keywords:
- character sets [C++], benefits
- portability [C++], character sets
ms.assetid: bd60b925-1498-4e4f-897b-4c8ce66edcf7
ms.openlocfilehash: 32d78e6a230d664970e819f766d70beb1df52a88
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187627"
---
# <a name="benefits-of-character-set-portability"></a>Zalety przenośności zestawu znaków

Można korzystać z funkcji przenośności w czasie wykonywania w języku MFC i C, nawet jeśli nie zamierzasz obecnie internationalize aplikacji:

- Kodowanie portów sprawia, że podstawa kodu jest elastyczna. Później możesz łatwo przenieść go do formatu Unicode lub MBCS.

- Użycie standardu Unicode sprawia, że aplikacje dla systemu Windows są wydajniejsze. Ponieważ system Windows używa standardu Unicode, ciągi inne niż Unicode przesyłane do i z systemu operacyjnego muszą być tłumaczone, co wiąże się z obciążeniem.

## <a name="see-also"></a>Zobacz też

[Unicode i MBCS](../text/unicode-and-mbcs.md)<br/>
[Obsługa formatu Unicode](../text/support-for-unicode.md)
