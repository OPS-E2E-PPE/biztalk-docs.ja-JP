---
title: BizTalk Server と SQL アダプタを使用して SQL Server をポーリング |Microsoft Docs
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
ms.openlocfilehash: f6fb95d5d070e53ae21e74ee101c04608b6599c5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368487"
---
# <a name="poll-sql-server-using-the-sql-adapter-with-biztalk-server"></a>BizTalk Server と SQL アダプタを使用して SQL Server をポーリング
構成することができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を SQL Server からのポーリングに基づいたデータ変更メッセージを受信します。 データベースをポーリングするアダプターを実行するポーリング ステートメントを指定することができます。 ポーリング ステートメントには、SELECT ステートメントまたはストアド プロシージャを返す結果セットを使用できます。 受信したメッセージのポーリングの種類に基づいて、アダプターは、ポーリングの 3 つの方法を公開します。  
  
- **ポーリング**します。 この操作は、ポーリング メッセージの一部としてデータ セットを返します。 デザイン時に、ポーリングされているデータベース オブジェクトのスキーマは使用できません。 代わりに、スキーマが使用可能な実行時のポーリング メッセージの一部として。  
  
- **TypedPolling**します。 この操作は、厳密に型指定されたポーリング メッセージを返します。 デザイン時に、データベース オブジェクトのスキーマも使用できます。 別の操作である可能性がある別のスキーマにポーリング メッセージから特定の要素をマップする場合をポーリングするためには、この操作を使用する必要があります。  
  
- **XmlPolling**します。 この操作は、XML メッセージとしてポーリング メッセージを返します。 SELECT ステートメントまたは XML メッセージとしてデータを返す FOR XML 句を使用するストアド プロシージャを使用する場合、この操作を使用する必要があります。 FOR XML 句の詳細については、次を参照してください。 [FOR XML (SQL Server)](https://msdn.microsoft.com/library/ms178107.aspx)します。 
  
  これらのポーリング操作の詳細については、次を参照してください。[のポーリング サポート](https://msdn.microsoft.com/library/dd788416.aspx)します。  
  
> [!NOTE]
>  [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]によりアダプターでクライアントに、同じデータベースまたはテーブルの 1 つ以上のポーリングや TypedPolling 操作を 1 つの BizTalk アプリケーションがあります。 アダプターには、このようなシナリオをサポートするには、一意の ID が含まれています — **InboundID**— 接続 URI。 接続 URI に追加されたときに、この ID になります一意、単一の BizTalk アプリケーションで複数のポーリング操作できるようにします。  
  
 このセクションのトピックでは、ポーリングや TypedPolling、XmlPolling を BizTalk アプリケーションで使用する方法について説明します。 このセクションでは、使用する方法についても説明します、 **InboundID**接続プロパティです。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [BizTalk Server を使用して SQL Server からのポーリングに基づいたデータ変更メッセージを受信します。](../../adapters-and-accelerators/adapter-sql/receive-polling-based-data-changed-messages-from-sql-server-using-biztalk.md)  
  
-   [BizTalk Server を使用して SQL Server からのポーリングに基づいたデータ変更メッセージを厳密に型指定の受信します。](../../adapters-and-accelerators/adapter-sql/receive-strongly-typed-polling-based-data-changed-messages-from-sql-in-biztalk.md)  
  
-   [BizTalk Server を使用して SQL からのポーリング メッセージを使用して SELECT ステートメントと FOR XML 句の受信します。](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-using-select-with-for-xml-clause-with-the-sql-adapter.md)  
  
-   [BizTalk Server を使用して SQL からの複数の受信ポートにメッセージ間でのポーリングの受信します。](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-across-multiple-receive-ports-from-sql-using-biztalk.md)  
  
## <a name="see-also"></a>参照  
[SQL アダプターを使用して BizTalk アプリケーションを開発する](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)