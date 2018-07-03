---
title: WCF チャネル モデルを使用して Oracle データベース アプリケーションの開発 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF channel model, streaming
- channel programming, streaming
- WCF channel model, performing operations
- developing applications, by using the WCF channel model
- streaming, using the WCF channel model
- WCF channel model, developingn applications
- channel programming, performing operations
ms.assetid: cb6bf5fd-ff90-44bd-a9dd-03b00f12a78d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4990ebb9e9aad612a82af42b3d186643da1e91ab
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002731"
---
# <a name="develop-oracle-database-applications-using-the-wcf-channel-model"></a>WCF チャネル モデルを使用して Oracle データベース アプリケーションを開発します。
使用することができます、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]チャネル モデルを使用する、 [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] Oracle DB のバインドで作成されたチャネル インスタンス経由で直接 XML メッセージを送信することです。  
  
 WCF チャネル モデルを使用して、厳密に型指定されたクラスと、WCF サービス モデルを公開するメソッドを使用する利点の 1 つは、チャネル モデルが Oracle データベースで実行する操作のきめの細かい制御を提供します。 なぜでしょうか。 WCF チャネル モデルでは、直接チャネル経由で送信するメッセージの内容を制御します。  
  
 特定のシナリオでこの追加レベルの制御はパフォーマンスを向上することはできます。 たとえば、WCF チャネル モデルを使用して、テーブルに対する Update 操作を実行するときに選択的に更新できますターゲット行内の列、メッセージを渡すテンプレートの更新からの列を省略することで。 によって公開されている、update メソッドを[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]クライアントで、テーブルのスキーマ内のすべての列を含むテンプレートのレコードの厳密に型指定されたパラメーターを使用します。 列にある場合は、"nillable = false"、WSDL の更新が必要、WCF サービス モデルを使用します。  
  
 WCF チャネル モデルを使用する WCF サービスのモデルに対するもう 1 つの主な利点は、Oracle のラージ オブジェクト (LOB) データ型のエンド ツー エンドのストリーミングをサポートするより包括的なです。 WCF チャネル モデルを使用して、エンド ツー エンドのストリーミングを実行できます。  
  
- テーブル内の LOB 列を更新または UpdateLOB 操作を使用して表示します。  
  
- アウトでと OUT パラメーターを含む IN は LOB プロシージャおよび関数によって返されるデータです。  
  
- LOB データを SQLEXECUTE 操作の結果に含まれます。  
  
- LOB データ POLLINGSTMT 操作で返される列。  
  
- LOB データ列でテーブルまたはビューの選択操作によって返されます。  
  
  これは、ため、WCF チャネル モデルで直接制御する送信メッセージにメッセージ本文を提供する方法と、受信メッセージでメッセージ本文を処理する方法です。  
  
  これに対し、WCF サービス モデルのみを提供します。  
  
- エンド ツー エンド ReadLOB 操作の 1 つの操作では LOB データにストリーミングします。  
  
- LOB データをストリーミング方式で Oracle データベースを更新する機能がありません。  
  
  このトピックのセクションでは、操作を実行する方法を説明します、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] WCF チャネル モデルを使用しています。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [Oracle データベース アダプターを使用した WCF チャネル モデルの概要](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-channel-model-with-the-oracle-database-adapter.md) 
  
-   [Oracle データベースを使用してチャネルを作成します。](../../adapters-and-accelerators/adapter-oracle-database/create-a-channel-using-oracle-database.md) 
  
-   [WCF チャネル モデルを使用して Oracle データベースに対する操作を呼び出す](../../adapters-and-accelerators/adapter-oracle-database/invoke-operations-on-the-oracle-database-using-the-wcf-channel-model.md)  
  
-   [WCF チャネル モデルを使用して Oracle データベースで SQLEXECUTE 操作を実行します。](../../adapters-and-accelerators/adapter-oracle-database/run-a-sqlexecute-operation-in-oracle-database-using-the-wcf-channel-model.md)  
  
-   [WCF チャネル モデルを使用して Oracle データベースで挿入操作を実行します。](../../adapters-and-accelerators/adapter-oracle-database/run-an-insert-operation-in-oracle-database-using-the-wcf-channel-model.md)  
  
-   [WCF チャネル モデルを使用して Oracle データベースで関数を呼び出す](../../adapters-and-accelerators/adapter-oracle-database/invoke-a-function-in-oracle-database-using-the-wcf-channel-model.md)  
  
-   [WCF チャネル モデルを使用して Oracle データベースでのポーリングに基づいたデータ変更メッセージを受信します。](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-db-using-a-wcf-channel.md)  
  
-   [ストリーミングの Oracle データベース LOB データ型 WCF チャネル モデルを使用します。](../../adapters-and-accelerators/adapter-oracle-database/streaming-oracle-database-lob-data-types-using-the-wcf-channel-model.md)