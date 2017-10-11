---
title: "BizTalk Adapter Pack の Siebel アダプターのメタデータのノードの Id |Microsoft ドキュメント"
description: "メタデータ、検索、取得ノードの種類および Siebel アダプターの BizTalk アダプター パック (BAP) で公開される Siebel コンポーネントで使用される Id"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bdffc8d1-0a0a-48d7-b134-5d16acf2c523
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5aecf8995b30f5cd545e4202da0c468d730e277
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="node-types-and-ids-for-the-siebel-adapter"></a>ノード型との Siebel アダプターの Id

## <a name="metadata-node-types-and-ids"></a>メタデータのノード型および Id 
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]階層状に Siebel システムの成果物を表示します。 次の表は、ノードの種類とによって表示される Siebel 成果物のためのノード Id、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。  
  
|成果物|ノードの種類|ノード Id|例|Description|  
|--------------|---------------|-------------|-------------|-----------------|  
|ビジネス オブジェクト (すべてのビジネス オブジェクト)|カテゴリ|[バージョン]/BusinessObjects|http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects|すべてのビジネス オブジェクトを返します。|  
|ビジネス オブジェクト (BO)|カテゴリ|[バージョン]/BusinessObjects/[BO]|http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account|指定されたビジネス オブジェクトに関連付けられているすべてのビジネス コンポーネントを返します。|  
|ビジネス コンポーネント (BC)|カテゴリ|[バージョン]/BusinessObjects/[BO]/[BC]|http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account|指定されたビジネス コンポーネントに関連付けられているすべての操作を返します。|  
|Insert|OPERATION|[バージョン]/BusinessObjects/[BO]/[BC]/挿入|http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert|指定されたビジネス コンポーネントの挿入操作を返します。|  
|Query|OPERATION|[バージョン]/BusinessObjects/[BO]/[BC]/[クエリ]|http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Query|指定されたビジネス コンポーネントのクエリ操作を返します。|  
|Update|OPERATION|[バージョン]/BusinessObjects/[BO]/[BC]/[更新]|http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Update|指定されたビジネス コンポーネントの更新操作を返します。|  
|DELETE|OPERATION|[バージョン]/BusinessObjects/[BO]/[BC] を削除します|http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Delete|指定されたビジネス コンポーネントの削除操作を返します。|  
|関連付け|OPERATION|[バージョン]/BusinessObjects/[BO]/[BC]/[関連付ける]|http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Associate|指定されたビジネス コンポーネントに関連付ける操作を返します。|  
|との関連付けを解除します。|OPERATION|[バージョン]/BusinessObjects/[BO]/[BC]/[との関連付けを解除]|http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Dissociate|指定されたビジネス コンポーネントの関連付けを解除操作を返します。|  
|Query_ [MVG 子ビジネス コンポーネント]|OPERATION|[バージョン]/BusinessObjects/[BO]/[BC]/Query_ [MVG 子ビジネス コンポーネント]|http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Query_Contact|Child business component のクエリ操作を返します|  
|ビジネス サービス|カテゴリ|[バージョン]/ビジネス サービス|http://Microsoft.LobServices.Siebel/2007/03/BusinessServices|すべてのビジネス サービスを返します。|  
|ビジネス サービス|カテゴリ|[バージョン]/BusinessServices/[ビジネス サービス]|http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/ATP|指定されたビジネス サービスのすべてのビジネス メソッドを返します。|  
|ビジネス サービス メソッド|OPERATION|[バージョン]/BusinessServices/[ビジネス サービス]/[ビジネス サービス メソッド]|http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/ATP/ATPRunCheck|指定されたビジネス サービス メソッドを返します。|  
  
 [バージョン] = バージョン文字列です。たとえば http://Microsoft.LobServices.Siebel/2007/03 します。  
  
 [BO] = A Siebel ビジネス オブジェクトです。たとえば、アカウントです。  
  
 [BC] = ビジネス コンポーネントです。たとえば、アカウントです。  
  
 [ビジネス サービス]、Siebel ビジネス サービスを =たとえば、分析ツールです。  
  
 [ビジネス サービス メソッド]、ビジネス サービスのメソッドを =たとえば、DismissAlarm です。  
  
 [MVG Child Business Component] = 複数値のグループの子ビジネス コンポーネントです。たとえばにお問い合わせください。  
  
