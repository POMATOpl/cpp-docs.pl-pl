---
description: 'Dowiedz się więcej na temat: rejestrowanie Storage-Class specyfikatora'
title: rejestracja specyfikatora klasy magazynowania
ms.date: 11/04/2016
helpviewer_keywords:
- register variables
- register storage class
ms.assetid: 7577bf48-88ec-4191-873c-ef4217a4034e
ms.openlocfilehash: a7e062f72191f6ee6d678d18b902ea184d362714
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97120760"
---
# <a name="register-storage-class-specifier"></a>rejestracja specyfikatora klasy magazynowania

**Specyficzne dla firmy Microsoft**

Kompilator języka Microsoft C/C++ nie honoruje żądań użytkowników dotyczących zmiennych rejestru. Jednak w przypadku przenoszenia wszystkie inne semantyki skojarzone ze **`register`** słowem kluczowym są uznawane przez kompilator. Na przykład nie można zastosować jednoargumentowego adresu operatora ( **&** ) do obiektu Register ani **`register`** słowa kluczowego nie można używać w tablicach.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Specyfikatory klasy magazynowania dla deklaracji Internal-Level](../c-language/storage-class-specifiers-for-internal-level-declarations.md)
