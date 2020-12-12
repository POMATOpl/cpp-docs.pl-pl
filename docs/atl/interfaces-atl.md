---
description: Dowiedz się więcej na temat interfejsów (ATL)
title: Interfejsy (ATL)
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- COM interfaces
- interfaces, COM
ms.assetid: de6c8b12-6230-4fdc-af66-a28b91d5ee55
ms.openlocfilehash: d68f482d05ff828631f5f9f27085f24af188d643
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97147696"
---
# <a name="interfaces-atl"></a>Interfejsy (ATL)

Interfejs to sposób, w jaki obiekt uwidacznia swoją funkcjonalność na świecie zewnętrznym. W modelu COM interfejs jest tabelą wskaźników (na przykład tablicą tablicami C++) do funkcji implementowanych przez obiekt. Tabela reprezentuje interfejs, a funkcje, do których wskazuje, są metodami tego interfejsu. Obiekt może uwidaczniać dowolną liczbę interfejsów.

Każdy interfejs jest oparty na podstawowym interfejsie COM, [IUnknown](../atl/iunknown.md). Metody `IUnknown` zezwalania na nawigację do innych interfejsów uwidocznionych przez obiekt.

Ponadto każdy interfejs ma unikatowy identyfikator interfejsu (IID). Ta unikatowość ułatwia obsługę wersji interfejsu. Nowa wersja interfejsu jest po prostu nowym interfejsem z nowym identyfikatorem IID.

> [!NOTE]
> IID dla standardowych interfejsów COM i OLE są wstępnie zdefiniowane.

## <a name="see-also"></a>Zobacz też

[Wprowadzenie do modelu COM](../atl/introduction-to-com.md)<br/>
[Obiekty COM i interfejsy](/windows/win32/com/com-objects-and-interfaces)
