---
title: "Oracle データベース アダプターでトランザクションの処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 971c2fba-640c-4ae5-9ab3-2d8227c1627d
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d45355100e728220745620e1c0df3552f523f649
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="handle-transactions-with-the-oracle-database-adapter"></a><span data-ttu-id="28795-102">Oracle データベース アダプターでトランザクションを処理します。</span><span class="sxs-lookup"><span data-stu-id="28795-102">Handle Transactions with the Oracle Database adapter</span></span>
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]<span data-ttu-id="28795-103">Oracle データベースで操作を実行中のトランザクションを開始しません。</span><span class="sxs-lookup"><span data-stu-id="28795-103"> does not initiate a transaction while performing an operation on the Oracle database.</span></span> <span data-ttu-id="28795-104">代わりに、アダプターは、アダプターのクライアントによって提供されるトランザクション コンテキストを使用して操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="28795-104">Instead, the adapter performs the operations using the transaction context provided by the adapter clients.</span></span> <span data-ttu-id="28795-105">使用してトランザクションで操作を実行するために、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]、する必要があります。</span><span class="sxs-lookup"><span data-stu-id="28795-105">In order to perform operations in a transaction using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], you must:</span></span>  
  
-   <span data-ttu-id="28795-106">アダプターのクライアントのトランザクションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="28795-106">Enable transactions in the adapter clients.</span></span> <span data-ttu-id="28795-107">例については、トランザクションを有効にする[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]を選択する必要があります、 **Use-transaction**  チェック ボックス、**トランザクション**の領域、**メッセージ**タブに移動して、Wcf-custom または Wcf-oracledb ポートです。</span><span class="sxs-lookup"><span data-stu-id="28795-107">For example, to enable transactions in [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)], you must select the **Use Transaction** check box in the **Transactions** area of the **Messages** tab for a WCF-Custom or WCF-OracleDB port.</span></span>  
  
-   <span data-ttu-id="28795-108">値を設定、 **UseAmbientTransaction**にプロパティのバインド**True**アダプターでします。</span><span class="sxs-lookup"><span data-stu-id="28795-108">Set the value of the **UseAmbientTransaction** binding property to **True** in the adapter.</span></span> <span data-ttu-id="28795-109">バインディング プロパティの詳細については、次を参照してください。 [Oracle データベースのバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)です。</span><span class="sxs-lookup"><span data-stu-id="28795-109">For more information about the binding property, see [Configure the binding properties for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="28795-110">トランザクションを実行する Oracle データベースで、アダプターを使用するインストール必要がありますが、 **Microsoft Transaction Server のサービスの Oracle**コンポーネント、アダプターを実行しているコンピューターで、Oracle クライアントをインストールするときに、クライアントです。</span><span class="sxs-lookup"><span data-stu-id="28795-110">To use the adapter to perform transactions on the Oracle database, you must have installed the **Oracle Services For Microsoft Transaction Server** component, while installing the Oracle client, on the computer running the adapter client.</span></span>  
  
## <a name="transactions-in-the-outbound-operations"></a><span data-ttu-id="28795-111">送信操作のトランザクション</span><span class="sxs-lookup"><span data-stu-id="28795-111">Transactions in the Outbound Operations</span></span>  
 <span data-ttu-id="28795-112">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]単一のトランザクションで送信操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="28795-112">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] performs an outbound operation in a single transaction.</span></span> <span data-ttu-id="28795-113">複合操作は、すべての操作を実行して、1 つのトランザクションではなく異なる ODP.NET 接続を使用します。</span><span class="sxs-lookup"><span data-stu-id="28795-113">For composite operations, all the operations are performed in a single transaction but using different ODP.NET connections.</span></span> <span data-ttu-id="28795-114">送信側に表示される操作の詳細については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[アダプター画面 Oracle メタデータをどのように?](https://msdn.microsoft.com/library/cc185310(v=bts.10).aspx)です。</span><span class="sxs-lookup"><span data-stu-id="28795-114">For more information about the outbound operations surfaced by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [How does the Adapter Surface Oracle Metadata?](https://msdn.microsoft.com/library/cc185310(v=bts.10).aspx).</span></span>  
  
## <a name="transactions-in-the-inbound-operations"></a><span data-ttu-id="28795-115">受信操作のトランザクション</span><span class="sxs-lookup"><span data-stu-id="28795-115">Transactions in the Inbound Operations</span></span>  
 <span data-ttu-id="28795-116">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]次の 2 つの受信操作を公開します。</span><span class="sxs-lookup"><span data-stu-id="28795-116">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] exposes the following two inbound operations:</span></span>  
  
-   <span data-ttu-id="28795-117">**ポーリング**: ポーリング ステートメントおよび (指定した場合)、ポーリング後ステートメントが実行されるトランザクションでは、一方、別のトランザクションでポーリングされたデータの使用可能なステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="28795-117">**Polling**: The polling statement and the post-poll statement (if specified) are executed in a transaction, whereas, the polled data available statement is executed in a different transaction.</span></span> <span data-ttu-id="28795-118">同様に、ポーリング ステートメントとポーリング後ステートメントは、実行同じ ODP.NET 接続を使用して一方、ODP.NET は別の接続を使用してポーリングされたデータの使用可能なステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="28795-118">Similarly, the polling statement and the post-poll statement are executed using the same ODP.NET connection, whereas, the polled data available statement is executed using a different ODP.NET connection.</span></span>  
  
-   <span data-ttu-id="28795-119">**通知**: 通知操作は 1 つの ODP.NET 接続を使用して、トランザクションで実行します。</span><span class="sxs-lookup"><span data-stu-id="28795-119">**Notification**: The notification operation is performed in a transaction using a single ODP.NET connection.</span></span>  
  
 <span data-ttu-id="28795-120">受信側に表示される操作の詳細については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[アダプター画面 Oracle メタデータをどのようにしますか?](https://msdn.microsoft.com/library/cc185310(v=bts.10).aspx)です。</span><span class="sxs-lookup"><span data-stu-id="28795-120">For more information about the inbound operations surfaced by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [How does the Adapter Surface Oracle Metadata?](https://msdn.microsoft.com/library/cc185310(v=bts.10).aspx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28795-121">参照</span><span class="sxs-lookup"><span data-stu-id="28795-121">See Also</span></span>  
 [<span data-ttu-id="28795-122">BizTalk Adapter 用 Oracle Database の概要</span><span class="sxs-lookup"><span data-stu-id="28795-122">Overview of BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)