---
title: Oracle E-business Suite アダプターでトランザクションを処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b443be9d-a93d-4836-8717-5ee9dad4442f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ddfe7ebc56fce471bb4dceabf24c09e7a084bca1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375486"
---
# <a name="handle-transactions-with-the-oracle-e-business-suite-adapter"></a><span data-ttu-id="6736f-102">Oracle E-business Suite アダプターでトランザクションを処理します。</span><span class="sxs-lookup"><span data-stu-id="6736f-102">Handle transactions with the Oracle E-Business Suite adapter</span></span>
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] <span data-ttu-id="6736f-103">Oracle E-business Suite の操作の実行中のトランザクションを開始しません。</span><span class="sxs-lookup"><span data-stu-id="6736f-103">does not initiate a transaction while performing an operation in Oracle E-Business Suite.</span></span> <span data-ttu-id="6736f-104">代わりに、アダプターはアダプター クライアントによって提供されるトランザクション コンテキストを使用して、操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="6736f-104">Instead, the adapter performs the operations using the transaction context provided by the adapter clients.</span></span> <span data-ttu-id="6736f-105">使用して、トランザクションで操作を実行するために、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]、する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6736f-105">In order to perform operations in a transaction using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], you must:</span></span>  
  
-   <span data-ttu-id="6736f-106">アダプター クライアントのトランザクションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="6736f-106">Enable transactions in the adapter clients.</span></span> <span data-ttu-id="6736f-107">たとえば、BizTalk Server のトランザクションを有効にする必要がありますを選択、 **Use-transaction**  チェック ボックス、**トランザクション**の領域、**メッセージ**WCF カスタム タブまたはWcf-oracleebs ポートです。</span><span class="sxs-lookup"><span data-stu-id="6736f-107">For example, to enable transactions in BizTalk Server, you must select the **Use Transaction** check box in the **Transactions** area of the **Messages** tab for a WCF-Custom or WCF-OracleEBS port.</span></span>  
  
-   <span data-ttu-id="6736f-108">値を設定、 **UseAmbientTransaction**プロパティをバインド**True**アダプター。</span><span class="sxs-lookup"><span data-stu-id="6736f-108">Set the value of the **UseAmbientTransaction** binding property to **True** in the adapter.</span></span> <span data-ttu-id="6736f-109">バインディング プロパティの詳細については、次を参照してください。[については、BizTalk Adapter for Oracle E-business Suite バインド プロパティを読み取る](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="6736f-109">For more information about the binding property, see [Read about the BizTalk Adapter for Oracle E-Business Suite Binding Properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6736f-110">アダプターを使用して、Oracle E-business Suite でトランザクションを実行する、する必要がありますがインストールされている、 **Microsoft Transaction Server のサービスの Oracle**アダプターを実行するコンピューターで、Oracle クライアントをインストールするときに、コンポーネントクライアント。</span><span class="sxs-lookup"><span data-stu-id="6736f-110">To use the adapter to perform transactions in Oracle E-Business Suite, you must have installed the **Oracle Services For Microsoft Transaction Server** component, while installing the Oracle client, on the computer running the adapter client.</span></span>  
  
## <a name="transactions-in-the-outbound-operations"></a><span data-ttu-id="6736f-111">送信操作のトランザクション</span><span class="sxs-lookup"><span data-stu-id="6736f-111">Transactions in the Outbound Operations</span></span>  
 <span data-ttu-id="6736f-112">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]単一のトランザクションで送信操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="6736f-112">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] performs an outbound operation in a single transaction.</span></span> <span data-ttu-id="6736f-113">複合操作は、のすべての操作を実行して、1 つのトランザクションが、異なる ODP.NET 接続を使用します。</span><span class="sxs-lookup"><span data-stu-id="6736f-113">For composite operations, all the operations are performed in a single transaction but using different ODP.NET connections.</span></span> <span data-ttu-id="6736f-114">送信側に表示される操作の詳細については、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[アダプター画面 Oracle E-business Suite のメタデータをどのようにですか?](https://msdn.microsoft.com/library/dd788431.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="6736f-114">For more information about the outbound operations surfaced by the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], see [How Does the Adapter Surface Oracle E-Business Suite Metadata?](https://msdn.microsoft.com/library/dd788431.aspx).</span></span>  
  
## <a name="transactions-in-the-inbound-operations"></a><span data-ttu-id="6736f-115">受信操作のトランザクション</span><span class="sxs-lookup"><span data-stu-id="6736f-115">Transactions in the Inbound Operations</span></span>  
 <span data-ttu-id="6736f-116">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]次の 2 つの受信操作を公開します。</span><span class="sxs-lookup"><span data-stu-id="6736f-116">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] exposes the following two inbound operations:</span></span>  
  
- <span data-ttu-id="6736f-117">**ポーリング**:ポーリング ステートメントとポーリング後ステートメント (指定した) 場合は、一方、別のトランザクションでポーリング済みデータの使用可能なステートメントが実行されるトランザクションで実行されます。</span><span class="sxs-lookup"><span data-stu-id="6736f-117">**Polling**: The polling statement and the post-poll statement (if specified) are executed in a transaction, whereas, the polled data available statement is executed in a different transaction.</span></span> <span data-ttu-id="6736f-118">同様に、ポーリング ステートメントとポーリング後ステートメントの実行同じ ODP.NET 接続を使用して一方、さまざまな ODP.NET 接続を使用してポーリング済みデータの使用可能なステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="6736f-118">Similarly, the polling statement and the post-poll statement are executed using the same ODP.NET connection, whereas, the polled data available statement is executed using a different ODP.NET connection.</span></span>  
  
- <span data-ttu-id="6736f-119">**通知**:通知の操作は、1 つの ODP.NET 接続を使用して、トランザクションで実行されます。</span><span class="sxs-lookup"><span data-stu-id="6736f-119">**Notification**: The notification operation is performed in a transaction using a single ODP.NET connection.</span></span>  
  
  <span data-ttu-id="6736f-120">受信側に表示される操作の詳細については、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[アダプター画面 Oracle E-business Suite のメタデータをどのようにですか?](https://msdn.microsoft.com/library/dd788431.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="6736f-120">For more information about the inbound operations surfaced by the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], see [How Does the Adapter Surface Oracle E-Business Suite Metadata?](https://msdn.microsoft.com/library/dd788431.aspx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6736f-121">参照</span><span class="sxs-lookup"><span data-stu-id="6736f-121">See Also</span></span>  
[<span data-ttu-id="6736f-122">BizTalk Adapter for Oracle E-Business Suite について</span><span class="sxs-lookup"><span data-stu-id="6736f-122">Understand BizTalk Adapter for Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md)