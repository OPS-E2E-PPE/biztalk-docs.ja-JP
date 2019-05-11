---
title: WCF チャネル モデルを使用して SQL アプリケーションの開発 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 11df5cc2-b532-45a8-9055-d05f4704a6e5
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0bf7b12a076e88cd59dcc463dd8c10bd0817e612
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65369867"
---
# <a name="develop-sql-applications-using-the-wcf-channel-model"></a><span data-ttu-id="16477-102">WCF チャネル モデルを使用して SQL アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="16477-102">Develop SQL applications using the WCF Channel Model</span></span>
<span data-ttu-id="16477-103">使用することができます、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]チャネル モデルを使用する、 [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] SQL サーバー バインドで作成されたチャネル インスタンス経由で直接 XML メッセージを送信することです。</span><span class="sxs-lookup"><span data-stu-id="16477-103">You can use the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] channel model to consume the [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] by sending XML messages directly over a channel instance created with the SQL Server Binding.</span></span>  
  
 <span data-ttu-id="16477-104">WCF チャネル モデルを使用して、厳密に型指定されたクラスと、WCF サービス モデルを公開するメソッドを使用する利点の 1 つは、チャネル モデルが SQL データベースで実行する操作のきめの細かい制御を提供します。</span><span class="sxs-lookup"><span data-stu-id="16477-104">One advantage of using the WCF channel model over using the strongly-typed classes and methods that the WCF service model exposes is that the channel model provides more fine-grained control over the operations that you perform on the SQL database.</span></span> <span data-ttu-id="16477-105">このコントロールは、ファクトのことで WCF チャネル モデルを直接制御チャネル経由で送信するメッセージの内容から取得されます。</span><span class="sxs-lookup"><span data-stu-id="16477-105">This control comes from the fact that in the WCF channel model, you directly control the contents of the messages that you send over the channel.</span></span>  
  
 <span data-ttu-id="16477-106">特定のシナリオでこの追加レベルの制御はパフォーマンスを向上することはできます。</span><span class="sxs-lookup"><span data-stu-id="16477-106">In certain scenarios, this extra level of control can be beneficial.</span></span> <span data-ttu-id="16477-107">たとえば、WCF チャネル モデルを使用して、テーブルに対する Update 操作を実行するときに選択的に更新できますターゲット行内の列、メッセージを渡すテンプレートの更新からの列を省略することで。</span><span class="sxs-lookup"><span data-stu-id="16477-107">For example, when you use the WCF channel model to perform an Update operation on a table, you can selectively update columns in the target rows by omitting columns from the update template that you pass in the message.</span></span> <span data-ttu-id="16477-108">必要な列のみが"nillable = false"、WSDL でします。</span><span class="sxs-lookup"><span data-stu-id="16477-108">The only columns that are required are those with “nillable=false” in the WSDL.</span></span> <span data-ttu-id="16477-109">によって公開されている、update メソッドを[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]クライアントで、テーブルのスキーマ内のすべての列を含むテンプレートのレコードの厳密に型指定されたパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="16477-109">The update method exposed by a [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] client uses a strongly-typed record parameter for the template that includes every column in the table schema.</span></span>  
  
 <span data-ttu-id="16477-110">このトピックのセクションでは、操作を実行する方法を説明します、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] WCF チャネル モデルを使用しています。</span><span class="sxs-lookup"><span data-stu-id="16477-110">The sections in this topic explain how to perform operations on the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] by using the WCF channel model.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="16477-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="16477-111">In This Section</span></span>  
  
-   [<span data-ttu-id="16477-112">SQL アダプターを使用した WCF チャネル モデルの概要</span><span class="sxs-lookup"><span data-stu-id="16477-112">Overview of the WCF channel model with the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-channel-model-with-the-sql-adapter.md)  
  
-   [<span data-ttu-id="16477-113">SQL アダプタを使用するチャネルを作成します。</span><span class="sxs-lookup"><span data-stu-id="16477-113">Create a channel using the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/create-a-channel-using-the-sql-adapter.md)  
  
-   [<span data-ttu-id="16477-114">WCF チャネル モデルを使用して SQL テーブルで挿入操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="16477-114">Run an Insert Operation on a Table in SQL using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-sql/run-an-insert-operation-on-a-table-in-sql-using-the-wcf-channel-model.md)  
  
-   [<span data-ttu-id="16477-115">WCF チャネル モデルを使用して SQL Server からのポーリングに基づいたデータ変更メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="16477-115">Receive Polling-based Data-changed Messages from SQL Server by Using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-sql/receive-polling-based-data-changed-messages-from-sql-server-using-a-wcf-channel.md)  
  
## <a name="see-also"></a><span data-ttu-id="16477-116">参照</span><span class="sxs-lookup"><span data-stu-id="16477-116">See Also</span></span>  
[<span data-ttu-id="16477-117">SQL アプリケーションを開発する</span><span class="sxs-lookup"><span data-stu-id="16477-117">Develop your SQL applications</span></span>](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md)