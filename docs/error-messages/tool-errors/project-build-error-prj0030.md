---
description: 'Dowiedz się więcej na temat: błąd kompilacji projektu PRJ0030'
title: Błąd PRJ0030 kompilacji projektu
ms.date: 11/04/2016
f1_keywords:
- PRJ0030
helpviewer_keywords:
- PRJ0030
ms.assetid: c48b3727-e166-46e7-bcd7-3e5b2ac5c1d4
ms.openlocfilehash: a8fdb99e7444383f3634730b3053b00b81661aed
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97160288"
---
# <a name="project-build-error-prj0030"></a>Błąd PRJ0030 kompilacji projektu

Błąd rozwinięcia makra. Obliczanie rekursji przekroczyło 32 poziomów dla $ (makro).

Ten błąd jest spowodowany przez rekursję w makrach. Na przykład jeśli ustawisz właściwość **katalogu pośredniego** (patrz [ogólna Strona właściwości (projekt)](../../build/reference/general-property-page-project.md)) do $ (IntDir), będziesz mieć rekursję.

Aby rozwiązać ten problem, nie należy definiować makr ani właściwości w warunkach makr, które są używane do definiowania.
