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
# <a name="receive-polling-messages-across-multiple-receive-ports-from-sql-using-biztalk-server"></a><span data-ttu-id="9c2a1-102">BizTalk Server を使用して SQL からの複数の受信ポートにメッセージ間でのポーリングの受信します。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-102">Receive Polling Messages Across Multiple Receive Ports from SQL using BizTalk Server</span></span>
<span data-ttu-id="9c2a1-103">2 つのポーリング操作を含む BizTalk アプリケーションを作成するシナリオを検討してください。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-103">Consider a scenario where you want to create a BizTalk application that includes two polling operations.</span></span> <span data-ttu-id="9c2a1-104">各ポーリング操作は、個別のテーブル、従業員とお客様同じデータベースからをポーリングします。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-104">Each polling operation polls separate tables, Employee and Customer, from the same database.</span></span> <span data-ttu-id="9c2a1-105">このようなアプリケーションを展開すると[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を作成する必要がある管理コンソールで、2 つの受信ポート。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-105">When you deploy such an application in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you will need to create two receive ports.</span></span> <span data-ttu-id="9c2a1-106">それぞれの接続 URI の受信ポートになります。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-106">The connection URI for each receive port will be:</span></span>  
  
```  
mssql://<server_name>/<database_instance_name>/<datbase_name>  
```  
  
 <span data-ttu-id="9c2a1-107">どちらの受信ポートは、同じサーバー上の同じデータベースからポーリング メッセージを受信するが、接続 URI の両方に同じになります。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-107">Because both receive ports are receiving polling messages from the same database on the same server, the connection URI for both will be the same.</span></span> <span data-ttu-id="9c2a1-108">ただし、BizTalk アプリケーションでは、2 つの受信ポートと同じ接続 URI を持つことはできません。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-108">However, a BizTalk application cannot have two receive ports with the same connection URI.</span></span>  
  
 <span data-ttu-id="9c2a1-109">2 つの BizTalk アプリケーションで同じデータベース (または、同じテーブルでも、データベース内) をポーリングするポートを受信アダプターのクライアントを有効にする、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]接続のプロパティを提供します。 **InboundID**します。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-109">To enable adapter clients to have two receive ports that poll the same database (or even the same table in a database) in a BizTalk application, the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] provides a connection property, **InboundID**.</span></span> <span data-ttu-id="9c2a1-110">この接続プロパティの値を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-110">You can specify any value for this connection property.</span></span> <span data-ttu-id="9c2a1-111">受信 ID を追加すると、接続 URI が一意になります。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-111">By adding the inbound ID, a connection URI becomes unique.</span></span> <span data-ttu-id="9c2a1-112">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-112">For example:</span></span>  
  
 <span data-ttu-id="9c2a1-113">Employee テーブルのポーリング メッセージを受信ポートの接続 URI を指定できます。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-113">The connection URI for the port receiving polling messages for the Employee table can be:</span></span>  
  
```  
mssql://<server_name>/<database_instance_name>/<datbase_name>?InboundID=Employee  
```  
  
 <span data-ttu-id="9c2a1-114">同様に、Customer テーブルのポーリング メッセージを受信ポートの接続 URI を指定できます。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-114">Similarly, the connection URI for the port receiving polling messages for the Customer table can be:</span></span>  
  
```  
mssql://<server_name>/<database_instance_name>/<datbase_name>?InboundID=Customer  
```  
  
 <span data-ttu-id="9c2a1-115">追加することで、接続 Uri が一意になるため、 **InboundID**プロパティ、複数の受信ポートは、同じデータベースまたは 1 つの BizTalk アプリケーション内のテーブルをポーリングするようになりましたができます。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-115">Because the connection URIs become unique by adding the **InboundID** property, you can now have multiple receive ports polling the same database or table in a single BizTalk application.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9c2a1-116">指定することができます、 **InboundID**両方の接続プロパティ、**ポーリング**と**TypedPolling**操作。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-116">You can choose to specify the **InboundID** connection property for both the **Polling** and **TypedPolling** operations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c2a1-117">参照</span><span class="sxs-lookup"><span data-stu-id="9c2a1-117">See Also</span></span>  
 [<span data-ttu-id="9c2a1-118">BizTalk Server と SQL アダプタを使用して SQL Server をポーリング</span><span class="sxs-lookup"><span data-stu-id="9c2a1-118">Poll SQL Server using the SQL Adapter with BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/poll-sql-server-using-the-sql-adapter-with-biztalk-server.md)