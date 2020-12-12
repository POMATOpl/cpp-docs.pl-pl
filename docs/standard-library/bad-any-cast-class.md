---
description: Dowiedz się więcej na temat klasy bad_any_cast
title: Klasa bad_any_cast
ms.date: 04/04/2019
f1_keywords:
- any/std::bad_any_cast
- any/std::bad_any_cast::what
helpviewer_keywords:
- any/std::bad_any_cast
- any/std::bad_any_cast::what
ms.openlocfilehash: 5b38405bf1fc826592995df4037c5853e88ad9eb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321630"
---
# <a name="bad_any_cast-class"></a>Klasa bad_any_cast

Obiekty zgłoszone przez nie powiodły się `any_cast` .

## <a name="syntax"></a>Składnia

```cpp
class bad_any_cast
```

### <a name="member-functions"></a>Funkcje członkowskie

|Nazwa|Opis|
|-|-|
|[Whatman](#what)|Zwraca typ.|

## <a name="what"></a><a name="what"></a> Whatman

Zwraca typ.

```cpp
const char* what() const noexcept override;
```
