---
title: WCF サービス モデルで、SQL アダプターを使用してポーリング SQL Server |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eef2e868-bd51-4393-b091-f67299b4759d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20d0ab576e5feddb0b5f3e867ca549a45bb2af97
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222914"
---
# <a name="poll-sql-server-using-the-sql-adapter-with-wcf-service-model"></a>WCF サービス モデルで、SQL アダプターを使用して SQL サーバーにポーリング
構成することができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を SQL Server からデータ変更のポーリングに基づいたメッセージを受信します。 データベースをポーリングするアダプターを実行するポーリング ステートメントを指定することができます。 ポーリング ステートメントには、SELECT ステートメントまたは結果セットを返すストアド プロシージャを使用できます。 ポーリングのメッセージの種類に基づいて、アダプターは、さまざまなポーリング操作を公開します。  
  
-   **ポーリング**です。 この操作は、ポーリング メッセージの一部としてデータ セットを返します。  
  
-   **TypedPolling**です。 この操作は、厳密に型指定されたポーリング メッセージを返します。  
  
-   **XmlPolling**です。 この操作は、XML メッセージとしてポーリング メッセージを返します。 SELECT ステートメントや XML メッセージとしてデータを返す FOR XML 句を使用するストアド プロシージャを使用する場合は、この操作を使用する必要があります。 [FOR XML 句](https://docs.microsoft.com/sql/relational-databases/xml/for-xml-sql-server)詳細な情報を提供します。 
  
 これらのポーリング処理の詳細については、次を参照してください。 [SQL アダプタを使用して SQL Server でのポーリング](../../adapters-and-accelerators/adapter-sql/polling-in-sql-server-using-the-sql-adapter.md)です。  
  
> [!NOTE]
>  [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]アダプター クライアントには同じデータベースまたはテーブルの 1 つ以上のポーリングや TypedPolling 操作を 1 つのアプリケーションを有効にします。 このようなシナリオをサポートするために、アダプターに一意の ID が含まれています — **InboundID**— 接続 URI にします。 接続 URI に追加すると、この ID には一意になります、1 つのアプリケーションで複数のポーリング操作できるようにします。  
  
 このセクションのトピックでは、.NET アプリケーションでのポーリングと TypedPolling 操作の両方を使用する方法の手順を説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [WCF サービス モデルを使用して SQL Server からのデータ変更のポーリングに基づいたメッセージを受信します。](../../adapters-and-accelerators/adapter-sql/receive-polling-based-data-changed-messages-from-sql-server-using-a-wcf-service.md)  
  
-   [厳密に型指定されたポーリング ベース データが変更されてから受信 WCF サービスのモデルを使用して SQL Server](../../adapters-and-accelerators/adapter-sql/receive-strongly-typed-polling-based-data-changed-sql-messages-with-wcf-service.md)  
  
## <a name="see-also"></a>参照  
[WCF サービス モデルを使用して SQL アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)