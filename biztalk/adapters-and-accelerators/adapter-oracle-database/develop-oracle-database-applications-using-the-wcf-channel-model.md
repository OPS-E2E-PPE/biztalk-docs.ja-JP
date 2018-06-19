---
title: WCF チャネル モデルを使用して Oracle データベース アプリケーションを開発 |Microsoft ドキュメント
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
ms.openlocfilehash: 77fb9b6ca1fc70a55b59c6708450b8d94a01eff8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214986"
---
# <a name="develop-oracle-database-applications-using-the-wcf-channel-model"></a>WCF チャネル モデルを使用して Oracle データベース アプリケーションを開発します。
使用することができます、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]チャネル モデルを使用する、 [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] Oracle DB バインドで作成されたチャネル インスタンス経由で直接 XML メッセージを送信することによってです。  
  
 厳密に型指定されたクラスと、WCF サービス モデルを公開するメソッドを使用する場合より、WCF チャネル モデルを使用する利点の 1 つは、チャネル モデルが Oracle データベースで実行する操作をより詳細に制御を提供することです。 なぜでしょうか。 WCF チャネル モデルでは、チャネル経由で送信するメッセージの内容を直接制御します。  
  
 特定のシナリオでは、この余分なレベルの制御と役に立つことがあります。 たとえば、WCF チャネル モデルを使用して、テーブルの更新操作を実行するときに、ターゲット行の列をメッセージを渡すテンプレートの更新からの列を省略することでに更新できます選択的にします。 によって公開されている、update メソッドを[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]クライアントは、テーブルのスキーマ内のすべての列を含むテンプレートに対してレコードの厳密に型指定されたパラメーターを使用します。 列にある場合"nillable = false"、WSDL 内で、更新する必要がある WCF サービス モデルを使用します。  
  
 WCF チャネル モデルを WCF サービス モデルを提供する主なメリットは、Oracle ラージ オブジェクト (LOB) データ型のエンド ツー エンドのストリーミングをサポートする包括的なです。 WCF チャネル モデルを使用して、エンド ツー エンドのストリーミングを実行できます。  
  
-   テーブル内の LOB 列を更新または UpdateLOB 操作を使用して表示します。  
  
-   アウトでと OUT パラメーターを含む IN は LOB プロシージャと関数によって返されるデータです。  
  
-   LOB データに SQLEXECUTE 操作の結果に含まれます。  
  
-   LOB データの列を POLLINGSTMT 操作で返されます。  
  
-   LOB データの列をテーブルまたはビューに対する Select 操作によって返されます。  
  
 これは、ため、WCF チャネル モデルで直接制御する送信メッセージにメッセージ本文を指定する方法と、受信メッセージでメッセージ本文を処理する方法です。  
  
 これに対し、WCF サービスのモデルのみを提供します。  
  
-   エンドツー エンド ReadLOB 操作の 1 つの操作の LOB データをストリーミングします。  
  
-   LOB データをストリーミング方式で Oracle データベースを更新する機能がありません。  
  
 このトピックのセクションでは、操作を実行する方法を説明する、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] WCF チャネル モデルを使用します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [Oracle データベース アダプターで WCF チャネル モデルの概要](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-channel-model-with-the-oracle-database-adapter.md) 
  
-   [Oracle データベースを使用して、チャネルを作成します。](../../adapters-and-accelerators/adapter-oracle-database/create-a-channel-using-oracle-database.md) 
  
-   [WCF チャネル モデルを使用して Oracle データベースに対する操作を呼び出す](../../adapters-and-accelerators/adapter-oracle-database/invoke-operations-on-the-oracle-database-using-the-wcf-channel-model.md)  
  
-   [WCF チャネル モデルを使用して Oracle データベースで SQLEXECUTE 操作を実行します。](../../adapters-and-accelerators/adapter-oracle-database/run-a-sqlexecute-operation-in-oracle-database-using-the-wcf-channel-model.md)  
  
-   [WCF チャネル モデルを使用して Oracle データベースで挿入操作を実行します。](../../adapters-and-accelerators/adapter-oracle-database/run-an-insert-operation-in-oracle-database-using-the-wcf-channel-model.md)  
  
-   [WCF チャネル モデルを使用して Oracle データベース内の関数を呼び出す](../../adapters-and-accelerators/adapter-oracle-database/invoke-a-function-in-oracle-database-using-the-wcf-channel-model.md)  
  
-   [WCF チャネル モデルを使用して Oracle データベースでデータ変更のポーリングに基づいたメッセージを受信します。](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-db-using-a-wcf-channel.md)  
  
-   [ストリーミングの Oracle データベース LOB データ型 WCF チャネル モデルを使用します。](../../adapters-and-accelerators/adapter-oracle-database/streaming-oracle-database-lob-data-types-using-the-wcf-channel-model.md)