---
title: BizTalk Server と SQL アダプタを使用してポーリング SQL Server |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eef9a4b4-552d-4552-b318-1deab506bad9
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 31e631a966ffee632e6c866a962c4fe47b2f1025
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223090"
---
# <a name="poll-sql-server-using-the-sql-adapter-with-biztalk-server"></a>BizTalk Server と SQL アダプタを使用して SQL サーバーにポーリング
構成することができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を SQL Server からデータ変更のポーリングに基づいたメッセージを受信します。 データベースをポーリングするアダプターを実行するポーリング ステートメントを指定することができます。 ポーリング ステートメントには、SELECT ステートメントまたは結果セットを返すストアド プロシージャを使用できます。 ポーリングのメッセージの種類に基づいて、アダプターは、ポーリングの 3 つの方法を公開します。  
  
-   **ポーリング**です。 この操作は、ポーリング メッセージの一部としてデータ セットを返します。 デザイン時に、ポーリングされているデータベース オブジェクトのスキーマは使用できません。 代わりに、スキーマは、実行時にポーリング メッセージの一部として。  
  
-   **TypedPolling**です。 この操作は、厳密に型指定されたポーリング メッセージを返します。 デザイン時に、データベース オブジェクトのスキーマも使用できます。 ポーリング メッセージから別の操作の場合も、別のスキーマの特定の要素をマップする場合のポーリングを行うには、この操作を使用する必要があります。  
  
-   **XmlPolling**です。 この操作は、XML メッセージとしてポーリング メッセージを返します。 SELECT ステートメントや XML メッセージとしてデータを返す FOR XML 句を使用するストアド プロシージャを使用する場合は、この操作を使用する必要があります。 FOR XML 句の詳細については、次を参照してください。 [FOR XML (SQL Server)](https://msdn.microsoft.com/library/ms178107.aspx)です。 
  
 これらのポーリング処理の詳細については、次を参照してください。[ポーリングのサポート](https://msdn.microsoft.com/library/dd788416.aspx)です。  
  
> [!NOTE]
>  [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]アダプター クライアントには同じデータベースまたはテーブルの 1 つ以上のポーリングや TypedPolling 操作を 1 つの BizTalk アプリケーションを有効にします。 このようなシナリオをサポートするために、アダプターに一意の ID が含まれています — **InboundID**— 接続 URI にします。 接続 URI に追加すると、この ID には一意になります、1 つの BizTalk アプリケーションで複数のポーリング操作できるようにします。  
  
 このセクションのトピックでは、BizTalk アプリケーションでのポーリング、TypedPolling、および XmlPolling の使用方法について説明します。 使用する方法についても説明、 **InboundID**接続プロパティです。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [SQL Server から BizTalk Server を使用して、データ変更のポーリングに基づいたメッセージを受信します。](../../adapters-and-accelerators/adapter-sql/receive-polling-based-data-changed-messages-from-sql-server-using-biztalk.md)  
  
-   [厳密に型指定されたポーリング ベース データが変更されてから受信 BizTalk Server を使用して SQL Server](../../adapters-and-accelerators/adapter-sql/receive-strongly-typed-polling-based-data-changed-messages-from-sql-in-biztalk.md)  
  
-   [BizTalk Server を使用して SQL からポーリング メッセージを使用して SELECT ステートメントで FOR XML 句の受信します。](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-using-select-with-for-xml-clause-with-the-sql-adapter.md)  
  
-   [BizTalk Server を使用して SQL からの複数の受信ポートにメッセージ間でのポーリングの受信します。](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-across-multiple-receive-ports-from-sql-using-biztalk.md)  
  
## <a name="see-also"></a>参照  
[SQL アダプターを使用して BizTalk アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)