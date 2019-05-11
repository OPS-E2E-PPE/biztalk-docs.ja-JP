---
title: どの Namespace サンプルは、動作の追加 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c76a90a9-5898-43b3-98af-ff546dd97153
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dccb5aebb19895e05ed424f64b4f2ba431174f6d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397110"
---
# <a name="how-the-add-namespace-sample-works"></a>どの Namespace サンプルは、動作を追加
1、2、および 4 番目のテストを使用して、**追加 Namespace** NamespaceSampleReceivePipeline パイプラインにコンポーネントがあります。 として、次のよう、ルート ノードの名前空間のないドキュメントを入力します。  

```  
<CanonicalOrder OrderID="OrderID_0" OrderDate="OrderDate_1" Status="Status_2">  
```  

 次の表は、プロパティの値の設定、**追加 Namespace**コンポーネント。  


|      プロパティ       |  型   |                          値                           |
|---------------------|---------|----------------------------------------------------------|
| ExtractionNodeXPath | スタティック  |                         (空)                          |
|    NamespaceBase    | スタティック  |    http://schemas.microsoft.biztalk.esb.test.com/test    |
|   NamespacePrefix   | スタティック  |                         esbTest                          |
|      [区切り記号]      | スタティック  |                            /                             |
|       Xpath        | 動的 | /CanonicalOrder/@OrderID&#124;/CanonicalOrder/@OrderDate |

 表に示したプロパティの設定により、2 つの XPath クエリを実行することによって、XML ドキュメントを検索するコンポーネント/CanonicalOrder/@OrderIDと/CanonicalOrder/@OrderDate(指定された 2 つのクエリ、 **Xpath** 「パイプ」で区切られたプロパティ文字)。 これらのクエリの値を返す、 **OrderID**と**OrderDate**属性は、ドキュメントのこの例では、ルート ノードの 2 つの値は、"OrderID_0"および"OrderDate_1"。  

 コンポーネントでは、新しいルート名前空間を作成するのにこれらの値とその他のプロパティの値を使用します。 組み合わされています、 **NamespaceBase**、 **NamespacePrefix**、**区切り**、および次の形式では、2 つの XPath クエリから値。  

```  
xmlns:{NamespacePrefix}="{NamespaceBase}{Separator}{XPaths[1]}{Seperator}  
                         {XPaths[2]}{Separator}...{XPaths[n]}"  
```  

 次のように、新しい名前空間が生成されます。  

```  
xmlns:esbTest="http://schemas.microsoft.biztalk.esb.test.com/test  
               /OrderID_0/OrderDate_1"  
```  

 処理後にそのため、更新されたドキュメント、 **NamespaceSampleReceivePipeline**パイプラインは、次。  

```  
<esbTest:CanonicalOrder xmlns:esbTest=  
    "http://schemas.microsoft.biztalk.esb.test.com/test/OrderID_0  
    /OrderDate_1" OrderID="OrderID_0" OrderDate="OrderDate_1"   
    Status="Status_2">  
```  

## <a name="using-the-extractionnodexpath-property"></a>ExtractionNodeXPath プロパティを使用します。  
 既定で、**追加 Namespace**名前空間とプレフィックスの情報を追加するときに、コンポーネントがメッセージ内の XML ドキュメントのルート要素を使用します。 設定することができます (エンベロープの特定のシナリオで、または受信ドキュメントの一部のみに関連性がある場合に便利です)、メッセージ本文として XML ドキュメントのサブセットのみを使用する場合、 **ExtractionNodeXPath**プロパティ、を強制するには**追加 Namespace**結果メッセージとして使用するための指定した要素を検索するコンポーネント。 たとえば、受信 CanonicalOrder メッセージを 1 つだけ持つことがわかっている場合**OrderDetails**はそれに含まれるこのメッセージのコンシューマーに関連する要素を設定できます、 **ExtractionNodeXPath**へのパスを指定するプロパティ、 **OrderDetails**要素。 前に説明したパススルー テストに追加を使用して抽出では、このプロセスの例を見ることができます。  

> [!NOTE]
>  **ExtractionNodeXPath**プロパティを 1 つだけの要素を返す XPath をする必要があります。 コンポーネントには、結果は要素ではない場合、または XPath クエリが 1 つ以上の要素を返す場合に、例外が発生します。