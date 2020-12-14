---
description: 'Dowiedz się więcej na temat: &lt; system_error&gt;'
title: '&lt;system_error&gt;'
ms.date: 03/15/2019
f1_keywords:
- <system_error>
- system_error
helpviewer_keywords:
- system_error header
ms.assetid: 5e046c6e-48d9-4740-8c8a-05f3727c1215
ms.openlocfilehash: 77ff4cae7d40ae4edb393e5d4f6743be1563556c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97259412"
---
# <a name="ltsystem_errorgt"></a>&lt;system_error&gt;

Dołącz nagłówek, \<system_error> Aby zdefiniować klasę wyjątku `system_error` i powiązane szablony służące do przetwarzania błędów systemu niskiego poziomu.

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<system_error>

**Przestrzeń nazw:** std

## <a name="members"></a>Elementy członkowskie

### <a name="objects"></a>Obiekty

|Nazwa|Opis|
|-|-|
|[generic_category](../standard-library/system-error-functions.md#generic_category)|Przedstawia kategorię błędów ogólnych.|
|[is_error_code_enum_v](../standard-library/system-error-functions.md#is_error_code_enum_v)||
|[is_error_condition_enum_v](../standard-library/system-error-functions.md#is_error_condition_enum_v)||
|[system_category](../standard-library/system-error-functions.md#system_category)|Reprezentuje kategorię błędów spowodowanych przepełnieniem systemu niskiego poziomu.|

### <a name="functions"></a>Funkcje

|Nazwa|Opis|
|-|-|
|[make_error_code](../standard-library/system-error-functions.md#make_error_code)|Tworzy obiekt `error_code`.|
|[make_error_condition](../standard-library/system-error-functions.md#make_error_condition)|Tworzy obiekt `error_condition`.|

### <a name="operators"></a>Operatory

|Nazwa|Opis|
|-|-|
|[operator = =](../standard-library/system-error-operators.md#op_eq_eq)|Testuje, czy obiekt po lewej stronie operatora jest równy obiektowi po prawej stronie.|
|[operator! =](../standard-library/system-error-operators.md#op_neq)|Testuje, czy obiekt po lewej stronie operatora nie jest równy obiektowi po prawej stronie.|
|[<operatora ](../standard-library/system-error-operators.md#op_lt)|Sprawdza, czy obiekt jest mniejszy niż obiekt przekazany do porównania.|
|[<<operatora ](../standard-library/system-error-operators.md#op_ostream)||

### <a name="enums"></a>Wyliczenia

|Nazwa|Opis|
|-|-|
|[ERRC —](../standard-library/system-error-enums.md#errc)|Zawiera nazwy symboliczne dla wszystkich makr kodu błędu zdefiniowanych przez POSIX w `<errno.h>` .|

### <a name="classes-and-structs"></a>Klasy i struktury

|Nazwa|Opis|
|-|-|
|[error_category](../standard-library/error-category-class.md)|Reprezentuje abstrakcyjną, popularną bazę dla obiektów, która opisuje kategorię kodów błędów.|
|[error_code](../standard-library/error-code-class.md)|Reprezentuje błędy systemu niskiego poziomu, które są specyficzne dla implementacji.|
|[error_condition](../standard-library/error-condition-class.md)|Reprezentuje kody błędów zdefiniowane przez użytkownika.|
|[skrótu](../standard-library/hash-structure.md#system_error)||
|[is_error_code_enum](../standard-library/is-error-code-enum-class.md)|Reprezentuje predykat typu, który testuje [error_code Wyliczenie klas](../standard-library/error-code-class.md) .|
|[is_error_condition_enum](../standard-library/is-error-condition-enum-class.md)|Reprezentuje predykat typu, który testuje [error_condition Wyliczenie klas](../standard-library/error-condition-class.md) .|
|[system_error](../standard-library/system-error-class.md)|Reprezentuje klasę bazową dla wszystkich wyjątków zgłoszonych w celu zgłaszania przepełnienia systemu niskiego poziomu.|

## <a name="see-also"></a>Zobacz też

[Dokumentacja plików nagłówkowych](../standard-library/cpp-standard-library-header-files.md)
