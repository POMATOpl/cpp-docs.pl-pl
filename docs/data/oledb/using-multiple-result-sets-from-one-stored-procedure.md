---
description: 'Dowiedz się więcej o programie: używanie wielu zestawów wyników z jednej procedury składowanej'
title: Używanie wielu zestawów wyników z jednej procedury składowanej
ms.date: 10/24/2018
helpviewer_keywords:
- stored procedures, returning result sets
- multiple result sets
ms.assetid: c450c12c-a76c-4ae4-9675-071a41eeac05
ms.openlocfilehash: 8e6b7a51635caf9ddfd86dddcad0e2a3f94bb7dd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319121"
---
# <a name="using-multiple-result-sets-from-one-stored-procedure"></a>Używanie wielu zestawów wyników z jednej procedury składowanej

Większość procedur składowanych zwraca wiele zestawów wyników. Taka procedura składowana zwykle zawiera jedną lub więcej instrukcji SELECT. Konsument musi wziąć pod uwagę ten dołączenie, aby obsłużyć wszystkie zestawy wyników.

## <a name="to-handle-multiple-result-sets"></a>Aby obsłużyć wiele zestawów wyników

1. Utwórz `CCommand` klasę z `CMultipleResults` jako argumentem szablonu i z metodą dodającą się do wyboru, zazwyczaj akcesorem dynamicznym lub ręcznym. Jeśli używasz innego typu metody dostępu, możesz nie być w stanie określić kolumn wyjściowych dla każdego zestawu wierszy.

1. Wykonaj procedurę składowaną w zwykły sposób i powiąż kolumny (zobacz [jak pobrać dane?](../../data/oledb/fetching-data.md)).

1. Użyj danych.

1. Wywołanie `GetNextResult` `CCommand` klasy. Jeśli jest dostępny inny zestaw wierszy wyników, `GetNextResult` zwraca S_OK i należy ponownie powiązać kolumny, jeśli używasz ręcznego dostępu. Jeśli `GetNextResult` zwraca błąd, nie ma dalszych dostępnych zestawów wyników.

## <a name="see-also"></a>Zobacz też

[Korzystanie z procedur składowanych](../../data/oledb/using-stored-procedures.md)
