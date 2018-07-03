---
title: BizTalk Adapter Pack で Siebel アダプターのメタデータ ノード Id |Microsoft Docs
description: メタデータ、検索、取得のタイプのノード、および Siebel アダプターの BizTalk アダプター パック (BAP) で公開される Siebel コンポーネントで使用される Id
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bdffc8d1-0a0a-48d7-b134-5d16acf2c523
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: abce1288be6c706d71bf644325a9cfd7200155c4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991483"
---
# <a name="node-types-and-ids-for-the-siebel-adapter"></a>ノードの種類と Siebel アダプターの Id

## <a name="metadata-node-types-and-ids"></a>メタデータのノードの種類と Id 
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Siebel システムの成果物を階層的に明らかになります。 次の表は、ノードの種類と側に表示される Siebel 成果物のノード Id、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。  


|                成果物                 | ノードの種類 |                                 ノード Id                                  |                                          例                                          |                                  説明                                   |
|-----------------------------------------|-----------|--------------------------------------------------------------------------|-------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------|
| ビジネス オブジェクト (すべてのビジネス オブジェクト) | カテゴリ  |                        [バージョン]/BusinessObjects                         |                http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects                |                         すべてのビジネス オブジェクトを返します。                          |
|          ビジネス オブジェクト (BO)           | カテゴリ  |                      [バージョン]/BusinessObjects/[BO]                      |            http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account            | 指定されたビジネス オブジェクトに関連付けられたすべてのビジネス コンポーネントを返します。 |
|         ビジネス コンポーネント (BC)         | カテゴリ  |                   [バージョン]/BusinessObjects/[BO]/[BC]                    |        http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account        |    指定されたビジネス コンポーネントに関連付けられているすべての操作を返します。    |
|                 Insert                  | OPERATION |                [バージョン]/BusinessObjects/[BO]/[BC]/挿入                |    http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert     |       指定されたビジネス コンポーネントの挿入操作を返します。       |
|                  Query                  | OPERATION |                [バージョン]/BusinessObjects/[BO]/[BC]/[クエリ]                 |     http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Query     |       指定されたビジネス コンポーネントのクエリ操作を返します。        |
|                 更新                  | OPERATION |                [バージョン]/BusinessObjects/[BO]/[BC]/[更新]                |    http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Update     |       指定されたビジネス コンポーネントの更新操作を返します。       |
|                 DELETE                  | OPERATION |                [バージョン]/BusinessObjects/[BO]/[BC]/削除                |    http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Delete     |       指定されたビジネス コンポーネントの削除操作を返します。       |
|                関連付け                | OPERATION |              [バージョン]/BusinessObjects/[BO]/[BC]/[関連付ける]               |   http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Associate   |     指定されたビジネス コンポーネントに関連付ける操作を返します。      |
|               関連付けを解除します。                | OPERATION |              [バージョン]/BusinessObjects/[BO]/[BC]/[との関連付けを解除]              |  http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Dissociate   |     指定されたビジネス コンポーネントの関連付け解除操作を返します。     |
|  Query_ [MVG Child Business Component]   | OPERATION | [バージョン]/BusinessObjects/[BO]/[BC]/[MVG Child Business Component] Query_ | http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Query_Contact |          Child business component のクエリ操作を返します          |
|            ビジネス サービス            | カテゴリ  |                        [バージョン]/ビジネス サービス                        |               http://Microsoft.LobServices.Siebel/2007/03/BusinessServices                |                         すべてのビジネス サービスを返します。                         |
|            ビジネス サービス             | カテゴリ  |              [バージョン]/BusinessServices/[ビジネス サービス]               |             http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/ATP              |        指定されたビジネス サービスのすべてのビジネス メソッドを返します。        |
|         ビジネス サービス メソッド         | OPERATION | [バージョン]/BusinessServices/[ビジネス サービス]/[ビジネス サービス メソッド]  |       http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/ATP/ATPRunCheck        |                 指定されたビジネス サービス メソッドを返します。                 |

 [バージョン] バージョンの文字列を =たとえばhttp://Microsoft.LobServices.Siebel/2007/03します。  

 [BO] = A Siebel ビジネス オブジェクト。たとえば、アカウントです。  

 [BC] = ビジネス コンポーネント。たとえば、アカウントです。  

 [ビジネス サービス]、Siebel ビジネス サービスを =たとえば、ATP です。  

 [ビジネス サービス メソッド] のビジネス サービスのメソッドを =たとえば、DismissAlarm です。  

 [MVG Child Business Component] = 複数値のグループの子ビジネス コンポーネント。たとえばにお問い合わせください。  

