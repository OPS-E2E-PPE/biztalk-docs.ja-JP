---
title: "インターセプタ構成式 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2695f509-fece-40b8-aa00-fa3c0c0f19c5
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 927afa60dc65fb014f0d44305db5e7f6e78b803b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="interceptor-configuration-expressions"></a>インターセプタ構成式
BAM インターセプタ構成ファイルは、フィルタ式を使用してアクティビティを識別し、データ式を使用してストレージのデータ要素を作成して、そのデータ要素を関連付け ID または継続トークンとして使用したり、同様の目的で使用します。 その目的に関係なく、個々の式は `expression` 要素によってインターセプタ構成ファイル内に指定され、式には後置表記法とも呼ばれる逆ポーランド表記法 (RPN: Reverse Polish Notation) を使用した 1 つまたは複数の演算子が含まれています。  
  
## <a name="about-reverse-polish-notation"></a>逆ポーランド表記法について  
 逆ポーランド表記法では、演算子の前にオペランドを記述するため、かっこを前置演算子として使用する必要はありません。 スタックは、スタックへの値のプッシュ、スタックからの値のポップ (削除)、またはプッシュとポップを組み合わせた操作の実行における各値とすべての操作の保持に使用されます。  
  
 たとえば、次の式の評価を行うとします。  
  
 `5 + (10 - 2)`  
  
 この式を同等の RPN に変換すると次のようになります。  
  
 `5 10 2 - +`  
  
 この式は、次のように評価されます。  
  
|入力|操作|スタック|  
|-----------|---------------|-----------|  
|5|プッシュ|5|  
|10|プッシュ|5, 10|  
|2|プッシュ|5, 10, 2|  
|-|減算|5, 8|  
|+|[追加]|13|  
  
 RPN システムで文字列連結操作がサポートされると仮定した場合、次の式を評価することもできます。  
  
 `"The quick brown " + "fox " + "jumped over the lazy " + "dog."`  
  
 この式を同等の RPN 表記法に変換すると次のようになります。  
  
 `"The quick brown " "fox " "jumped over the lazy " "dog" + + +`  
  
 この式は、次のように評価されます。  
  
|入力|操作|スタック|  
|-----------|---------------|-----------|  
|"The quick brown"|プッシュ|"クイック brown"|  
|"fox"|プッシュ|"The quick brown ", "fox "|  
|"jumped over the lazy"|プッシュ|"The quick brown ", "fox ", "jumped over the lazy "|  
|"dog."|プッシュ|"The quick brown ", "fox ", "jumped over the lazy ", "dog."|  
|+|連結|"The quick brown ", "fox ", "jumped over the lazy dog."|  
|+|連結|"The quick brown ", "fox jumped over the lazy dog."|  
|+|連結|"The quick brown fox jumped over the lazy dog."|  
  
 この例でわかるように、比較、ブール演算、関与する演算に適した値を取得するカスタム操作など、任意の数の操作をサポートできます。 スタックに値が累積され、個々の操作に従ってプッシュまたはポップされます。  
  
## <a name="reverse-polish-notation-in-the-interceptor-configuration-file"></a>インターセプタ構成ファイル内での逆ポーランド表記法  
 2 つの式で作成、インターセプター構成ファイル: 式とデータ式をフィルター処理します。 フィルタ式は RPN 式の結果を処理してブール値 `true` または `false` を返すのに対し、データ式はスタック上の単一の値を処理します。  
  
