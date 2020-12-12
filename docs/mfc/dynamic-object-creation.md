---
description: 'Dowiedz się więcej na temat: dynamiczne tworzenie obiektów'
title: Dynamiczne tworzenie obiektów
ms.date: 03/27/2020
helpviewer_keywords:
- object creation [MFC], dynamically at run time
- CObject class [MFC], dynamic object creation
- objects [MFC], creating dynamically at run time
- dynamic object creation [MFC]
ms.assetid: 3e0f51cb-3e24-4231-817f-1c0ce9f2d5df
ms.openlocfilehash: b39c0561a98807030c471b3de4cd5921883f9f0e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97290976"
---
# <a name="dynamic-object-creation"></a>Dynamiczne tworzenie obiektów

W tym artykule wyjaśniono, jak utworzyć obiekt dynamicznie w czasie wykonywania. Procedura używa informacji o klasie czasu wykonywania, jak opisano w artykule [Uzyskiwanie dostępu do Run-Time informacji o klasie](accessing-run-time-class-information.md).

#### <a name="dynamically-create-an-object-given-its-run-time-class"></a>Dynamicznie Twórz obiekt z określoną klasą czasu wykonywania

1. Użyj poniższego kodu, aby dynamicznie utworzyć obiekt przy użyciu `CreateObject` funkcji `CRuntimeClass` . W przypadku niepowodzenia `CreateObject` zwraca **wartość null** zamiast podnoszenia wyjątku:

   [!code-cpp[NVC_MFCCObjectSample#6](codesnippet/cpp/dynamic-object-creation_1.cpp)]

## <a name="see-also"></a>Zobacz też

[Niszczenie obiektów okien](tn017-destroying-window-objects.md) 
 [Korzystanie z CObject](using-cobject.md)
