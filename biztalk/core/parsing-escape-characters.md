---
title: エスケープ文字の解析 |Microsoft ドキュメント
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
ms.openlocfilehash: f200e7c68a43360dc9edbae42ebea196b884f577
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25971976"
---
# <a name="parsing-escape-characters"></a>エスケープ文字の解析
パーサーは通常の文字 (区切り文字以外またはその他の特殊文字以外の文字) の前に付加されたエスケープ文字を見つけると、そのエスケープ文字を無視します。 たとえば、文字列を指定して"abc \d"、"\\"エスケープ文字は、出力は"abcd"です。  
  
 パーサーには、ダブル エスケープ文字が検出された場合 (たとえば、"abc\\\d")、出力には、1 つのエスケープ文字 ("abc \d") が含まれています。  
  
 パーサーが次の 3 つのエスケープ文字を検出する場合 (たとえば、abc\\\\\d)、最初の 2 つのエスケープ文字を解析しているために、出力は"abc \d""\\"と 3 番目のエスケープ文字は無視されます。  
  
 パーサーは、間違った位置にある区切り文字を通常の文字として扱います。 たとえば、"Record, Field1, Field, 2"を受信する場合、出力 XML は\<Field1\> \<Field, 2\>です。  
  
## <a name="see-also"></a>参照  
 [フラット ファイル解析エンジンの使用](../core/using-the-flat-file-parsing-engine.md)