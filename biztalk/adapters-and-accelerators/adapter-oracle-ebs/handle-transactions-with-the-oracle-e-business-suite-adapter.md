---
title: "Oracle E-business Suite アダプターでトランザクションの処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b443be9d-a93d-4836-8717-5ee9dad4442f
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e00b31230760d1bb811b987c3b1a926bad803b6d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="handle-transactions-with-the-oracle-e-business-suite-adapter"></a><span data-ttu-id="7f850-102">Oracle E-business Suite アダプターでトランザクションを処理します。</span><span class="sxs-lookup"><span data-stu-id="7f850-102">Handle transactions with the Oracle E-Business Suite adapter</span></span>
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]<span data-ttu-id="7f850-103">Oracle E-business suite 操作の実行中にトランザクションを開始しません。</span><span class="sxs-lookup"><span data-stu-id="7f850-103"> does not initiate a transaction while performing an operation in Oracle E-Business Suite.</span></span> <span data-ttu-id="7f850-104">代わりに、アダプターは、アダプターのクライアントによって提供されるトランザクション コンテキストを使用して操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="7f850-104">Instead, the adapter performs the operations using the transaction context provided by the adapter clients.</span></span> <span data-ttu-id="7f850-105">使用してトランザクションで操作を実行するために、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]、する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f850-105">In order to perform operations in a transaction using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], you must:</span></span>  
  
-   <span data-ttu-id="7f850-106">アダプターのクライアントのトランザクションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="7f850-106">Enable transactions in the adapter clients.</span></span> <span data-ttu-id="7f850-107">例については、トランザクションを有効にする[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]を選択する必要があります、 **Use-transaction**  チェック ボックス、**トランザクション**の領域、**メッセージ**タブに移動して、Wcf-custom または Wcf-oracleebs ポートです。</span><span class="sxs-lookup"><span data-stu-id="7f850-107">For example, to enable transactions in [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)], you must select the **Use Transaction** check box in the **Transactions** area of the **Messages** tab for a WCF-Custom or WCF-OracleEBS port.</span></span>  
  
-   <span data-ttu-id="7f850-108">値を設定、 **UseAmbientTransaction**にプロパティのバインド**True**アダプターでします。</span><span class="sxs-lookup"><span data-stu-id="7f850-108">Set the value of the **UseAmbientTransaction** binding property to **True** in the adapter.</span></span> <span data-ttu-id="7f850-109">バインディング プロパティの詳細については、次を参照してください。 [BizTalk Adapter for Oracle E-business Suite バインド プロパティ読む](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="7f850-109">For more information about the binding property, see [Read about the BizTalk Adapter for Oracle E-Business Suite Binding Properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7f850-110">アダプターを使用すると、Oracle E-business Suite でトランザクションを実行して、する必要がありますがインストールされている、 **Microsoft Transaction Server のサービスの Oracle**コンポーネントは、アダプターを実行しているコンピューターに、Oracle クライアントをインストールするときにクライアントです。</span><span class="sxs-lookup"><span data-stu-id="7f850-110">To use the adapter to perform transactions in Oracle E-Business Suite, you must have installed the **Oracle Services For Microsoft Transaction Server** component, while installing the Oracle client, on the computer running the adapter client.</span></span>  
  
## <a name="transactions-in-the-outbound-operations"></a><span data-ttu-id="7f850-111">送信操作のトランザクション</span><span class="sxs-lookup"><span data-stu-id="7f850-111">Transactions in the Outbound Operations</span></span>  
 <span data-ttu-id="7f850-112">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]単一のトランザクションで送信操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="7f850-112">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] performs an outbound operation in a single transaction.</span></span> <span data-ttu-id="7f850-113">複合操作は、すべての操作を実行して、1 つのトランザクションではなく異なる ODP.NET 接続を使用します。</span><span class="sxs-lookup"><span data-stu-id="7f850-113">For composite operations, all the operations are performed in a single transaction but using different ODP.NET connections.</span></span> <span data-ttu-id="7f850-114">送信側に表示される操作の詳細については、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[アダプター画面 Oracle E-business Suite のメタデータをどのように?](https://msdn.microsoft.com/library/dd788431.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="7f850-114">For more information about the outbound operations surfaced by the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], see [How Does the Adapter Surface Oracle E-Business Suite Metadata?](https://msdn.microsoft.com/library/dd788431.aspx).</span></span>  
  
## <a name="transactions-in-the-inbound-operations"></a><span data-ttu-id="7f850-115">受信操作のトランザクション</span><span class="sxs-lookup"><span data-stu-id="7f850-115">Transactions in the Inbound Operations</span></span>  
 <span data-ttu-id="7f850-116">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]次の 2 つの受信操作を公開します。</span><span class="sxs-lookup"><span data-stu-id="7f850-116">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] exposes the following two inbound operations:</span></span>  
  
-   <span data-ttu-id="7f850-117">**ポーリング**: ポーリング ステートメントおよび (指定した場合)、ポーリング後ステートメントが実行されるトランザクションでは、一方、別のトランザクションでポーリングされたデータの使用可能なステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="7f850-117">**Polling**: The polling statement and the post-poll statement (if specified) are executed in a transaction, whereas, the polled data available statement is executed in a different transaction.</span></span> <span data-ttu-id="7f850-118">同様に、ポーリング ステートメントとポーリング後ステートメントは、実行同じ ODP.NET 接続を使用して一方、ODP.NET は別の接続を使用してポーリングされたデータの使用可能なステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="7f850-118">Similarly, the polling statement and the post-poll statement are executed using the same ODP.NET connection, whereas, the polled data available statement is executed using a different ODP.NET connection.</span></span>  
  
-   <span data-ttu-id="7f850-119">**通知**: 通知操作は 1 つの ODP.NET 接続を使用して、トランザクションで実行します。</span><span class="sxs-lookup"><span data-stu-id="7f850-119">**Notification**: The notification operation is performed in a transaction using a single ODP.NET connection.</span></span>  
  
 <span data-ttu-id="7f850-120">受信側に表示される操作の詳細については、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[アダプター画面 Oracle E-business Suite のメタデータをどのように?](https://msdn.microsoft.com/library/dd788431.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="7f850-120">For more information about the inbound operations surfaced by the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], see [How Does the Adapter Surface Oracle E-Business Suite Metadata?](https://msdn.microsoft.com/library/dd788431.aspx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f850-121">参照</span><span class="sxs-lookup"><span data-stu-id="7f850-121">See Also</span></span>  
[<span data-ttu-id="7f850-122">Oracle E-business Suite の BizTalk アダプターを理解します。</span><span class="sxs-lookup"><span data-stu-id="7f850-122">Understand BizTalk Adapter for Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md)