## <a name="metadata-search-and-node-ids"></a>メタデータの検索とノード Id  
 メタデータの検索では、高度な機能、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]サーフェスの一部としてその**MetadataRetrievalContract**インターフェイスです。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Siebel の次の成果物の検索をサポートするには、この機能を活用します。  
  
|成果物|ノード Id|Description|  
|--------------|-------------|-----------------|  
|ビジネス オブジェクト|[バージョン]/BusinessObjects|検索式に一致するビジネス オブジェクトを返します。|  
|ビジネス コンポーネント|[バージョン]/BusinessObjects/[BO]|検索式に一致するビジネス コンポーネントを返します。|  
|ビジネス サービス|[バージョン]/ビジネス サービス|検索式に一致するビジネス サービスを返します。|  
|ビジネス サービス メソッド|[バージョン]/BusinessServices/[ビジネス サービス]|検索式に一致するビジネス サービス メソッドを返します。|  
  
 [バージョン] = バージョン文字列です。たとえば http://Microsoft.LobServices.Siebel/2007/03 します。  
  
 [BO] = Siebel ビジネス オブジェクトです。たとえば、アカウントです。  
  
 [ビジネス サービス]、Siebel ビジネス サービスを =たとえば、分析ツールです。  
  
 有効な検索式の場合は、Siebel のドキュメントを参照してください。  
  
> [!NOTE]
>  [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]のみ、現在選択されているノードの下のレベルでの検索をサポートします。  たとえば、BusinessObjects を選択すると、A * は、サポートされているが、検索、A\*/A\*はありません。  
  
## <a name="metadata-retrieval-and-node-ids"></a>メタデータを取得し、ノード Id  
 Siebel アダプターは、成果物の種類ごとに次の特徴をキャプチャします。  
  
|成果物|メタデータの特性|  
|--------------|------------------------------|  
|ビジネス コンポーネント|<ul><li>ビジネス コンポーネント名</li><li>ビジネス コンポーネントのフィールド名</li><li>WSDL を複雑な単純型にマップされたビジネス コンポーネントのフィールドのデータ型</li><li>ファセットの maxlength プロパティにマップされているビジネス コンポーネントのフィールド長</li><li>ビジネス コンポーネントの必須フィールドがファセット minOccurs にマップされている 1 を =</li><li>ビジネス コンポーネントの省略可能なフィールドがファセット minOccurs にマップされている 0 を =</li><li>WSDL での候補リストの複合型にマップされているビジネス コンポーネントの候補リスト フィールド</li><li>ビジネス コンポーネントの静的な列挙値の一覧を含む候補のリストを制限します。</li><li>ビジネス コンポーネント フィールド NULL 制約ファセット isNillable にマップされている = true</li><li>ビジネス コンポーネント操作<br /><br /> <ul><li>INSERT</li><li>QUERY</li><li>UPDATE</li><li>DELETE</li><li>関連付ける</li><li>との関連付けを解除します。</li><li>ビジネス コンポーネントを使用するには、m:n リレーションシップは、各子ビジネス コンポーネント [MVG 子ビジネス Comp] QUERY_</li></ul></li></ul>|  
|ビジネス サービス メソッド|ビジネス サービス名<br />メソッド名<br />メソッドは、操作です。<br />メソッド パラメーター名<br />の WSDL の種類にマップされているメソッド パラメーターのデータ型<br />の WSDL パラメーターの方向にマップされているメソッド パラメーターの方向<br />の要素のシーケンスにマップ メソッド パラメーターの順序|  
  
 詳細については、形式のメタデータを[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]特定の成果物と Siebel システムの操作の公開を参照してください[メッセージ スキーマと BizTalk Adapter for Siebel eBusiness Applicationsメッセージスキーマ](../../adapters-and-accelerators/adapter-siebel/messages-and-message-schemas-for-siebel-adapter-in-biztalk.md).  
  