---
description: 'Dowiedz się więcej o: &lt; opcjonalne&gt;'
title: '&lt;optional&gt;'
ms.date: 08/06/2019
f1_keywords:
- <optional>
helpviewer_keywords:
- <optional>
ms.openlocfilehash: c1f1e6f99278abf296c361515953a931109f47ae
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201836"
---
# <a name="ltoptionalgt"></a>&lt;optional&gt;

Definiuje szablon klasy kontenera `optional` i kilka szablonów pomocniczych.

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<optional>

**Przestrzeń nazw:** std

## <a name="members"></a>Elementy członkowskie

### <a name="operators"></a>Operatory

|Nazwa|Opis|
|-|-|
|[operator = =](../standard-library/optional-operators.md#op_eq_eq)|Testuje, czy obiekt jest równy innemu obiektowi.|
|[operator! =](../standard-library/optional-operators.md#op_neq)|Testuje, czy obiekt nie jest równy innemu obiektowi.|
|[<operatora ](../standard-library/optional-operators.md#op_lt)|Testuje, czy obiekt po lewej stronie jest mniejszy niż obiekt po prawej stronie.|
|[<operatora =](../standard-library/optional-operators.md#op_lt_eq)|Testuje, czy obiekt po lewej stronie jest mniejszy niż lub równy obiektowi po prawej stronie.|
|[>operatora ](../standard-library/optional-operators.md#op_gt)|Testuje, czy obiekt po lewej stronie jest większy niż obiekt po prawej stronie.|
|[>operatora =](../standard-library/optional-operators.md#op_lt_eq)|Testuje, czy obiekt po lewej stronie jest większy lub równy obiektowi po prawej stronie.|

> [!NOTE]
> Oprócz porównania relacyjnego \<optional> Operatory obsługują również porównanie z **nullopt** i `T` .

### <a name="functions"></a>Funkcje

|Nazwa|Opis|
|-|-|
|[make_optional](../standard-library/optional-functions.md#make_optional)|Sprawia, że obiekt jest opcjonalny.|
|[wymiany](../standard-library/optional-functions.md#swap)|Zamienia zawarte wartości dwóch `optional` obiektów.|

### <a name="classes-and-structs"></a>Klasy i struktury

|Nazwa|Opis|
|-|-|
|hash|Zwraca wartość skrótu zawartego obiektu.|
|[optional, klasa](../standard-library/optional-class.md)|Opisuje obiekt, który może lub nie może zawierać wartości.|
|[Struktura nullopt_t](../standard-library/nullopt-t-structure.md)|Opisuje obiekt, który nie utrzymuje wartości.|
|[Klasa bad_optional_access](../standard-library/bad-optional-access-class.md)|Opisuje obiekt zgłoszony jako wyjątek, aby zgłosić próbę uzyskania dostępu do wartości, która nie istnieje.|

### <a name="objects"></a>Obiekty

|Nazwa|Opis|
|-|-|
|[nullopt](../standard-library/optional-functions.md#nullopt)|Wystąpienie `nullopt_t` do porównywania.|

## <a name="see-also"></a>Zobacz też

[Dokumentacja plików nagłówkowych](../standard-library/cpp-standard-library-header-files.md)
