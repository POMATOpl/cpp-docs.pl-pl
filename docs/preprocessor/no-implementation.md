---
description: 'Dowiedz się więcej na temat: no_implementation Importowanie atrybutu'
title: no_implementation atrybut importowania
ms.date: 08/29/2019
f1_keywords:
- no_implementation
helpviewer_keywords:
- no_implementation attribute
ms.assetid: bdc67785-e131-409c-87bc-f4d2f4abb07b
ms.openlocfilehash: 0cfd51b344847d2e5658fd4e4ec1a9f30db51fe6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333333"
---
# <a name="no_implementation-import-attribute"></a>no_implementation atrybut importowania

**Specyficzne dla języka C++**

Pomija generowanie `.tli` nagłówka, który zawiera implementacje funkcji elementu członkowskiego otoki.

## <a name="syntax"></a>Składnia

> **#import** **no_implementation** *biblioteki typów*

## <a name="remarks"></a>Uwagi

Jeśli ten atrybut jest określony, `.tlh` nagłówek wraz z deklaracjami do udostępnienia elementów biblioteki typów, zostanie wygenerowany bez `#include` instrukcji, aby dołączyć `.tli` plik nagłówka.

Ten atrybut jest używany w połączeniu z [implementation_only](../preprocessor/implementation-only.md).

**ZAKOŃCZENIE specyficzne dla języka C++**

## <a name="see-also"></a>Zobacz też

[Atrybuty #import](../preprocessor/hash-import-attributes-cpp.md)\
[#import — dyrektywa](../preprocessor/hash-import-directive-cpp.md)
