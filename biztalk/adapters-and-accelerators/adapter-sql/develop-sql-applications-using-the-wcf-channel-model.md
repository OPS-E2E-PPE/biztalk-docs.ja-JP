---
title: "WCF チャネル モデルを使用して SQL アプリケーションを開発 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 11df5cc2-b532-45a8-9055-d05f4704a6e5
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b503b0766a4848e05c9361fb151196ee43afd81
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="develop-sql-applications-using-the-wcf-channel-model"></a><span data-ttu-id="a5b78-102">WCF チャネル モデルを使用して SQL アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="a5b78-102">Develop SQL applications using the WCF Channel Model</span></span>
<span data-ttu-id="a5b78-103">使用することができます、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]チャネル モデルを使用する、 [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] SQL サーバー バインドで作成されたチャネル インスタンス経由で直接 XML メッセージを送信することによってです。</span><span class="sxs-lookup"><span data-stu-id="a5b78-103">You can use the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] channel model to consume the [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] by sending XML messages directly over a channel instance created with the SQL Server Binding.</span></span>  
  
 <span data-ttu-id="a5b78-104">厳密に型指定されたクラスと、WCF サービス モデルを公開するメソッドを使用する場合より、WCF チャネル モデルを使用する利点の 1 つは、チャネル モデルが SQL データベースで実行する操作をより詳細に制御を提供することです。</span><span class="sxs-lookup"><span data-stu-id="a5b78-104">One advantage of using the WCF channel model over using the strongly-typed classes and methods that the WCF service model exposes is that the channel model provides more fine-grained control over the operations that you perform on the SQL database.</span></span> <span data-ttu-id="a5b78-105">このコントロールは、ファクトのことで、WCF チャネル モデルを直接制御するチャネル経由で送信するメッセージの内容から取得されます。</span><span class="sxs-lookup"><span data-stu-id="a5b78-105">This control comes from the fact that in the WCF channel model, you directly control the contents of the messages that you send over the channel.</span></span>  
  
 <span data-ttu-id="a5b78-106">特定のシナリオでは、この余分なレベルの制御と役に立つことがあります。</span><span class="sxs-lookup"><span data-stu-id="a5b78-106">In certain scenarios, this extra level of control can be beneficial.</span></span> <span data-ttu-id="a5b78-107">たとえば、WCF チャネル モデルを使用して、テーブルの更新操作を実行するときに、ターゲット行の列をメッセージを渡すテンプレートの更新からの列を省略することでに更新できます選択的にします。</span><span class="sxs-lookup"><span data-stu-id="a5b78-107">For example, when you use the WCF channel model to perform an Update operation on a table, you can selectively update columns in the target rows by omitting columns from the update template that you pass in the message.</span></span> <span data-ttu-id="a5b78-108">必要な列のみが"nillable = false"、WSDL でします。</span><span class="sxs-lookup"><span data-stu-id="a5b78-108">The only columns that are required are those with “nillable=false” in the WSDL.</span></span> <span data-ttu-id="a5b78-109">によって公開されている、update メソッドを[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]クライアントは、テーブルのスキーマ内のすべての列を含むテンプレートに対してレコードの厳密に型指定されたパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="a5b78-109">The update method exposed by a [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] client uses a strongly-typed record parameter for the template that includes every column in the table schema.</span></span>  
  
 <span data-ttu-id="a5b78-110">このトピックのセクションでは、操作を実行する方法を説明する、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] WCF チャネル モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="a5b78-110">The sections in this topic explain how to perform operations on the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] by using the WCF channel model.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a5b78-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a5b78-111">In This Section</span></span>  
  
-   [<span data-ttu-id="a5b78-112">SQL アダプタを使用して WCF チャネル モデルの概要</span><span class="sxs-lookup"><span data-stu-id="a5b78-112">Overview of the WCF channel model with the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-channel-model-with-the-sql-adapter.md)  
  
-   [<span data-ttu-id="a5b78-113">SQL アダプターを使用して、チャネルを作成します。</span><span class="sxs-lookup"><span data-stu-id="a5b78-113">Create a channel using the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/create-a-channel-using-the-sql-adapter.md)  
  
-   [<span data-ttu-id="a5b78-114">WCF チャネル モデルを使用して SQL でのテーブルに対して挿入操作の実行します。</span><span class="sxs-lookup"><span data-stu-id="a5b78-114">Run an Insert Operation on a Table in SQL using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-sql/run-an-insert-operation-on-a-table-in-sql-using-the-wcf-channel-model.md)  
  
-   [<span data-ttu-id="a5b78-115">WCF チャネル モデルを使用して SQL Server からデータ変更のポーリングに基づいたメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="a5b78-115">Receive Polling-based Data-changed Messages from SQL Server by Using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-sql/receive-polling-based-data-changed-messages-from-sql-server-using-a-wcf-channel.md)  
  
## <a name="see-also"></a><span data-ttu-id="a5b78-116">参照</span><span class="sxs-lookup"><span data-stu-id="a5b78-116">See Also</span></span>  
[<span data-ttu-id="a5b78-117">SQL アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="a5b78-117">Develop your SQL applications</span></span>](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md)