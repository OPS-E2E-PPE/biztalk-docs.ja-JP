---
title: "リゾルバー サービスのサンプルを実行している |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b4bf0b21-6aa0-4524-9e63-93a172845d4a
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb9d7e3e4d4bce4e46653f7b650004928368eced
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="running-the-resolver-service-sample"></a>リゾルバー サービスのサンプルを実行しています。
リゾルバー サービス サンプルでは、次のシナリオを使用します。  
  
-   サービス エンドポイント バインド キーを使用して、UDDI3 から URI を解決するには  
  
-   サービス エンドポイントのカテゴリ化検索を使用して、UDDI3 から URI を解決するには  
  
-   静的な競合回避モジュールを使用して、変換 (BizTalk マップの種類) を解決するには  
  
-   サービス エンドポイントに静的な競合回避モジュールを使用して URI を解決するには  
  
-   サービス エンドポイント、XPath 式を使用して URI を解決するには  
  
-   静的行程リゾルバーを使用して、日程を解決するには  
  
-   行程静的 (Unity) リゾルバーを使用して、日程を解決するには  
  
-   BRE (BRI リゾルバー) を使用して、日程を解決するには  
  
-   BRE (BRI リゾルバー) を使用して、メッセージと共に日程を解決するには  
  
-   サービス エンドポイントの URI を解決するには BRE を使用して  
  
-   BRE を使用して変換を解決するには  
  
 **ASMX、リゾルバー サービスの実装を使用するすべての解像度シナリオを実行するには**  
  
1.  GlobalBank.ESB アプリケーションが既に実行されていない場合は、Microsoft BizTalk 管理コンソールを使用して、開始します。  
  
2.  Windows エクスプ ローラーで、\Source\Samples\ResolverService フォルダーを開き RunTestClient_ASMX.cmd ファイルをダブルクリックします。  
  
3.  \Source\Samples\ResolverService\Output フォルダーを開き、以前に一覧表示する解決要求に対応する結果ファイルを開きます。  
  
 **リゾルバー サービスの WCF 実装を使用してすべての解像度シナリオを実行するには**  
  
1.  GlobalBank.ESB アプリケーションが既に実行されていない場合は、BizTalk 管理コンソールを使用して、開始します。  
  
2.  Windows エクスプ ローラーで、\Source\Samples\ResolverService フォルダーを開き RunTestClient_WCF.cmd ファイルをダブルクリックします。  
  
3.  \Source\Samples\ResolverService\Output フォルダーを開き、以前に一覧表示する解決要求に対応する結果ファイルを開きます。