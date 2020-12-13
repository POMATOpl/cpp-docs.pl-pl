---
description: 'Dowiedz się więcej o: IUnknown'
title: IUnknown
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- COM interfaces, base interface
- IUnknown interface
ms.assetid: e6b85472-e54b-4b8c-b19f-4454d6c05a8f
ms.openlocfilehash: ddfd35155162275885a1c0c842b4589fa6773a4a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152649"
---
# <a name="iunknown"></a>IUnknown

[IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) jest interfejsem podstawowym każdego innego interfejsu com.  Ten interfejs definiuje trzy metody: [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)), [AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref)i [Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release). Funkcja [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) umożliwia użytkownikowi interfejsu poproszenie obiektu o wskaźnik do innego interfejsu. [AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref) i [wydanie](/windows/win32/api/unknwn/nf-unknwn-iunknown-release) Implementuj zliczanie odwołań w interfejsie.

## <a name="see-also"></a>Zobacz też

[Wprowadzenie do modelu COM](../atl/introduction-to-com.md)<br/>
[Interfejs IUnknown i dziedziczenie interfejsu](/windows/win32/com/iunknown-and-interface-inheritance)