### <a name="filter-expressions"></a>フィルタ式  
 フィルタ式はブール値 `true` または `false` を評価し、特定のイベントを識別して WF アプリケーションまたは WFC アプリケーションを追跡するために使用されます。 WF アプリケーションでは、一般にアクティビティ名とイベントに基づいてフィルタ処理します。 たとえばを選択することがあります、 **FoodAndDrinksPolicy**アクティビティであるときに**Closed**です。 WF 操作を使用すると、フィルタを次のように表現できます。  
  
 `(GetActivityName = "FoodAndDrinksPolicy") && (GetActivityEvent = "Closed")`  
  
 この式を RPN に変換すると次のようになります。  
  
 `GetActivityName "FoodAndDrinksPolicy" == GetActivityEvent "Closed" == &&`  
  
 この式をインターセプタ構成ファイル用の同等の式に変換すると、次の XML になります。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>FoodAndDrinksPolicy</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <wf:Operation Name="GetActivityEvent"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>Closed</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <ic:Operation Name="And"/>  
  </ic:Expression>  
</ic:Filter>  
```  
  
 最後に、この式の評価と仮定すると次のように**GetActivityName** "dessertpolicy"と**GetActivityEvent** "Closed"が返されます。  
  
|入力|操作|スタック|  
|-----------|---------------|-----------|  
||GetActivityName|"DessertPolicy"|  
|"FoodAndDrinksPolicy"|定数|"DessertPolicy", "FoodAndDrinksPolicy"|  
|[等しい]|比較|False|  
||GetActivityEvent|False, Closed|  
|"Closed"|定数|False, "Closed", "Closed"|  
|[等しい]|比較|False, True|  
|And|論理と|False|  
  
 スタックに残される値はブール値 `False` です。 したがって、対応するイベントは発生しません。 アクティビティ名が "FoodAndDrinksPolicy" であった場合、この式はブール値 `True` として評価されます。  
  
 WCF 操作 `GetEndpointName` および `GetOperationName` を使用すると、同様の評価を行う式を作成できます。  
  
### <a name="data-expressions"></a>データ式  
 データ式は、単一の文字列データ値を定義するために使用されます。 データ式は、`Filter` 要素で囲まれていない任意の式です。 データ式は、`OnEvent` 要素の `CorrelationID`、`ContinuationToken`、`Reference`、および `Update` で使用されます。  
  
 これは、BAM アクティビティ データベースをラベル付きタイム スタンプで更新するための一般的な要件です。 イベントの設定として書式設定文字列が開始された時刻をキャプチャするたとえば、"開始: \<EventTime\>"です。 これを行うには、次のような式を使用する必要があります (+ は連結を表します)。  
  
 `"Start: " + GetContextProperty(EventTime)`  
  
 この式を RPN に変換すると次のようになります。  
  
 `"Start: " GetContextProperty(EventTime) +`  
  
 この式をインターセプタ構成ファイルの `Update` 要素用の同等の式に変換すると、次の XML になります。  
  
```  
<ic:Update DataItemName="NewOrderCreateTime" Type="NVARCHAR">  
  <ic:Expression>  
    <ic:Operation Name="Constant">  
      <ic:Argument>Start:</ic:Argument>  
    </ic:Operation>  
    <wf:Operation Name="GetContextProperty">  
      <wf:Argument>EventTime</wf:Argument>  
    </wf:Operation>  
    <ic:Operation Name="Concatenate" />  
  </ic:Expression>  
</ic:Update>  
```  
  
 次の表は、イベント時刻が "12:00 PM" の場合に、この式がどのように解釈されるかを示しています。  
  
|入力|操作|スタック|  
|-----------|---------------|-----------|  
|"を開始します"。|定数|"を開始します"。|  
|GetContextProperty(EventTime)|プッシュ|"開始:"、"2006-09-27T12:00:34.000Z"|  
|連結|連結|"開始: 2006-09-27T12:00:34.000Z"|  
  
 更新コマンドで使用される値になります"開始: 2006-09-27T12:00:34.000Z"です。  
  
> [!NOTE]
>  データ式では比較演算 "And" および "Equals" は使用しないでください。 この演算を使用すると、インターセプタ構成ファイルを展開するときにエラーが発生します。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [インターセプターの操作](../core/interceptor-operations.md)  
  
## <a name="see-also"></a>参照  
 [インターセプター構成ファイルの構造](../core/structure-of-an-interceptor-configuration-file.md)