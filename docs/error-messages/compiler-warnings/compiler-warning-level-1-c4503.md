---
title: Kompilatora (poziom 1) ostrzeżeń C4503 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4503
dev_langs:
- C++
helpviewer_keywords:
- C4503
ms.assetid: 7c5a98ae-5b6d-41d8-b881-12d3ffd5e392
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: adafddff679cbe04cf26a39647760bf595af0bd3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4503"></a>Kompilatora (poziom 1) ostrzeżeń C4503
"identyfikator": przekroczona długość nazwy, dekorowanej nazwa została obcięta  
  
 Nazwa był dłuższy niż limit kompilatora (4096) i została obcięta. Aby uniknąć tego ostrzeżenia i obcinania, Zmniejsz liczbę argumentów lub długość nazwy identyfikatorów używane.  
  
 Jedna sytuacja, w którym to ostrzeżenie zostanie wyświetlone jest Jeśli kod zawiera szablony przeznaczone na szablonach wielokrotnie.  Na przykład mapa mapy (z standardowa biblioteka C++).  W takiej sytuacji można wprowadzić Twoje definicje typów typu (na przykład struktury), który zawiera mapy.  
  
 Jednak możesz nie restrukturyzacji kodu.  Można wydać aplikację, która generuje C4503, ale występują błędy czasu łącza na symbol obcięty, będzie trudno jest określić typ symbolu w dzienniku błędów.  Debugowanie będzie również trudniejsza; Debuger będzie miał difficultly mapowania nazwy symbolu nazwy.  Poprawność programu, jednak nie mają wpływu skróconą nazwę.  
  
 Poniższy przykład generuje C4503:  
  
```  
// C4503.cpp  
// compile with: /W1 /EHsc /c  
// C4503 expected  
#include <string>  
#include <map>  
  
class Field{};  
  
typedef std::map<std::string, Field> Screen;  
typedef std::map<std::string, Screen> WebApp;  
typedef std::map<std::string, WebApp> WebAppTest;  
typedef std::map<std::string, WebAppTest> Hello;  
Hello MyWAT;  
```  
  
 Poniższy przykład przedstawia sposób ponownego zapisywania swój kod, aby rozwiązać C4503:  
  
```  
// C4503b.cpp  
// compile with: /W1 /EHsc /c  
#include <string>  
#include <map>  
  
class Field{};  
struct Screen2 {  
   std::map<std::string, Field> Element;  
};  
  
struct WebApp2 {  
   std::map<std::string, Screen2> Element;  
};  
  
struct WebAppTest2 {  
   std::map<std::string, WebApp2> Element;  
};  
  
struct Hello2 {  
   std::map<std::string, WebAppTest2> Element;  
};  
  
Hello2 MyWAT2;  
```