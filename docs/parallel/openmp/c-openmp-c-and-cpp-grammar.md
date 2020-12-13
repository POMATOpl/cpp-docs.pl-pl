---
description: 'Dowiedz się więcej na temat: C. OpenMP C i gramatyki C++'
title: C. OpenMP C i gramatyka C++
ms.date: 01/16/2019
ms.assetid: 97a878ce-1533-47f7-a134-66fcbff48524
ms.openlocfilehash: 9543d721afbff1069b5497ba8dc7092089a1b706
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342507"
---
# <a name="c-openmp-c-and-c-grammar"></a>C. OpenMP C i gramatyka C++

[C.1 Notacja](#c1-notation)<br/>
[C.2 Reguły](#c2-rules)

## <a name="c1-notation"></a>C.1 Notacja

Reguły gramatyki składają się z nazwy, która nie jest terminalem, po którym następuje dwukropek, a następnie zamian zamiennych w osobnych wierszach.

Wyrażenie wyrażenia "<sub>opt</sub> " oznacza, że termin jest opcjonalny w zamian.

Termin wyrażenie składni <sub>optseq</sub> jest odpowiednikiem *warunku-SEQ*<sub>opt</sub> z następującymi dodatkowymi regułami:

*termin — SEQ*:  
&nbsp;&nbsp;&nbsp;&nbsp;*mandat*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*termin —* *termin* SEQ<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*termin — SEQ* `,` *termin*   

## <a name="c2-rules"></a>C.2 Reguły

Notacja jest opisana w sekcji 6,1 standardu C. Ten dodatek do gramatyki pokazuje rozszerzenia gramatyki języka podstawowego dla dyrektyw OpenMP C i C++.

**/\* w języku C++ (ISO/IEC 14882:1998) \*/**

*instrukcja-SEQ*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Merge*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*OpenMP — dyrektywa*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Instrukcja-SEQ — instrukcja*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Instrukcja-SEQ OpenMP — dyrektywa*

**/\* w C90 (ISO/IEC 9899:1990) \*/**

*Lista instrukcji*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Merge*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*OpenMP — dyrektywa*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Instrukcja-list — instrukcja*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Instrukcja OpenMP-dyrektywa*

**/\* w C99 (ISO/IEC 9899:1999) \*/**

*element bloku*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*oświadczeń*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Merge*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*OpenMP — dyrektywa*

**/\* standardowe instrukcje \*/**

*instrukcja*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*OpenMP — konstrukcja*

*konstrukcja OpenMP*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*równoległa konstrukcja*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*dla-konstrukcja*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sekcje-konstrukcja*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Pojedyncza konstrukcja*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Parallel-for-konstrukcja*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*równoległe sekcje-konstrukcja*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*wzorzec — konstrukcja*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Konstrukcja krytyczna*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*konstrukcja niepodzielna*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*uporządkowane — konstrukcja*

*OpenMP — dyrektywa*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bariera — dyrektywa*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Flush — dyrektywa*

*blok strukturalny*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Merge*

*równoległa konstrukcja*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*równoległa — dyrektywa strukturalna — blok*

*równoległa dyrektywa*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp parallel`*równoległa klauzula*<sub>optseq</sub> *New-line*

*klauzula równoległa*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*unikatowa — równoległa klauzula*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*klauzula danych*

*unikatowa klauzula-Parallel-*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `if (`*wyrażenie*   `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `num_threads (`*wyrażenie*   `)`

*dla-konstrukcja*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Instrukcja iteracji for dyrektywy*

*dla dyrektywy*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp for`*klauzula for-*<sub>optseq</sub> *New-line*

*klauzula for*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*unikatowa klauzula for*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*klauzula danych*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `nowait`

*unikatowa klauzula-for-*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `ordered`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `schedule (`*rodzaj harmonogramu*   `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `schedule (`*rodzaj harmonogramu* `,` *wyrażenie*      `)`

*Typ harmonogramu*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `static`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `dynamic`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `guided`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `runtime`

*sekcje-konstrukcja*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sekcje — sekcja dyrektywy-Scope*

*sekcje — dyrektywa*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp sections`sections *— klauzula*<sub>optseq</sub> *New-line*

*sekcje — klauzula*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*klauzula danych*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `nowait`

*zakres sekcji*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*{Sekcja-Sequence}*

*sekwencja sekcji*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sekcja —*<sub>wybór</sub> dyrektywy *— blok strukturalny*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Sekcja-sekwencja sekcji-dyrektywa — blok strukturalny*

*sekcja — dyrektywa*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp section`*nowy wiersz*

*Pojedyncza konstrukcja*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*blok strukturalny o pojedynczej dyrektywie*

*Pojedyncza dyrektywa*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp single`*Pojedyncza klauzula*<sub>optseq</sub> *New-line*

*Pojedyncza klauzula*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*klauzula danych*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `nowait`

*równoległe dla konstrukcji*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*iteracja równoległa dla dyrektywy — instrukcja*

*równoległe dla dyrektywy*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp parallel for`*równoległa klauzula*<sub>optseq</sub> *New-line*

*równoległa klauzula*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*unikatowa — równoległa klauzula*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*unikatowa klauzula for*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*klauzula danych*

*równoległe sekcje-konstrukcja*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Sekcja równoległa-sekcja dyrektywy — zakres*

*równoległe sekcje-dyrektywa*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp parallel sections`*równoległe sekcje-klauzule*<sub>optseq</sub> *New-line*

*klauzula Parallel-* sections:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*unikatowa — równoległa klauzula*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*klauzula danych*

*konstrukcja główna*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Master — struktura strukturalna — blok*

*wzorzec — dyrektywa*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp master`*nowy wiersz*

*konstrukcja krytyczna*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*krytyczna — dyrektywa strukturalna — blok*

*krytyczna — dyrektywa*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp critical`*wybór regionu —*<sub></sub> *Nowa linia*

*region — fraza*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*identyfikatora*

*bariera — dyrektywa*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp barrier`*nowy wiersz*

*konstrukcje niepodzielne*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*wyrażenie atomowe dyrektywy-Statement*

*niepodzielna dyrektywa*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp atomic`*nowy wiersz*

*opróżnianie dyrektywy*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp flush`*Flush-zmiennych*<sub>opt</sub> *New-line*

*zmiennych opróżniania*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*(lista zmiennych)*

*uporządkowane — konstrukcja*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*uporządkowana — dyrektywa — blok strukturalny*

*uporządkowane — dyrektywa*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp ordered`*nowy wiersz*

**/\* deklaracje standardowe \*/**

*Deklaracja*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*threadprivate — dyrektywa*

*threadprivate — dyrektywa*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp threadprivate (`*lista zmiennych* `)` *nowy wiersz*    

*klauzula danych*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `private (`*lista zmiennych*   `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `copyprivate (`  *Lista zmiennych*    `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `firstprivate (`  *Lista zmiennych*    `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `lastprivate (`*lista zmiennych*    `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `shared (`*lista zmiennych*   `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `default ( shared )`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `default ( none )`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `reduction (`  *redukcja — operator* `:` *lista zmiennych*          `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `copyin (`  *Lista zmiennych*    `)`

*redukcja — operator*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;Jeden z:   `+ \* - & ^ | && ||`

**/\* w języku C \*/**

*lista zmiennych*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*identyfikatora*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*lista zmiennych* `,` *Identyfikator*   

**/\* w języku C++ \*/**

*lista zmiennych*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*wyrażenie identyfikatora*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*lista zmiennych* `,` *wyrażenie identyfikatora*   
