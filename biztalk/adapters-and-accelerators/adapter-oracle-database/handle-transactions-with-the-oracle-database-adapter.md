---
title: Oracle データベース アダプターでトランザクションの処理 |Microsoft Docs
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
ms.openlocfilehash: 67d0cce0da65e1b2a7e3c1e6df1ef3eda944bbeb
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529182"
---
# <a name="handle-transactions-with-the-oracle-database-adapter"></a><span data-ttu-id="1d167-102">Oracle データベース アダプターでトランザクションを処理します。</span><span class="sxs-lookup"><span data-stu-id="1d167-102">Handle Transactions with the Oracle Database adapter</span></span>
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] <span data-ttu-id="1d167-103">Oracle データベースで操作を実行中にトランザクションを開始しません。</span><span class="sxs-lookup"><span data-stu-id="1d167-103">does not initiate a transaction while performing an operation on the Oracle database.</span></span> <span data-ttu-id="1d167-104">代わりに、アダプターはアダプター クライアントによって提供されるトランザクション コンテキストを使用して、操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="1d167-104">Instead, the adapter performs the operations using the transaction context provided by the adapter clients.</span></span> <span data-ttu-id="1d167-105">使用して、トランザクションで操作を実行するために、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]、する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d167-105">In order to perform operations in a transaction using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], you must:</span></span>  
  
-   <span data-ttu-id="1d167-106">アダプター クライアントのトランザクションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="1d167-106">Enable transactions in the adapter clients.</span></span> <span data-ttu-id="1d167-107">たとえば、BizTalk Server のトランザクションを有効にする必要がありますを選択、 **Use-transaction**  チェック ボックス、**トランザクション**の領域、**メッセージ**WCF カスタム タブまたはWcf-oracledb ポートです。</span><span class="sxs-lookup"><span data-stu-id="1d167-107">For example, to enable transactions in BizTalk Server, you must select the **Use Transaction** check box in the **Transactions** area of the **Messages** tab for a WCF-Custom or WCF-OracleDB port.</span></span>  
  
-   <span data-ttu-id="1d167-108">値を設定、 **UseAmbientTransaction**プロパティをバインド**True**アダプター。</span><span class="sxs-lookup"><span data-stu-id="1d167-108">Set the value of the **UseAmbientTransaction** binding property to **True** in the adapter.</span></span> <span data-ttu-id="1d167-109">バインディング プロパティの詳細については、次を参照してください。 [for Oracle Database バインド プロパティを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)します。</span><span class="sxs-lookup"><span data-stu-id="1d167-109">For more information about the binding property, see [Configure the binding properties for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1d167-110">アダプターを使用して、Oracle データベースでトランザクションを実行する、する必要がありますがインストールされている、 **Microsoft Transaction Server のサービスの Oracle**アダプターを実行するコンピューターで、Oracle クライアントをインストールするときに、コンポーネントクライアント。</span><span class="sxs-lookup"><span data-stu-id="1d167-110">To use the adapter to perform transactions on the Oracle database, you must have installed the **Oracle Services For Microsoft Transaction Server** component, while installing the Oracle client, on the computer running the adapter client.</span></span>  
  
## <a name="transactions-in-the-outbound-operations"></a><span data-ttu-id="1d167-111">送信操作のトランザクション</span><span class="sxs-lookup"><span data-stu-id="1d167-111">Transactions in the Outbound Operations</span></span>  
 <span data-ttu-id="1d167-112">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]単一のトランザクションで送信操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="1d167-112">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] performs an outbound operation in a single transaction.</span></span> <span data-ttu-id="1d167-113">複合操作は、のすべての操作を実行して、1 つのトランザクションが、異なる ODP.NET 接続を使用します。</span><span class="sxs-lookup"><span data-stu-id="1d167-113">For composite operations, all the operations are performed in a single transaction but using different ODP.NET connections.</span></span> <span data-ttu-id="1d167-114">送信側に表示される操作の詳細については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[アダプター画面 Oracle のメタデータをどのようにですか?](https://msdn.microsoft.com/library/cc185310(v=bts.10).aspx)します。</span><span class="sxs-lookup"><span data-stu-id="1d167-114">For more information about the outbound operations surfaced by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [How does the Adapter Surface Oracle Metadata?](https://msdn.microsoft.com/library/cc185310(v=bts.10).aspx).</span></span>  
  
## <a name="transactions-in-the-inbound-operations"></a><span data-ttu-id="1d167-115">受信操作のトランザクション</span><span class="sxs-lookup"><span data-stu-id="1d167-115">Transactions in the Inbound Operations</span></span>  
 <span data-ttu-id="1d167-116">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]次の 2 つの受信操作を公開します。</span><span class="sxs-lookup"><span data-stu-id="1d167-116">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] exposes the following two inbound operations:</span></span>  
  
- <span data-ttu-id="1d167-117">**ポーリング**:ポーリング ステートメントとポーリング後ステートメント (指定した) 場合は、一方、別のトランザクションでポーリング済みデータの使用可能なステートメントが実行されるトランザクションで実行されます。</span><span class="sxs-lookup"><span data-stu-id="1d167-117">**Polling**: The polling statement and the post-poll statement (if specified) are executed in a transaction, whereas, the polled data available statement is executed in a different transaction.</span></span> <span data-ttu-id="1d167-118">同様に、ポーリング ステートメントとポーリング後ステートメントの実行同じ ODP.NET 接続を使用して一方、さまざまな ODP.NET 接続を使用してポーリング済みデータの使用可能なステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="1d167-118">Similarly, the polling statement and the post-poll statement are executed using the same ODP.NET connection, whereas, the polled data available statement is executed using a different ODP.NET connection.</span></span>  
  
- <span data-ttu-id="1d167-119">**通知**:通知の操作は、1 つの ODP.NET 接続を使用して、トランザクションで実行されます。</span><span class="sxs-lookup"><span data-stu-id="1d167-119">**Notification**: The notification operation is performed in a transaction using a single ODP.NET connection.</span></span>  
  
  <span data-ttu-id="1d167-120">受信側に表示される操作の詳細については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[アダプター画面 Oracle のメタデータをどのようにですか?](https://msdn.microsoft.com/library/cc185310(v=bts.10).aspx)します。</span><span class="sxs-lookup"><span data-stu-id="1d167-120">For more information about the inbound operations surfaced by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [How does the Adapter Surface Oracle Metadata?](https://msdn.microsoft.com/library/cc185310(v=bts.10).aspx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d167-121">参照</span><span class="sxs-lookup"><span data-stu-id="1d167-121">See Also</span></span>  
 [<span data-ttu-id="1d167-122">BizTalk Adapter for Oracle Database の概要</span><span class="sxs-lookup"><span data-stu-id="1d167-122">Overview of BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)