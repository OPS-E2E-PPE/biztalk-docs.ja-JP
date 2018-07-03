---
title: リゾルバー サービス サンプルを実行している |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b4bf0b21-6aa0-4524-9e63-93a172845d4a
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21c569f0be544292b4a70d49f4c75a038e2fed65
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006675"
---
# <a name="running-the-resolver-service-sample"></a>リゾルバー サービス サンプルを実行しています。
リゾルバー サービス サンプルでは、次のシナリオを使用します。  

- サービス エンドポイント バインド キーを使用して、UDDI3 から URI を解決するには  

- サービス エンドポイントのカテゴリ化の検索を使用して、UDDI3 から URI を解決するには  

- 静的な競合回避モジュールを使用して、変換 (BizTalk マップの種類) を解決するには  

- サービス エンドポイントの静的な競合回避モジュールを使用して、URI を解決するには  

- サービス エンドポイント、XPath 式を使用して、URI を解決するには  

- 静的行程リゾルバーを使用するスケジュールを解決するには  

- 行程静的 (Unity) の競合回避モジュールを使用して、スケジュールを解決するには  

- BRE (BRI リゾルバー) を使用するスケジュールを解決するには  

- BRE (BRI リゾルバー) を使用してメッセージを使用するスケジュールを解決するには  

- サービス エンドポイント URI を解決する BRE を使用します。  

- BRE を使用して変換を解決するには  

  **リゾルバー サービスの ASMX 実装を使用してすべての解決シナリオを実行するには**  

1. GlobalBank.ESB アプリケーションが実行されていない場合は、Microsoft の BizTalk 管理コンソールを使用して、開始します。  

2. Windows エクスプ ローラーで \Source\Samples\ResolverService フォルダーを開き、RunTestClient_ASMX.cmd ファイルをダブルクリックします。  

3. \Source\Samples\ResolverService\Output フォルダーを開き、前に示した解決要求に対応する結果ファイルを開きます。  

   **リゾルバー サービスの WCF 実装を使用してすべての解決シナリオを実行するには**  

4. GlobalBank.ESB アプリケーションが実行されていない場合は、BizTalk 管理コンソールを使用して開始します。  

5. Windows エクスプ ローラーで \Source\Samples\ResolverService フォルダーを開き、RunTestClient_WCF.cmd ファイルをダブルクリックします。  

6. \Source\Samples\ResolverService\Output フォルダーを開き、前に示した解決要求に対応する結果ファイルを開きます。
