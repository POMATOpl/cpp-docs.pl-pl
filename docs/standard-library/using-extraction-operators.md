---
description: 'Dowiedz się więcej o: korzystanie z operatorów wyodrębniania'
title: Korzystanie z operatorów wyodrębniania
ms.date: 11/04/2016
helpviewer_keywords:
- extraction operators [C++]
- '&gt;&gt; operator [C++], extraction operators'
- operators [C++], extraction
ms.assetid: a961e1a9-4897-41de-b210-89d5b2d051ae
ms.openlocfilehash: 11115ed9d7f83b5e4d8cefe088c638afe8d95f38
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97153580"
---
# <a name="using-extraction-operators"></a>Korzystanie z operatorów wyodrębniania

Operator wyodrębniania ( `>>` ), który jest zaprogramowany dla wszystkich typów danych w języku C++, jest najprostszym sposobem uzyskania bajtów z obiektu strumienia wejściowego.

Operatory wyodrębniania tekstu sformatowanego są zależne od odstępu, aby oddzielić wartości danych przychodzących. Jest to niewygodne, gdy pole tekstowe zawiera wiele słów lub przecinki oddzielające cyfry. W takim przypadku jedną alternatywą jest użycie niesformatowanej wejściowej funkcji członkowskiej [IStream:: getline](../standard-library/basic-istream-class.md#getline) , aby odczytać blok tekstu z dołączonym białym znakiem, a następnie przeanalizować blok przy użyciu funkcji specjalnych. Inna metoda polega na utworzeniu klasy strumienia wejściowego z funkcją składową, taką jak `GetNextToken` , która może wywoływać IStream członków, aby wyodrębnić i sformatować dane znakowe.

## <a name="see-also"></a>Zobacz też

[Strumienie wejściowe](../standard-library/input-streams.md)
