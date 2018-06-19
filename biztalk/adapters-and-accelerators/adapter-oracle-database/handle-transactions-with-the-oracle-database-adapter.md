---
title: Oracle データベース アダプターでトランザクションの処理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 971c2fba-640c-4ae5-9ab3-2d8227c1627d
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5072a49c9edc5dc8ce03ec819d6042b640b94a47
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26005707"
---
# <a name="handle-transactions-with-the-oracle-database-adapter"></a><span data-ttu-id="144a6-102">Oracle データベース アダプターでトランザクションを処理します。</span><span class="sxs-lookup"><span data-stu-id="144a6-102">Handle Transactions with the Oracle Database adapter</span></span>
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]<span data-ttu-id="144a6-103">Oracle データベースで操作を実行中のトランザクションを開始しません。</span><span class="sxs-lookup"><span data-stu-id="144a6-103"> does not initiate a transaction while performing an operation on the Oracle database.</span></span> <span data-ttu-id="144a6-104">代わりに、アダプターは、アダプターのクライアントによって提供されるトランザクション コンテキストを使用して操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="144a6-104">Instead, the adapter performs the operations using the transaction context provided by the adapter clients.</span></span> <span data-ttu-id="144a6-105">使用してトランザクションで操作を実行するために、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]、する必要があります。</span><span class="sxs-lookup"><span data-stu-id="144a6-105">In order to perform operations in a transaction using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], you must:</span></span>  
  
-   <span data-ttu-id="144a6-106">アダプターのクライアントのトランザクションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="144a6-106">Enable transactions in the adapter clients.</span></span> <span data-ttu-id="144a6-107">たとえば、BizTalk Server のトランザクションを有効にする必要がありますを選択する、 **Use-transaction**  チェック ボックス、**トランザクション**の領域、**メッセージ**WCF カスタム タブまたはWcf-oracledb ポートです。</span><span class="sxs-lookup"><span data-stu-id="144a6-107">For example, to enable transactions in BizTalk Server, you must select the **Use Transaction** check box in the **Transactions** area of the **Messages** tab for a WCF-Custom or WCF-OracleDB port.</span></span>  
  
-   <span data-ttu-id="144a6-108">値を設定、 **UseAmbientTransaction**にプロパティのバインド**True**アダプターでします。</span><span class="sxs-lookup"><span data-stu-id="144a6-108">Set the value of the **UseAmbientTransaction** binding property to **True** in the adapter.</span></span> <span data-ttu-id="144a6-109">バインディング プロパティの詳細については、次を参照してください。 [Oracle データベースのバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)です。</span><span class="sxs-lookup"><span data-stu-id="144a6-109">For more information about the binding property, see [Configure the binding properties for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="144a6-110">トランザクションを実行する Oracle データベースで、アダプターを使用するインストール必要がありますが、 **Microsoft Transaction Server のサービスの Oracle**コンポーネント、アダプターを実行しているコンピューターで、Oracle クライアントをインストールするときに、クライアントです。</span><span class="sxs-lookup"><span data-stu-id="144a6-110">To use the adapter to perform transactions on the Oracle database, you must have installed the **Oracle Services For Microsoft Transaction Server** component, while installing the Oracle client, on the computer running the adapter client.</span></span>  
  
## <a name="transactions-in-the-outbound-operations"></a><span data-ttu-id="144a6-111">送信操作のトランザクション</span><span class="sxs-lookup"><span data-stu-id="144a6-111">Transactions in the Outbound Operations</span></span>  
 <span data-ttu-id="144a6-112">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]単一のトランザクションで送信操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="144a6-112">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] performs an outbound operation in a single transaction.</span></span> <span data-ttu-id="144a6-113">複合操作は、すべての操作を実行して、1 つのトランザクションではなく異なる ODP.NET 接続を使用します。</span><span class="sxs-lookup"><span data-stu-id="144a6-113">For composite operations, all the operations are performed in a single transaction but using different ODP.NET connections.</span></span> <span data-ttu-id="144a6-114">送信側に表示される操作の詳細については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[アダプター画面 Oracle メタデータをどのように?](https://msdn.microsoft.com/library/cc185310(v=bts.10).aspx)です。</span><span class="sxs-lookup"><span data-stu-id="144a6-114">For more information about the outbound operations surfaced by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [How does the Adapter Surface Oracle Metadata?](https://msdn.microsoft.com/library/cc185310(v=bts.10).aspx).</span></span>  
  
## <a name="transactions-in-the-inbound-operations"></a><span data-ttu-id="144a6-115">受信操作のトランザクション</span><span class="sxs-lookup"><span data-stu-id="144a6-115">Transactions in the Inbound Operations</span></span>  
 <span data-ttu-id="144a6-116">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]次の 2 つの受信操作を公開します。</span><span class="sxs-lookup"><span data-stu-id="144a6-116">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] exposes the following two inbound operations:</span></span>  
  
-   <span data-ttu-id="144a6-117">**ポーリング**: ポーリング ステートメントおよび (指定した場合)、ポーリング後ステートメントが実行されるトランザクションでは、一方、別のトランザクションでポーリングされたデータの使用可能なステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="144a6-117">**Polling**: The polling statement and the post-poll statement (if specified) are executed in a transaction, whereas, the polled data available statement is executed in a different transaction.</span></span> <span data-ttu-id="144a6-118">同様に、ポーリング ステートメントとポーリング後ステートメントは、実行同じ ODP.NET 接続を使用して一方、ODP.NET は別の接続を使用してポーリングされたデータの使用可能なステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="144a6-118">Similarly, the polling statement and the post-poll statement are executed using the same ODP.NET connection, whereas, the polled data available statement is executed using a different ODP.NET connection.</span></span>  
  
-   <span data-ttu-id="144a6-119">**通知**: 通知操作は 1 つの ODP.NET 接続を使用して、トランザクションで実行します。</span><span class="sxs-lookup"><span data-stu-id="144a6-119">**Notification**: The notification operation is performed in a transaction using a single ODP.NET connection.</span></span>  
  
 <span data-ttu-id="144a6-120">受信側に表示される操作の詳細については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[アダプター画面 Oracle メタデータをどのようにしますか?](https://msdn.microsoft.com/library/cc185310(v=bts.10).aspx)です。</span><span class="sxs-lookup"><span data-stu-id="144a6-120">For more information about the inbound operations surfaced by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [How does the Adapter Surface Oracle Metadata?](https://msdn.microsoft.com/library/cc185310(v=bts.10).aspx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="144a6-121">参照</span><span class="sxs-lookup"><span data-stu-id="144a6-121">See Also</span></span>  
 [<span data-ttu-id="144a6-122">BizTalk Adapter for Oracle Database の概要</span><span class="sxs-lookup"><span data-stu-id="144a6-122">Overview of BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)