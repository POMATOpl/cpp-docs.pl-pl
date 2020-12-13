---
description: 'Dowiedz się więcej na temat: no_namespace Importowanie atrybutu'
title: no_namespace atrybut importowania
ms.date: 08/29/2019
f1_keywords:
- no_namespace
helpviewer_keywords:
- no_namespace attribute
ms.assetid: 5d81b741-a558-451b-b493-1f3b18967337
ms.openlocfilehash: e1503015f455af65a138e4e3e6843fd0516d2773
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333314"
---
# <a name="no_namespace-import-attribute"></a>no_namespace atrybut importowania

**Specyficzne dla języka C++**

Określa, że kompilator nie generuje nazwy przestrzeni nazw.

## <a name="syntax"></a>Składnia

> **#import** **no_namespace** *biblioteki typów*

## <a name="remarks"></a>Uwagi

Zawartość biblioteki typów w `#import` pliku nagłówkowym są zwykle zdefiniowane w przestrzeni nazw. Nazwa przestrzeni nazw jest określona w `library` instrukcji oryginalnego pliku IDL. Jeśli atrybut **no_namespace** jest określony, ta przestrzeń nazw nie jest generowana przez kompilator.

Jeśli chcesz użyć innej nazwy przestrzeni nazw, zamiast tego użyj atrybutu [rename_namespace](../preprocessor/rename-namespace.md) .

**ZAKOŃCZENIE specyficzne dla języka C++**

## <a name="see-also"></a>Zobacz też

[Atrybuty #import](../preprocessor/hash-import-attributes-cpp.md)\
[#import — dyrektywa](../preprocessor/hash-import-directive-cpp.md)
