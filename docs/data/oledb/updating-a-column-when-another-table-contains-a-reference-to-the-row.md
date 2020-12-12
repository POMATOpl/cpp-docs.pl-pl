---
description: 'Dowiedz się więcej na temat: aktualizowanie kolumny, gdy inna tabela zawiera odwołanie do wiersza'
title: Aktualizowanie kolumny, gdy inna tabela zawiera odwołanie do wiersza
ms.date: 10/24/2018
helpviewer_keywords:
- rowsets, column updates
ms.assetid: abb5db69-055d-431f-b12d-ad2940a661ba
ms.openlocfilehash: 5c4562aaaa435c9745bedd146c04c98158d50cc5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272620"
---
# <a name="updating-a-column-when-another-table-contains-a-reference-to-the-row"></a>Aktualizowanie kolumny, gdy inna tabela zawiera odwołanie do wiersza

Niektórzy dostawcy mogą wykrywać, które kolumny w wierszu zmieniają się, ale wielu dostawców nie może. W efekcie aktualizacja kolumny może spowodować błąd, gdy istnieje odwołanie do wiersza, który próbujesz zaktualizować. Aby rozwiązać ten problem, Utwórz oddzielny akcesor zawierający tylko te kolumny, które chcesz zmienić. Przekaż liczbę tego akcesora do `SetData` .

## <a name="see-also"></a>Zobacz też

[Korzystanie z metod dostępu](../../data/oledb/using-accessors.md)
