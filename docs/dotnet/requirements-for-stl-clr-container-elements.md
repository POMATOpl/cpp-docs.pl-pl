---
description: 'Dowiedz się więcej o: wymagania dotyczące elementów kontenera STL/CLR'
title: Wymagania dotyczące elementów kontenera STL/CLR
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- C++ Standard Library, template class containers
- STL/CLR, containers
- containers, STL/CLR
- containers, C++ Standard Library
ms.assetid: 59ab240c-15bf-4701-a9f9-e7c56e5ab53f
ms.openlocfilehash: 3696d9df40f69b1dd39205a2dc7a3b802e815841
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97305510"
---
# <a name="requirements-for-stlclr-container-elements"></a>Wymagania dotyczące elementów kontenera STL/CLR

Wszystkie typy odwołań, które są wstawiane do kontenerów STL/CLR, muszą mieć co najmniej następujące elementy:

- Publiczny Konstruktor kopiujący.

- Publiczny operator przypisania.

- Publiczny destruktor.

Ponadto Kontenery asocjacyjne, takie jak [Set](../dotnet/set-stl-clr.md) i [map](../dotnet/map-stl-clr.md) , muszą mieć zdefiniowany publiczny operator porównania, który jest `operator<` domyślnie. Niektóre operacje na kontenerach mogą również wymagać publicznego konstruktora domyślnego i publicznego operatora równoważności do zdefiniowania.

Podobnie jak typy odwołań, typy wartości i dojścia do typów referencyjnych, które mają zostać wstawione do kontenera asocjacyjnego, muszą mieć operator porównania, taki jak `operator<` zdefiniowany. Wymagania dotyczące publicznego konstruktora kopiującego, operatora przypisania publicznego i destruktora publicznego nie istnieją dla typów wartości lub dojść do typów referencyjnych.

## <a name="see-also"></a>Zobacz też

[Dokumentacja standardowej biblioteki języka C++](../standard-library/cpp-standard-library-reference.md)
