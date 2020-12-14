---
description: 'Dowiedz się więcej o: konwersje z typów zmiennoprzecinkowych'
title: Konwersje z typów zmiennoprzecinkowych
ms.date: 10/02/2019
helpviewer_keywords:
- converting floating point
- floating-point conversion
ms.assetid: 96804c8e-fa3b-4742-9006-0082ed9e57f2
ms.openlocfilehash: 2e2a78a68b39d9109a2304d78070bddef36e9b52
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97293238"
---
# <a name="conversions-from-floating-point-types"></a>Konwersje z typów zmiennoprzecinkowych

Wartość zmiennoprzecinkowa, która jest konwertowana na inny typ zmiennoprzecinkowy, nie zmienia wartości, jeśli oryginalna wartość zostanie zaprezentowana dokładnie w typie wynikowym. Jeśli oryginalna wartość jest wartością liczbową, ale nie będzie można jej przedstawić dokładnie, wynikiem jest kolejna lub Następna Dolna wartość. Zobacz [limity dla stałych zmiennoprzecinkowych](../c-language/limits-on-floating-point-constants.md) dla zakresu typów zmiennoprzecinkowych.

Wartość zmiennoprzecinkowa konwertowana na typ całkowity jest najpierw obcinana przez odrzucenie dowolnej wartości ułamkowej. Jeśli ta obcięta wartość będzie reprezentować w typie wyniku, wynik musi być tą wartością. Gdy nie można jej reprezentować, wartość wyniku jest niezdefiniowana.

**Specyficzne dla firmy Microsoft**

Kompilatory firmy Microsoft używają reprezentacji binary32 IEEE-754 dla **`float`** wartości i reprezentacji binary64 dla **`long double`** i **`double`** . Ponieważ **`long double`** i **`double`** używają tej samej reprezentacji, mają one ten sam zakres i precyzję.

Gdy kompilator konwertuje **`double`** **`long double`** liczbę zmiennoprzecinkową na a **`float`** , zaokrągla wynik zgodnie z kontrolkami środowisk zmiennoprzecinkowych, które domyślnie są "zaokrąglone do najbliższe, powiązania z parzystością". Jeśli wartość liczbowa jest zbyt duża lub zbyt niska, aby mogła być reprezentowana jako wartość liczbowa **`float`** , wynik konwersji jest dodatnią lub ujemną nieskończoność zgodnie ze znakiem oryginalnej wartości i zostanie zgłoszony wyjątek przepełnienia, jeśli jest włączony.

Podczas konwertowania na typy całkowite, wynik konwersji na typ mniejszy niż **`long`** jest wynikiem konwersji wartości na **`long`** , a następnie przekonwertowania na typ wyniku.

Dla konwersji na typy całkowite co najmniej tak duże jak **`long`** , konwersja wartości, która jest zbyt duża lub zbyt niska do reprezentowania w typie wynikowym, może zwracać jedną z następujących wartości:

- Wynik może być *wartością wskaźnikową*, która jest reprezentacją z wartości od zera. W przypadku podpisanych typów jest to najniższa wartość reprezentacja (0x800... 0). W przypadku typów bez znaku jest to najwyższa reprezentacja wartości (0xFF... F).

- Wyniki mogą być *nasycone*, gdzie wartości zbyt wysokie do reprezentowania są konwertowane na największą reprezentację wartości, a wartości zbyt niskie do reprezentowania są konwertowane na najniższą reprezentację wartości. Jedna z tych dwóch wartości jest również używana jako wartość wskaźnikowa.

- W przypadku konwersji na **`unsigned long`** lub **`unsigned long long`** , wynik konwersji wartości poza zakresem może być wartością inną niż najwyższa lub najniższa wartość, którą można reprezentować. Określa, czy wynik jest wartością wskaźnikową, czy niezależną od opcji kompilatora i architektury docelowej. Przyszłe wydania kompilatora mogą zwrócić wartość nasyconej lub wskaźnikowej.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

W poniższej tabeli zestawiono konwersje z typów zmiennoprzecinkowych.

## <a name="table-of-conversions-from-floating-point-types"></a>Tabela konwersji z typów zmiennoprzecinkowych

