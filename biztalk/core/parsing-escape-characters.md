---
title: エスケープ文字の解析 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], code samples
- pipeline components [custom], escape characters
- pipeline components [custom], parsing
ms.assetid: 2b33f436-3c29-4ff5-8dfa-26d6591713bc
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f16ddf0225c2b8ebaa1a934955a1a05f45f64ee0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395052"
---
# <a name="parsing-escape-characters"></a>エスケープ文字の解析
パーサーには、プレフィックス (つまり、1 つの区切り記号またはその他の特殊文字はない) 通常の文字をエスケープ文字が検出されると、エスケープ文字は無視されます。 たとえば、指定された文字列"abc \d"を"\\"エスケープ文字では、出力は"abcd"。  
  
 パーサーがエスケープ文字を検出する場合 (たとえば、"abc\\\d")、出力には、1 つのエスケープ文字 ("abc \d") が含まれています。  
  
 パーサーが次の 3 つのエスケープ文字を検出する場合 (たとえば、abc\\\\\d)、最初の 2 つのエスケープ文字を解析しているために、出力は"abc \d""\\"と 3 番目のエスケープ文字は無視されます。  
  
 間違っている区切り記号は、パーサーは、標準の文字として扱います。 たとえば、"Record, Field1, Field, 2"を受信した場合、出力 XML は\<Field1\> \<Field, 2\>します。  
  
## <a name="see-also"></a>参照  
 [フラット ファイル解析エンジンの使用](../core/using-the-flat-file-parsing-engine.md)