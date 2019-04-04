---
title: WCF サービス モデルで、SQL アダプターを使用して SQL Server をポーリング |Microsoft Docs
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
ms.openlocfilehash: eb3bbd42c732f3377c5823831b9507bbeb0c83bf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022312"
---
# <a name="poll-sql-server-using-the-sql-adapter-with-wcf-service-model"></a>SQL Server をポーリングする WCF サービス モデルでの SQL アダプタの使用
構成することができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を SQL Server からのポーリングに基づいたデータ変更メッセージを受信します。 データベースをポーリングするアダプターを実行するポーリング ステートメントを指定することができます。 ポーリング ステートメントには、SELECT ステートメントまたはストアド プロシージャを返す結果セットを使用できます。 受信したメッセージのポーリングの種類に基づいて、アダプターは、さまざまなポーリング操作を公開します。  
  
- **ポーリング**します。 この操作は、ポーリング メッセージの一部としてデータ セットを返します。  
  
- **TypedPolling**します。 この操作は、厳密に型指定されたポーリング メッセージを返します。  
  
- **XmlPolling**します。 この操作は、XML メッセージとしてポーリング メッセージを返します。 SELECT ステートメントまたは XML メッセージとしてデータを返す FOR XML 句を使用するストアド プロシージャを使用する場合、この操作を使用する必要があります。 [FOR XML 句](https://docs.microsoft.com/sql/relational-databases/xml/for-xml-sql-server)詳細情報を提供します。 
  
  これらのポーリング操作の詳細については、[SQL アダプターを使用して SQL Server でのポーリング](../../adapters-and-accelerators/adapter-sql/polling-in-sql-server-using-the-sql-adapter.md)を参照してください。  
  
> [!NOTE]
>  [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]アダプター クライアントは同じデータベースまたはテーブルの 1 つ以上のポーリングまたは TypedPolling 操作を 1 つのアプリケーションに使用できます。 アダプターには、このようなシナリオをサポートするには、一意の ID が含まれています — **InboundID**— 接続 URI。 この ID は、接続、URI に追加されたときに、一意で単一のアプリケーションで複数のポーリング操作できるようにできます。  
  
 このセクションのトピックでは、.NET アプリケーションでのポーリングと TypedPolling 操作を使用する方法について説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [WCF サービス モデルを使用して SQL Server からのポーリングに基づいたデータ変更メッセージを受信します。](../../adapters-and-accelerators/adapter-sql/receive-polling-based-data-changed-messages-from-sql-server-using-a-wcf-service.md)  
  
-   [WCF サービス モデルを使用して SQL Server からのポーリングに基づいたデータ変更メッセージを厳密に型指定の受信します。](../../adapters-and-accelerators/adapter-sql/receive-strongly-typed-polling-based-data-changed-sql-messages-with-wcf-service.md)  
  
## <a name="see-also"></a>参照  
[WCF サービス モデルを使用して SQL アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)