---
title: データ変換 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- maps, data translation
- data translation, about data translation
- data transformation, about data transformation
- maps, data transformation
- data transformation, maps
- data translation, maps
ms.assetid: a6aa5e9a-8d9c-478d-8f69-f9b16ed1a18c
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4366e37d206902ec3aff5e016c02c4bd721da5b6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015956"
---
# <a name="data-transformation"></a>[データの変換]
データのマッピングは、データのトランスフォームによって異なります。  
  
 トランスフォームは、送信元スキーマと送信先スキーマ間のさまざまなレコードやフィールドについて、両者の対応関係を作成するプロセスです。 たとえば、注文書に含まれる出荷先や請求先の住所情報を請求書にマッピングする場合にトランスフォームが使用されます。 これは、最も基本的なタイプのマッピングです。 トランスフォームは、次のような操作に適用することもできます。  
  
- ループ レコードから平均データを割り出し、その出力を送信先スキーマの単一フィールドに送る。  
  
- 文字データを ASCII 形式に変換する。  
  
- 1 つまたは複数のレコードに対して加算または減算を適用し、その結果を送信先スキーマの単一フィールドに出力する。  
  
  データを 1 つの形式から別の形式に変換する場合は、パイプラインを使用します。 パイプラインは、エンタープライズ アプリケーション統合の問題を解決するために、特定の種類のメッセージを、既存のシステムで利用可能な別の形式に変換する必要があり、マップではそれを行うことができない場合に役に立ちます。  
  
## <a name="see-also"></a>参照  
 [マップ](../core/maps.md)   
 [BizTalk マッパーを使用してマップを作成します。](../core/creating-maps-using-biztalk-mapper.md)