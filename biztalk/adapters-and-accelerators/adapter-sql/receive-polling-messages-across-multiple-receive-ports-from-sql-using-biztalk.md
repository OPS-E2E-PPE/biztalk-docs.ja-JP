---
title: "BizTalk Server を使用して SQL からの複数の受信ポートにメッセージ間でのポーリングの受信 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 21cf4875-1c04-41cf-98f5-d1307987ca55
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2be084ca9e0a90813a541563bf6f600ea277aec9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="receive-polling-messages-across-multiple-receive-ports-from-sql-using-biztalk-server"></a><span data-ttu-id="2ca3f-102">BizTalk Server を使用して SQL からの複数の受信ポートにメッセージ間でのポーリングの受信します。</span><span class="sxs-lookup"><span data-stu-id="2ca3f-102">Receive Polling Messages Across Multiple Receive Ports from SQL using BizTalk Server</span></span>
<span data-ttu-id="2ca3f-103">2 つのポーリング操作を含む BizTalk アプリケーションを作成するシナリオを検討してください。</span><span class="sxs-lookup"><span data-stu-id="2ca3f-103">Consider a scenario where you want to create a BizTalk application that includes two polling operations.</span></span> <span data-ttu-id="2ca3f-104">ポーリングの各操作は、別のテーブルに従業員とお客様同じデータベースからをポーリングします。</span><span class="sxs-lookup"><span data-stu-id="2ca3f-104">Each polling operation polls separate tables, Employee and Customer, from the same database.</span></span> <span data-ttu-id="2ca3f-105">このようなアプリケーションを展開するときに[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を作成する必要がある管理コンソールで、2 つの受信ポート。</span><span class="sxs-lookup"><span data-stu-id="2ca3f-105">When you deploy such an application in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you will need to create two receive ports.</span></span> <span data-ttu-id="2ca3f-106">各接続 URI の受信ポートになります。</span><span class="sxs-lookup"><span data-stu-id="2ca3f-106">The connection URI for each receive port will be:</span></span>  
  
```  
mssql://<server_name>/<database_instance_name>/<datbase_name>  
```  
  
 <span data-ttu-id="2ca3f-107">どちらの受信ポートが同じサーバー上の同じデータベースからポーリング メッセージの受信、両方の接続 URI は同じになります。</span><span class="sxs-lookup"><span data-stu-id="2ca3f-107">Because both receive ports are receiving polling messages from the same database on the same server, the connection URI for both will be the same.</span></span> <span data-ttu-id="2ca3f-108">ただし、BizTalk アプリケーションでは、2 つの受信ポートは同じ接続 URI を持つことはできません。</span><span class="sxs-lookup"><span data-stu-id="2ca3f-108">However, a BizTalk application cannot have two receive ports with the same connection URI.</span></span>  
  
 <span data-ttu-id="2ca3f-109">2 つの BizTalk アプリケーションで同じデータベース (または、データベース内の同じテーブルにも) をポーリングするポートを受信するアダプターのクライアントを有効にする、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]接続プロパティを提供**InboundID**です。</span><span class="sxs-lookup"><span data-stu-id="2ca3f-109">To enable adapter clients to have two receive ports that poll the same database (or even the same table in a database) in a BizTalk application, the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] provides a connection property, **InboundID**.</span></span> <span data-ttu-id="2ca3f-110">この接続プロパティのすべての値を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="2ca3f-110">You can specify any value for this connection property.</span></span> <span data-ttu-id="2ca3f-111">受信 ID を追加すると、接続 URI が一意になります。</span><span class="sxs-lookup"><span data-stu-id="2ca3f-111">By adding the inbound ID, a connection URI becomes unique.</span></span> <span data-ttu-id="2ca3f-112">例:</span><span class="sxs-lookup"><span data-stu-id="2ca3f-112">For example:</span></span>  
  
 <span data-ttu-id="2ca3f-113">Employee テーブルに対してポーリング メッセージを受信ポートの接続 URI を指定できます。</span><span class="sxs-lookup"><span data-stu-id="2ca3f-113">The connection URI for the port receiving polling messages for the Employee table can be:</span></span>  
  
```  
mssql://<server_name>/<database_instance_name>/<datbase_name>?InboundID=Employee  
```  
  
 <span data-ttu-id="2ca3f-114">同様に、Customer テーブルのポーリング メッセージを受信ポートの接続 URI を指定できます。</span><span class="sxs-lookup"><span data-stu-id="2ca3f-114">Similarly, the connection URI for the port receiving polling messages for the Customer table can be:</span></span>  
  
```  
mssql://<server_name>/<database_instance_name>/<datbase_name>?InboundID=Customer  
```  
  
 <span data-ttu-id="2ca3f-115">追加することで、接続 Uri が一意になるため、 **InboundID**プロパティ、複数の受信ポートが、同じデータベースまたは 1 つの BizTalk アプリケーション内のテーブルをポーリングするようになりました持つことができます。</span><span class="sxs-lookup"><span data-stu-id="2ca3f-115">Because the connection URIs become unique by adding the **InboundID** property, you can now have multiple receive ports polling the same database or table in a single BizTalk application.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2ca3f-116">指定することができます、 **InboundID**両方の接続プロパティ、**ポーリング**と**TypedPolling**操作します。</span><span class="sxs-lookup"><span data-stu-id="2ca3f-116">You can choose to specify the **InboundID** connection property for both the **Polling** and **TypedPolling** operations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ca3f-117">参照</span><span class="sxs-lookup"><span data-stu-id="2ca3f-117">See Also</span></span>  
 [<span data-ttu-id="2ca3f-118">BizTalk Server と SQL アダプタを使用して SQL サーバーにポーリング</span><span class="sxs-lookup"><span data-stu-id="2ca3f-118">Poll SQL Server using the SQL Adapter with BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/poll-sql-server-using-the-sql-adapter-with-biztalk-server.md)