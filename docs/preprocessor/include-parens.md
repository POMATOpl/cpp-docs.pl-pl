---
description: 'Dowiedz się więcej na temat: dołączanie () atrybutu importowania'
title: include () — atrybut importowania
ms.date: 08/29/2019
f1_keywords:
- include()
helpviewer_keywords:
- include() attribute
ms.assetid: 86c9dcb2-d9e0-4fd5-97d7-0bb3e23d6ecc
ms.openlocfilehash: e1164526f95bf1b916cd684a892fbef35027f984
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97236480"
---
# <a name="include-import-attribute"></a>include () — atrybut importowania

**Specyficzne dla języka C++**

Wyłącza automatyczne wykluczenie.

## <a name="syntax"></a>Składnia

> **#import** dołączenia *do biblioteki typów* **("**_Name1_**"** [__, "__*NAME2*__"__ ...] __)__

### <a name="parameters"></a>Parametry

*Name1*\
Pierwszy element do wymuszenia.

*NAME2*\
Drugi element, który ma zostać wywymuszany (w razie potrzeby).

## <a name="remarks"></a>Uwagi

Biblioteki typów mogą zawierać definicje elementów zdefiniowanych w nagłówkach systemowych lub innych bibliotekach typów. `#import` próbuje uniknąć wielu błędów definicji przez automatyczne wyłączenie takich elementów. Jeśli niektóre elementy nie powinny być wykluczone automatycznie, może zostać wyświetlone [Ostrzeżenie kompilatora (poziom 3) C4192](../error-messages/compiler-warnings/compiler-warning-level-3-c4192.md). Za pomocą tego atrybutu można wyłączyć automatyczne wykluczenie. Ten atrybut może przyjmować dowolną liczbę argumentów, jedną dla każdej nazwy elementu biblioteki typów do uwzględnienia.

**ZAKOŃCZENIE specyficzne dla języka C++**

## <a name="see-also"></a>Zobacz też

[Atrybuty #import](../preprocessor/hash-import-attributes-cpp.md)\
[#import — dyrektywa](../preprocessor/hash-import-directive-cpp.md)
