---
description: 'Dowiedz się więcej o: Obsługa modelu COM+ 1,0 w projektach ATL'
title: Obsługa modelu COM+ 1,0 w projektach ATL
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.ATL.MTS
helpviewer_keywords:
- ATL projects, COM+ 1.0 support
ms.assetid: 51fb08ac-d632-4657-a4e0-d3f989f0b6f8
ms.openlocfilehash: 8e196bccf25667da28532248765e47906fdcee97
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141287"
---
# <a name="com-10-support-in-atl-projects"></a>Obsługa modelu COM+ 1,0 w projektach ATL

Za pomocą [Kreatora projektu ATL](../../atl/reference/creating-an-atl-project.md) można utworzyć projekt z podstawową obsługą składników COM+ 1,0.

Model COM+ 1,0 jest przeznaczony do tworzenia rozproszonych aplikacji opartych na składnikach. Zapewnia również infrastrukturę wykonawczą do wdrażania tych aplikacji i zarządzania nimi.

W przypadku zaznaczenia pola wyboru **Obsługuj model COM+ 1,0** Kreator modyfikuje skrypt kompilacji w kroku link. W przypadku projektu COM+ 1,0 linki do następujących bibliotek:

- Comsvcs. lib

- Mtxguid. lib

W przypadku zaznaczenia pola wyboru **Obsługuj model COM+ 1,0** można także wybrać pozycję **Obsługa rejestratora składników**. Rejestrator składnika umożliwia obiektowi modelu COM+ 1,0 uzyskanie listy składników, rejestrowanie składników lub Wyrejestrowywanie składników (pojedynczo lub wszystkie jednocześnie).

## <a name="see-also"></a>Zobacz też

[Podstawowe informacje o obiektach COM ATL](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[Programowanie za pomocą kodu ATL i języka C Run-Time](../../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[Domyślne konfiguracje projektu ATL](../../atl/reference/default-atl-project-configurations.md)
