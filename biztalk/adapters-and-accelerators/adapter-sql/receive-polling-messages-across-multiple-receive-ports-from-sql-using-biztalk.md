---
title: BizTalk Server を使用して SQL からの複数の受信ポートにメッセージ間でのポーリングの受信 |Microsoft ドキュメント
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
ms.openlocfilehash: 2be084ca9e0a90813a541563bf6f600ea277aec9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223962"
---
# <a name="receive-polling-messages-across-multiple-receive-ports-from-sql-using-biztalk-server"></a>BizTalk Server を使用して SQL からの複数の受信ポートにメッセージ間でのポーリングの受信します。
2 つのポーリング操作を含む BizTalk アプリケーションを作成するシナリオを検討してください。 ポーリングの各操作は、別のテーブルに従業員とお客様同じデータベースからをポーリングします。 このようなアプリケーションを展開するときに[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を作成する必要がある管理コンソールで、2 つの受信ポート。 各接続 URI の受信ポートになります。  
  
```  
mssql://<server_name>/<database_instance_name>/<datbase_name>  
```  
  
 どちらの受信ポートが同じサーバー上の同じデータベースからポーリング メッセージの受信、両方の接続 URI は同じになります。 ただし、BizTalk アプリケーションでは、2 つの受信ポートは同じ接続 URI を持つことはできません。  
  
 2 つの BizTalk アプリケーションで同じデータベース (または、データベース内の同じテーブルにも) をポーリングするポートを受信するアダプターのクライアントを有効にする、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]接続プロパティを提供**InboundID**です。 この接続プロパティのすべての値を指定することができます。 受信 ID を追加すると、接続 URI が一意になります。 例:  
  
 Employee テーブルに対してポーリング メッセージを受信ポートの接続 URI を指定できます。  
  
```  
mssql://<server_name>/<database_instance_name>/<datbase_name>?InboundID=Employee  
```  
  
 同様に、Customer テーブルのポーリング メッセージを受信ポートの接続 URI を指定できます。  
  
```  
mssql://<server_name>/<database_instance_name>/<datbase_name>?InboundID=Customer  
```  
  
 追加することで、接続 Uri が一意になるため、 **InboundID**プロパティ、複数の受信ポートが、同じデータベースまたは 1 つの BizTalk アプリケーション内のテーブルをポーリングするようになりました持つことができます。  
  
> [!IMPORTANT]
>  指定することができます、 **InboundID**両方の接続プロパティ、**ポーリング**と**TypedPolling**操作します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server と SQL アダプタを使用して SQL サーバーにポーリング](../../adapters-and-accelerators/adapter-sql/poll-sql-server-using-the-sql-adapter-with-biztalk-server.md)