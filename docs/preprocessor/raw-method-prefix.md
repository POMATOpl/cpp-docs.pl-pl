---
description: 'Dowiedz się więcej na temat: raw_method_prefix'
title: raw_method_prefix
ms.date: 08/29/2019
f1_keywords:
- raw_method_prefix
helpviewer_keywords:
- raw_method_prefix attribute
ms.assetid: 71490313-af78-4bb2-b28a-eee67950d30b
ms.openlocfilehash: 9e05f70814e48a4460287e96905b543f7d76dde6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201992"
---
# <a name="raw_method_prefix"></a>raw_method_prefix

**Specyficzne dla języka C++**

Określa inny prefiks, aby uniknąć kolizji nazw.

## <a name="syntax"></a>Składnia

> **#import** raw_method_prefix *biblioteki typów* **(** "*prefiks*" **)**

### <a name="parameters"></a>Parametry

*Prefiks*\
Prefiks, który ma być używany.

## <a name="remarks"></a>Uwagi

Właściwości i metody niskiego poziomu są uwidaczniane przez funkcje Członkowskie o nazwie przy użyciu domyślnego prefiksu **raw_**, aby uniknąć kolizji nazw z funkcjami członkowskimi obsługi błędów wysokiego poziomu.

> [!NOTE]
> Skutki atrybutu **raw_method_prefix** są niezmienione przez obecność atrybutu [raw_interfaces_only](raw-interfaces-only.md) . **Raw_method_prefix** zawsze ma pierwszeństwo przed `raw_interfaces_only` określeniem prefiksu. Jeśli oba atrybuty są używane w tej samej `#import` instrukcji, zostanie użyty prefiks określony przez atrybut **raw_method_prefix** .

**ZAKOŃCZENIE specyficzne dla języka C++**

## <a name="see-also"></a>Zobacz też

[Atrybuty #import](../preprocessor/hash-import-attributes-cpp.md)\
[#import — dyrektywa](../preprocessor/hash-import-directive-cpp.md)
