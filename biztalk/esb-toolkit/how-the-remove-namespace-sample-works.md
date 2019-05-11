---
title: 削除 Namespace サンプルのしくみ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bf5834b4-e0fd-4180-9d15-4cdd99f0f353
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9fc0c3accdf81322a08562bd186417421c10c50
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279008"
---
# <a name="how-the-remove-namespace-sample-works"></a>削除 Namespace サンプルのしくみ
2 番目と 3 番目のテストを使用して、**削除 Namespace**コンポーネントにある、 **NamespaceSampleSendPipeline**パイプライン。 として、次のよう、ルート ノードの名前空間を持つドキュメントを入力します。  
  
```  
<ns0:CanonicalOrder OrderID="OrderID_0" OrderDate="OrderDate_1"   
    Status="Status_2"   
    xmlns:ns0="http://schemas.microsoft.biztalk.esb.test.com/test">  
```  
  
 **削除 Namespace**コンポーネントは、単にこの名前空間を削除し、次に示すように、ルート ノードの名前空間がないドキュメントを返します。  
  
```  
<CanonicalOrder OrderID="OrderID_0" OrderDate="OrderDate_1" Status="Status_2">  
```