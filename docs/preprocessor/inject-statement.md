---
description: 'Dowiedz się więcej na temat: inject_statement Importowanie atrybutu'
title: inject_statement atrybut importowania
ms.date: 08/29/2019
f1_keywords:
- inject_statement
helpviewer_keywords:
- inject_statement attribute
ms.assetid: 07d6f0f4-d9fb-4e18-aa62-f235f142ff5e
ms.openlocfilehash: b7ab8059e95ed3799857fe1b899ef2efff729ffb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97236428"
---
# <a name="inject_statement-import-attribute"></a>inject_statement atrybut importowania

**Specyficzne dla języka C++**

Wstawia swój argument jako tekst źródłowy do nagłówka biblioteki typów.

## <a name="syntax"></a>Składnia

> **#import** inject_statement *biblioteki typów* **(** "*Źródło tekstu*" **)**

### <a name="parameters"></a>Parametry

*tekst źródłowy*\
Tekst źródłowy, który ma zostać wstawiony do pliku nagłówkowego biblioteki typów.

## <a name="remarks"></a>Uwagi

Tekst jest umieszczany na początku deklaracji przestrzeni nazw, która otacza zawartość *biblioteki typów* w pliku nagłówkowym.

**ZAKOŃCZENIE specyficzne dla języka C++**

## <a name="see-also"></a>Zobacz też

[Atrybuty #import](../preprocessor/hash-import-attributes-cpp.md)\
[#import — dyrektywa](../preprocessor/hash-import-directive-cpp.md)