## <a name="metadata-search-and-node-ids"></a>メタデータの検索とノードの Id  
 メタデータの検索は、強力な機能、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]サーフェスの一部としてその**MetadataRetrievalContract**インターフェイス。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Siebel の次のアーティファクトの検索をサポートするには、この機能を活用します。  

|成果物|ノード Id|説明|  
|--------------|-------------|-----------------|  
|ビジネス オブジェクト|[バージョン]/BusinessObjects|検索式に一致するビジネス オブジェクトを返します。|  
|ビジネス コンポーネント|[バージョン]/BusinessObjects/[BO]|検索式に一致するビジネス コンポーネントを返します。|  
|ビジネス サービス|[バージョン]/ビジネス サービス|検索式に一致するビジネス サービスを返します。|  
|ビジネス サービス メソッド|[バージョン]/BusinessServices/[ビジネス サービス]|検索式に一致するビジネス サービス メソッドが返されます。|  

 [バージョン] バージョンの文字列を =たとえばhttp://Microsoft.LobServices.Siebel/2007/03します。  

 [BO] = Siebel ビジネス オブジェクト。たとえば、アカウントです。  

 [ビジネス サービス] = Siebel ビジネス サービスです。たとえば、ATP です。  

 有効な検索式の場合は、Siebel のドキュメントを参照してください。  

> [!NOTE]
>  [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]のみ、現在選択されているノードの下のレベルでの検索をサポートします。  たとえば、BusinessObjects を選択すると、A * はサポートされている検索が A\*/A\*はありません。  

## <a name="metadata-retrieval-and-node-ids"></a>メタデータを取得し、ノード Id  
 Siebel アダプターでは、成果物の種類ごとに、次の特性をキャプチャします。  

|成果物|メタデータの特性|  
|--------------|------------------------------|  
|ビジネス コンポーネント|<ul><li>ビジネス コンポーネント名</li><li>ビジネス コンポーネントのフィールド名</li><li>WSDL のシンプル/複雑な型にマップされたビジネス コンポーネントのフィールドのデータ型</li><li>ファセットの maxLength にマップされているビジネス コンポーネントのフィールド長</li><li>ビジネス コンポーネントの必須フィールドがファセット minOccurs にマップされている 1 を =</li><li>ビジネス コンポーネントの省略可能なフィールドがファセット minOccurs にマップされている 0 を =</li><li>WSDL での候補リストの複合型にマップされているビジネス コンポーネントの候補リスト フィールド</li><li>ビジネス コンポーネントの静的な値の一覧の列挙を含む候補リストを制限します。</li><li>ファセット isNillable にマップされているビジネス コンポーネントのフィールドの NULL 制約 = true</li><li>ビジネス コンポーネント操作<br /><br /> <ul><li>INSERT</li><li>QUERY</li><li>UPDATE</li><li>Del</li><li>関連付ける</li><li>関連付けを解除します。</li><li>ビジネス コンポーネントが m:n リレーションシップを各子ビジネス コンポーネント [MVG 子ビジネス Comp] QUERY_</li></ul></li></ul>|  
|ビジネス サービス メソッド|ビジネス サービス名<br />メソッド名<br />メソッドは、操作です。<br />メソッドのパラメーター名<br />-WSDL 型にマップ メソッド パラメーターのデータ型<br />-WSDL パラメーターの方向にマップ メソッド パラメーターの方向<br />-要素のシーケンスにマップ メソッド パラメーターの順序|  

 メタデータの形式に関する詳細情報を[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]特定の成果物と、Siebel システムに対する操作の公開を参照してください[メッセージと BizTalk adapter for Siebel eBusiness Applicationsメッセージスキーマ](../../adapters-and-accelerators/adapter-siebel/messages-and-message-schemas-for-siebel-adapter-in-biztalk.md).  
