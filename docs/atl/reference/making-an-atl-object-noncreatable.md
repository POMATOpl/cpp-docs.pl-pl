---
description: 'Dowiedz się więcej na temat: wprowadzanie obiektu ATL jako niemożliwego do utworzenia'
title: Tworzenie obiektu ATL z atrybutem noncreatable
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.ATL.objects
helpviewer_keywords:
- noncreatable ATL objects
- ATL projects, noncreatable objects
ms.assetid: 80d0bca2-dea0-4801-9a85-6243124437f6
ms.openlocfilehash: 0a7a07081546722e5a960cb8bf0384a1d7e47f9b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139181"
---
# <a name="making-an-atl-object-noncreatable"></a>Tworzenie obiektu ATL z atrybutem noncreatable

Można zmienić atrybuty obiektu COM opartego na ATL, aby klient nie mógł bezpośrednio utworzyć obiektu. W takim przypadku obiekt zostałby zwrócony przez wywołanie metody w innym obiekcie, a nie utworzony bezpośrednio.

## <a name="to-make-an-object-noncreatable"></a>Aby sprawić, że obiekt nie jest możliwy do utworzenia

1. Usuń [OBJECT_ENTRY_AUTO](object-map-macros.md#object_entry_auto) dla obiektu. Jeśli chcesz, aby obiekt miał być niemożliwy do utworzenia, ale formant, który ma być zarejestrowany, Zastąp OBJECT_ENTRY_AUTO z [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](object-map-macros.md#object_entry_non_createable_ex_auto).

1. Dodaj atrybut [](../../windows/attributes/noncreatable.md) niemożliwy do utworzenia do klasy coclass w pliku. idl. Na przykład:

    ```
    [uuid(A1992E3D-3CF0-11D0-826F-00A0C90F2851),
    helpstring("MyObject"),
    noncreatable]
    coclass MyObject
    {
        [default] interface IMyInterface;
    }
    ```

## <a name="see-also"></a>Zobacz też

[Kreator projektu ATL](../../atl/reference/atl-project-wizard.md)<br/>
[Typy projektów C++ w programie Visual Studio](../../build/reference/visual-cpp-project-types.md)<br/>
[Programowanie za pomocą kodu ATL i języka C Run-Time](../../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[Podstawowe informacje o obiektach COM ATL](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[Domyślne konfiguracje projektu ATL](../../atl/reference/default-atl-project-configurations.md)
