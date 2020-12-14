---
description: Dowiedz się więcej na temat identyfikatorów zasobów (symboli) (C++)
title: Identyfikatory zasobów (symbole) (C++)
ms.date: 02/14/2019
f1_keywords:
- vc.editors.symbol.identifiers
helpviewer_keywords:
- symbols [C++], resource identifiers
- symbols [C++], creating
- resource symbols
- symbols [C++], editing
- resource editors [C++], resource symbols
ms.assetid: 8fccc09a-0237-4a65-b9c4-57d60c59e324
ms.openlocfilehash: 1299bb366ba380972d0027dc7285f6ac14dffe37
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247088"
---
# <a name="resource-identifiers-symbols-c"></a>Identyfikatory zasobów (symbole) (C++)

Symbol jest identyfikatorem zasobu (ID), który składa się z dwóch części, nazwy symbolu (ciągu tekstowego) zamapowanego na wartość symbolu (liczba całkowita), na przykład:

```cpp
IDC_EDITNAME = 5100
```

Nazwy symboli są najczęściej określane mianem identyfikatorów.

Symbole zapewniają opisowy sposób odwoływania się do zasobów i obiektów interfejsu użytkownika, zarówno w kodzie źródłowym, jak i podczas pracy z nimi w edytorach zasobów. Można wyświetlać symbole i manipulować nimi w jednym wygodnym miejscu przy użyciu [okna dialogowego symbole zasobów](./creating-new-symbols.md).

W miarę zwiększania się rozmiaru i złożoności aplikacji, więc jest to liczba zasobów i symboli. Śledzenie dużej liczby symboli rozmieszczonych w kilku plikach może być trudne. Okno dialogowe **symbole zasobów** upraszcza zarządzanie symbolami, oferując centralne narzędzie, za pomocą którego można:

- [Tworzenie symboli](../windows/creating-new-symbols.md)

- [Zarządzanie symbolami](../windows/changing-a-symbol-or-symbol-name-id.md)

- [Wyświetlanie wstępnie zdefiniowanych identyfikatorów symboli](../windows/predefined-symbol-ids.md)

Podczas tworzenia nowego zasobu lub obiektu zasobu [edytory zasobów](../windows/resource-editors.md) podają domyślną nazwę zasobu, na przykład, `IDC_RADIO1` i przypisuje do niego wartość. Nazwa i Definicja wartości są przechowywane w `Resource.h` pliku.

> [!NOTE]
> Podczas kopiowania zasobów lub obiektów zasobów z jednego pliku. RC do innego, Visual C++ może zmienić wartość symbolu transferowanego zasobu lub nazwę i wartość symbolu, aby uniknąć konfliktów z nazwami symboli lub wartościami w istniejącym pliku.

## <a name="requirements"></a>Wymagania

Win32

## <a name="see-also"></a>Zobacz też

[Praca z plikami zasobów](../windows/working-with-resource-files.md)<br/>
[Pliki zasobów](../windows/resource-files-visual-studio.md)<br/>
[Edytory zasobów](../windows/resource-editors.md)<br/>
