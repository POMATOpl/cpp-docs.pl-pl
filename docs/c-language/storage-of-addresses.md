---
description: 'Dowiedz się więcej o: przechowywanie adresów'
title: Magazynowanie adresów
ms.date: 11/04/2016
helpviewer_keywords:
- storage [C++], addresses
- addresses [C++], storage of
ms.assetid: 423b2402-b847-4788-ad70-943b7c9c5c8b
ms.openlocfilehash: 8f0b51370659d7a23739d75f53492d171c17e422
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97296696"
---
# <a name="storage-of-addresses"></a>Magazynowanie adresów

Ilość miejsca do magazynowania wymagana dla adresu i znaczenie adresu zależy od implementacji kompilatora. Wskaźniki do różnych typów nie mają takiej samej długości. W związku z tym **sizeof (Char \* )** nie musi być równy **sizeof (int \* )**.

**Specyficzne dla firmy Microsoft**

W przypadku kompilatora języka Microsoft C wartość **sizeof (Char \* )** jest równa **sizeof (int \* )**.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Deklaracje wskaźnika](../c-language/pointer-declarations.md)
