---
description: 'Dowiedz się więcej na temat: niekompletne typy'
title: Niekompletne typy
ms.date: 11/04/2016
helpviewer_keywords:
- void keyword [C], incomplete
- types [C], incomplete
- incomplete types
- unions, incomplete
- arrays [C], incomplete types
- void keyword [C]
- structures, incomplete
ms.assetid: 01bc0cf6-9fa7-458c-9371-ecbe54ea6aee
ms.openlocfilehash: b85d7a703d6687ad7ec1b0476b8b8a43930330dc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97243578"
---
# <a name="incomplete-types"></a>Niekompletne typy

*Niekompletny typ* to typ, który opisuje identyfikator, ale nie wymaga informacji wymaganych do określenia rozmiaru identyfikatora. Niekompletny typ może:

- Typ struktury, którego elementy członkowskie nie zostały jeszcze określone.

- Typ Unii, którego elementy członkowskie nie zostały jeszcze określone.

- Typ tablicy, którego wymiar nie został jeszcze określony.

**`void`** Typ jest niekompletnym typem, którego nie można ukończyć. Aby ukończyć niekompletny typ, określ brakujące informacje. W poniższych przykładach pokazano, jak utworzyć i zakończyć niekompletne typy.

- Aby utworzyć niekompletny typ struktury, zadeklaruj typ struktury bez określania jej elementów członkowskich. W tym przykładzie `ps` wskaźnik wskazuje niekompletny typ struktury o nazwie `student` .

    ```C
    struct student *ps;
    ```

- Aby ukończyć niekompletny typ struktury, zadeklaruj ten sam typ struktury w dalszej części tego samego zakresu z określonymi elementami członkowskimi, jak w

    ```C
    struct student
    {
        int num;
    }                   /* student structure now completed */
    ```

- Aby utworzyć niekompletny typ tablicy, zadeklaruj typ tablicy bez określenia jego liczby powtórzeń. Na przykład:

    ```C
    char a[];  /* a has incomplete type */
    ```

- Aby ukończyć niekompletny typ tablicy, zadeklaruj tę samą nazwę później w tym samym zakresie z określoną liczbą powtórzeń, jak w

    ```C
    char a[25]; /* a now has complete type */
    ```

## <a name="see-also"></a>Zobacz też

[Deklaracje i typy](../c-language/declarations-and-types.md)
