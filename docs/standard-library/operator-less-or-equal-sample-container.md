---
title: operator&lt;= (&lt;przykładowy kontener&gt;) | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- std::<=
- std.operator<=
- operator<=
- std.<=
- std::operator<=
- <=
dev_langs:
- C++
helpviewer_keywords:
- operator<=
- operator <=
- <= operator, with specific objects
- <= operator
ms.assetid: 338577dd-dc88-4a2b-9e12-0379c54fc8a2
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a936d2b867bda18867e00fedc0f2db50e39f582a
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/26/2018
---
# <a name="operatorlt-ltsample-containergt"></a>operator&lt;= (&lt;przykładowy kontener&gt;)

> [!NOTE]
> Ten temat dotyczy w dokumentacji Visual C++ prawidłowo przykład kontenerów używanych w standardowej bibliotece C++. Aby uzyskać więcej informacji, zobacz [standardowe kontenery biblioteki C++](../standard-library/stl-containers.md).

Overloads **operator < =** do porównywania dwóch obiektów klasy szablonu [kontenera](../standard-library/sample-container-class.md).

## <a name="syntax"></a>Składnia

```cpp
template <class Ty>
bool operator<=(
    const Container <Ty>& left,
    const Container <Ty>& right);
```

## <a name="return-value"></a>Wartość zwracana

Zwraca `!(right < left)`.

## <a name="see-also"></a>Zobacz także

[\<Przykładowy kontener >](../standard-library/sample-container.md)<br/>
