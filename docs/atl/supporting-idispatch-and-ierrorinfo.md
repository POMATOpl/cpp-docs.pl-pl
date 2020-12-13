---
description: Dowiedz się więcej na temat obsługi elementu IDispatch i IErrorInfo
title: Obsługa interfejsów IDispatch i IErrorInfo
ms.date: 11/04/2016
helpviewer_keywords:
- ISupportErrorInfoImpl method
- IErrorInfo class suppor in ATL
- IDispatchImpl class
- IDispatch class support in ATL
ms.assetid: 7db2220f-319d-4ce9-9382-d340019f14f7
ms.openlocfilehash: 4622c8811fafc9512400345e5876dd24c466bc93
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138453"
---
# <a name="supporting-idispatch-and-ierrorinfo"></a>Obsługa interfejsów IDispatch i IErrorInfo

Można użyć klasy szablonu [IDispatchImpl](../atl/reference/idispatchimpl-class.md) , aby zapewnić domyślną implementację `IDispatch Interface` części każdego podwójnego interfejsu w obiekcie.

Jeśli obiekt używa `IErrorInfo` interfejsu do raportowania błędów z powrotem do klienta, obiekt musi obsługiwać `ISupportErrorInfo Interface` interfejs. Klasa szablonu [ISupportErrorInfoImpl](../atl/reference/isupporterrorinfoimpl-class.md) zapewnia łatwy sposób wdrożenia tego elementu, jeśli masz tylko jeden interfejs generujący błędy w obiekcie.

## <a name="see-also"></a>Zobacz też

[Podstawowe informacje o obiektach COM ATL](../atl/fundamentals-of-atl-com-objects.md)
