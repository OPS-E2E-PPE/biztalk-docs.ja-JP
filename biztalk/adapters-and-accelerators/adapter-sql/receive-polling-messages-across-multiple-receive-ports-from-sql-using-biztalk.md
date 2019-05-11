---
title: BizTalk Server を使用して SQL からの複数の受信ポートにメッセージ間でのポーリングの受信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 21cf4875-1c04-41cf-98f5-d1307987ca55
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 17f7be558dfcd5939836143e361f4b3a76850701
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368718"
---
# <a name="receive-polling-messages-across-multiple-receive-ports-from-sql-using-biztalk-server"></a>BizTalk Server を使用して SQL からの複数の受信ポートにメッセージ間でのポーリングの受信します。
2 つのポーリング操作を含む BizTalk アプリケーションを作成するシナリオを検討してください。 各ポーリング操作は、個別のテーブル、従業員とお客様同じデータベースからをポーリングします。 このようなアプリケーションを展開すると[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を作成する必要がある管理コンソールで、2 つの受信ポート。 それぞれの接続 URI の受信ポートになります。  
  
```  
mssql://<server_name>/<database_instance_name>/<datbase_name>  
```  
  
 どちらの受信ポートは、同じサーバー上の同じデータベースからポーリング メッセージを受信するが、接続 URI の両方に同じになります。 ただし、BizTalk アプリケーションでは、2 つの受信ポートと同じ接続 URI を持つことはできません。  
  
 2 つの BizTalk アプリケーションで同じデータベース (または、同じテーブルでも、データベース内) をポーリングするポートを受信アダプターのクライアントを有効にする、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]接続のプロパティを提供します。 **InboundID**します。 この接続プロパティの値を指定することができます。 受信 ID を追加すると、接続 URI が一意になります。 以下に例を示します。  
  
 Employee テーブルのポーリング メッセージを受信ポートの接続 URI を指定できます。  
  
```  
mssql://<server_name>/<database_instance_name>/<datbase_name>?InboundID=Employee  
```  
  
 同様に、Customer テーブルのポーリング メッセージを受信ポートの接続 URI を指定できます。  
  
```  
mssql://<server_name>/<database_instance_name>/<datbase_name>?InboundID=Customer  
```  
  
 追加することで、接続 Uri が一意になるため、 **InboundID**プロパティ、複数の受信ポートは、同じデータベースまたは 1 つの BizTalk アプリケーション内のテーブルをポーリングするようになりましたができます。  
  
> [!IMPORTANT]
>  指定することができます、 **InboundID**両方の接続プロパティ、**ポーリング**と**TypedPolling**操作。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server と SQL アダプタを使用して SQL Server をポーリング](../../adapters-and-accelerators/adapter-sql/poll-sql-server-using-the-sql-adapter-with-biztalk-server.md)