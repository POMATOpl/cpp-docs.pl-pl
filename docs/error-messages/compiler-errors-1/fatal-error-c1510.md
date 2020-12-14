---
description: 'Dowiedz się więcej na temat: błąd krytyczny C1510'
title: Błąd krytyczny C1510
ms.date: 04/11/2017
f1_keywords:
- C1510
helpviewer_keywords:
- C1510
ms.assetid: 150c827f-9514-41a9-8d7e-82f820749bcb
ms.openlocfilehash: 3112874f033fdeed4cc4290b2469105a275baed8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97276325"
---
# <a name="fatal-error-c1510"></a>Błąd krytyczny C1510

Nie można otworzyć clui.dll zasobów języka

Kompilator nie może załadować biblioteki DLL zasobów języka.

Istnieją dwie typowe przyczyny tego problemu. W przypadku korzystania z 32-bitowego kompilatora i narzędzi, ten błąd może pojawić się w przypadku dużych projektów, które używają więcej niż 2 GB pamięci podczas łączenia. Możliwym rozwiązaniem w 64-bitowych systemach Windows jest użycie z 64-bitowym kompilatorem natywnym lub krzyżowym oraz narzędzi do generowania kodu. Umożliwia to wykorzystanie większej ilości miejsca dostępnego w pamięci dla aplikacji 64-bitowych. Jeśli musisz użyć 32-bitowego kompilatora, ponieważ Pracujesz w systemie 32-bitowym, w niektórych przypadkach można zwiększyć ilość pamięci dostępnej dla konsolidatora do WŁĄCZONĄ. Aby uzyskać więcej informacji, zobacz [dostrajanie 4-gigabajtowe: bcdedit i Boot.ini](/windows/win32/memory/4-gigabyte-tuning) i polecenie [bcdedit/set IncreaseUserVa](/windows-hardware/drivers/devtest/bcdedit--set) .

Inną typową przyczyną jest uszkodzenie lub niepełna instalacja programu Visual Studio. W takim przypadku ponownie uruchom Instalatora, aby naprawić lub ponownie zainstalować program Visual Studio.
