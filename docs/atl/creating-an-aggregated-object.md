---
description: 'Dowiedz się więcej o: tworzeniu zagregowanego obiektu'
title: Tworzenie zagregowanego obiektu
ms.date: 11/04/2016
helpviewer_keywords:
- aggregation [C++], creating aggregated objects
- aggregate objects [C++], creating
ms.assetid: fc29d7aa-fd53-4276-9c2f-37379f71b179
ms.openlocfilehash: e6efbf63e28d0477730a2d7c31ec91e9b75520e4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97153229"
---
# <a name="creating-an-aggregated-object"></a>Tworzenie zagregowanego obiektu

Wywołania delegatów agregacji `IUnknown` , dostarczając wskaźnik do obiektu zewnętrznego w obiekcie `IUnknown` wewnętrznym.

## <a name="to-create-an-aggregated-object"></a>Aby utworzyć zagregowany obiekt

1. Dodaj `IUnknown` wskaźnik do obiektu klasy i zainicjuj go do wartości null w konstruktorze.

1. Zastąp [FinalConstruct](../atl/reference/ccomobjectrootex-class.md#finalconstruct) , aby utworzyć agregację.

1. Użyj `IUnknown` wskaźnika zdefiniowanego w kroku 1 jako drugi parametr dla makr [COM_INTERFACE_ENTRY_AGGREGATE](reference/com-interface-entry-macros.md#com_interface_entry_aggregate) .

1. Przesłoń [FinalRelease](../atl/reference/ccomobjectrootex-class.md#finalrelease) , aby zwolnić `IUnknown` wskaźnik.

> [!NOTE]
> Jeśli używasz i zwolnisz interfejs z zagregowanego obiektu podczas `FinalConstruct` , należy dodać makro [DECLARE_PROTECT_FINAL_CONSTRUCT](reference/aggregation-and-class-factory-macros.md#declare_protect_final_construct) do definicji obiektu klasy.

## <a name="see-also"></a>Zobacz też

[Podstawowe informacje o obiektach COM ATL](../atl/fundamentals-of-atl-com-objects.md)
