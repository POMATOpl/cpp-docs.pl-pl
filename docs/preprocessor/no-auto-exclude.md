---
description: 'Dowiedz się więcej na temat: no_auto_exclude Importowanie atrybutu'
title: no_auto_exclude atrybut importowania
ms.date: 08/29/2019
f1_keywords:
- no_auto_exclude
helpviewer_keywords:
- no_auto_exclude attribute
ms.assetid: 3241ef9c-758a-4e86-bdc5-37da6072430f
ms.openlocfilehash: 81e4d7e7f9295a4ed983e2a5024d891e30fe1361
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333354"
---
# <a name="no_auto_exclude-import-attribute"></a>no_auto_exclude atrybut importowania

**Specyficzne dla języka C++**

Wyłącza automatyczne wykluczenie.

## <a name="syntax"></a>Składnia

> **#import** **no_auto_exclude** *biblioteki typów*

## <a name="remarks"></a>Uwagi

Biblioteki typów mogą zawierać definicje elementów zdefiniowanych w nagłówkach systemowych lub innych bibliotekach typów. `#import` próbuje uniknąć wielu błędów definicji przez automatyczne wyłączenie takich elementów. Powoduje to wystawienie [ostrzeżenia kompilatora (poziom 3)](../error-messages/compiler-warnings/compiler-warning-level-3-c4192.md) dla każdego elementu, który ma zostać wykluczony. Można wyłączyć automatyczne wykluczenie przy użyciu tego atrybutu.

**ZAKOŃCZENIE specyficzne dla języka C++**

## <a name="see-also"></a>Zobacz też

[Atrybuty #import](../preprocessor/hash-import-attributes-cpp.md)\
[#import — dyrektywa](../preprocessor/hash-import-directive-cpp.md)
