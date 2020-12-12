---
description: Dowiedz się więcej o tym, jak włączać i wyłączać usługi OLE DB
title: Włączanie i wyłączanie usług OLE DB
ms.date: 10/29/2018
helpviewer_keywords:
- OLE DB services [OLE DB], enabling and disabling
- service providers [OLE DB]
ms.assetid: 445f97eb-32a8-41c2-ad26-1169f78a074f
ms.openlocfilehash: a2a3e51b69a0051b6a231d14c18f3b1f416fb547
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97317665"
---
# <a name="enabling-and-disabling-ole-db-services"></a>Włączanie i wyłączanie usług OLE DB

Menedżer składników usługi OLE DB porównuje właściwości określone przez konsumenta z właściwościami obsługiwanymi przez dostawcę w celu określenia, czy poszczególne składniki usługi mogą być używane do zaspokojenia rozszerzonych funkcji zażądanych przez klienta. Na przykład jeśli aplikacja żąda przewijanego kursora, a dostawca obsługuje tylko kursor tylko do przodu, Menedżer składników usług używa składnika usługi aparat kursora klienta w celu zapewnienia możliwości przewijania. Jeśli aplikacja korzysta z rozszerzonych funkcji obsługiwanych domyślnie w zestawie wierszy dostawcy, a aplikacja nie ustawi jawnie właściwości do żądania tej funkcjonalności, funkcjonalność może nie być widoczna w zestawie wierszy zwracanym przez aparat kursora klienta. Aby można było współdziałać, aplikacje powinny zawsze ustawiać właściwości, aby jawnie zażądać rozszerzonych funkcji, gdy jest to konieczne.

W niektórych przypadkach może być konieczne wyłączenie poszczególnych usług OLE DB, aby działały prawidłowo z istniejącymi aplikacjami, które składają się na informacje o charakterystyce dostawcy. Usługi OLE DB umożliwiają wyłączenie poszczególnych usług lub wszystkich usług, w zależności od połączenia lub dla wszystkich aplikacji korzystających z jednego dostawcy.

## <a name="see-also"></a>Zobacz też

[OLE DB pul i usług zasobów](../../data/oledb/ole-db-resource-pooling-and-services.md)