|Źródło|Działanie|Metoda|
|----------|--------|------------|
|**`float`**|**`char`**|Konwertuj na **`long`** ; Konwertuj **`long`** na **`char`**|
|**`float`**|**`short`**|Konwertuj na **`long`** ; Konwertuj **`long`** na **`short`**|
|**`float`**|**`int`**|Obetnij w punkcie dziesiętnym. Jeśli wynik jest zbyt duży do reprezentowania jako **`int`** , wynik jest niezdefiniowany.|
|**`float`**|**`long`**|Obetnij w punkcie dziesiętnym. Jeśli wynik jest zbyt duży do reprezentowania jako **`long`** , wynik jest niezdefiniowany.|
|**`float`**|**`long long`**|Obetnij w punkcie dziesiętnym. Jeśli wynik jest zbyt duży do reprezentowania jako **`long long`** , wynik jest niezdefiniowany.|
|**`float`**|**`unsigned char`**|Konwertuj na **`long`** ; Konwertuj **`long`** na **`unsigned char`**|
|**`float`**|**`unsigned short`**|Konwertuj na **`long`** ; Konwertuj **`long`** na **`unsigned short`**|
|**`float`**|**`unsigned`**|Obetnij w punkcie dziesiętnym. Jeśli wynik jest zbyt duży do reprezentowania jako **`unsigned`** , wynik jest niezdefiniowany.|
|**`float`**|**`unsigned long`**|Obetnij w punkcie dziesiętnym. Jeśli wynik jest zbyt duży do reprezentowania jako **`unsigned long`** , wynik jest niezdefiniowany.|
|**`float`**|**`unsigned long long`**|Obetnij w punkcie dziesiętnym. Jeśli wynik jest zbyt duży do reprezentowania jako **`unsigned long long`** , wynik jest niezdefiniowany.|
|**`float`**|**`double`**|Reprezentuje jako **`double`** .|
|**`float`**|**`long double`**|Reprezentuje jako **`long double`** .|
|**`double`**|**`char`**|Konwertuj na **`float`** ; Konwertuj **`float`** na **`char`**|
|**`double`**|**`short`**|Konwertuj na **`float`** ; Konwertuj **`float`** na **`short`**|
|**`double`**|**`int`**|Obetnij w punkcie dziesiętnym. Jeśli wynik jest zbyt duży do reprezentowania jako **`int`** , wynik jest niezdefiniowany.|
|**`double`**|**`long`**|Obetnij w punkcie dziesiętnym. Jeśli wynik jest zbyt duży do reprezentowania jako **`long`** , wynik jest niezdefiniowany.|
|**`double`**|**`unsigned char`**|Konwertuj na **`long`** ; Konwertuj **`long`** na **`unsigned char`**|
|**`double`**|**`unsigned short`**|Konwertuj na **`long`** ; Konwertuj **`long`** na **`unsigned short`**|
|**`double`**|**`unsigned`**|Obetnij w punkcie dziesiętnym. Jeśli wynik jest zbyt duży do reprezentowania jako **`unsigned`** , wynik jest niezdefiniowany.|
|**`double`**|**`unsigned long`**|Obetnij w punkcie dziesiętnym. Jeśli wynik jest zbyt duży do reprezentowania jako **`unsigned long`** , wynik jest niezdefiniowany.|
|**`double`**|**`unsigned long long`**|Obetnij w punkcie dziesiętnym. Jeśli wynik jest zbyt duży do reprezentowania jako **`unsigned long long`** , wynik jest niezdefiniowany.|
|**`double`**|**`float`**|Reprezentuje jako **`float`** . Jeśli **`double`** wartość nie może być reprezentowana dokładnie jako **`float`** , wystąpi spadek dokładności. Jeśli wartość jest zbyt duża, aby była reprezentowana jako **`float`** , wynik jest niezdefiniowany.|
|**`double`**|**`long double`**|**`long double`** Wartość jest traktowana jako **`double`** .|

Konwersje z **`long double`** metody są takie same jak konwersje z **`double`** .

## <a name="see-also"></a>Zobacz też

[Konwersje przypisań](../c-language/assignment-conversions.md)
