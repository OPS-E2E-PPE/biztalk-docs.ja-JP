---
title: "トランザクションを追加する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adding, transactions
- transactions, adding
ms.assetid: 25385c20-3025-4cf1-bc1f-ef266e081bad
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24c67a9c76ae87f2355bb0ea4638d3bd156cda6e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-transaction"></a><span data-ttu-id="af0f6-102">トランザクションを追加する方法</span><span class="sxs-lookup"><span data-stu-id="af0f6-102">How to Add a Transaction</span></span>
<span data-ttu-id="af0f6-103">以下の手順に従ってトランザクションを追加します。</span><span class="sxs-lookup"><span data-stu-id="af0f6-103">Follow these steps to add a transaction.</span></span>  
  
### <a name="to-add-a-transaction"></a><span data-ttu-id="af0f6-104">トランザクションを追加するには</span><span class="sxs-lookup"><span data-stu-id="af0f6-104">To add a transaction</span></span>  
  
1.  <span data-ttu-id="af0f6-105">クリックして、**トランザクション**タブです。</span><span class="sxs-lookup"><span data-stu-id="af0f6-105">Click the **Transactions** tab.</span></span>  
  
2.  <span data-ttu-id="af0f6-106">をクリックして**追加トランザクション**です。</span><span class="sxs-lookup"><span data-stu-id="af0f6-106">Click **Add Transaction**.</span></span>  
  
3.  <span data-ttu-id="af0f6-107">をクリックして**新しい値を追加**です。</span><span class="sxs-lookup"><span data-stu-id="af0f6-107">Click **Add a New Value**.</span></span> <span data-ttu-id="af0f6-108">次の情報を入力し、クリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="af0f6-108">Enter the following information, and then click **Add**.</span></span>  
  
    1.  <span data-ttu-id="af0f6-109">**ノード名:**これは、ことを確認して**MSEXTERNAL**です。</span><span class="sxs-lookup"><span data-stu-id="af0f6-109">**Node Name:** Verify that this is **MSEXTERNAL**.</span></span>  
  
    2.  <span data-ttu-id="af0f6-110">**トランザクションの種類:**これは、ことを確認して**Outbound Asynchronous**です。</span><span class="sxs-lookup"><span data-stu-id="af0f6-110">**Transaction Type:** Verify that this is **Outbound Asynchronous**.</span></span>  
  
    3.  <span data-ttu-id="af0f6-111">**要求メッセージ:**入力`LOCATION_SYNC`です。</span><span class="sxs-lookup"><span data-stu-id="af0f6-111">**Request Message:** Enter `LOCATION_SYNC`.</span></span>  
  
    4.  <span data-ttu-id="af0f6-112">**要求メッセージのバージョン:**入力`VERSION_1`です。</span><span class="sxs-lookup"><span data-stu-id="af0f6-112">**Request Message Version:** Enter `VERSION_1`.</span></span>  
  
     ![](../core/media/psadapter-38-task-gatewayaddtransaction.gif "PSAdapter_38_Task_GatewayAddTransaction")  
  
4.  <span data-ttu-id="af0f6-113">**Transaction Detail**  タブで、次の設定を確認してください。</span><span class="sxs-lookup"><span data-stu-id="af0f6-113">On the **Transaction Detail** tab, verify the following settings:</span></span>  
  
    1.  <span data-ttu-id="af0f6-114">**状態:**アクティブです。</span><span class="sxs-lookup"><span data-stu-id="af0f6-114">**Status:** Active.</span></span>  
  
    2.  <span data-ttu-id="af0f6-115">**ルーティング:**暗黙の型。</span><span class="sxs-lookup"><span data-stu-id="af0f6-115">**Routing:** Implicit.</span></span>  
  
     ![](../core/media/psadapter-39-task-gatewaytransdetail.gif "PSAdapter_39_Task_GatewayTransDetail")  
  
5.  <span data-ttu-id="af0f6-116">**[保存]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af0f6-116">Click **Save**.</span></span>  
  
6.  <span data-ttu-id="af0f6-117">クリックして、 **Return to Transaction List**リンクします。</span><span class="sxs-lookup"><span data-stu-id="af0f6-117">Click the **Return to Transaction List** link.</span></span>  
  
     <span data-ttu-id="af0f6-118">トランザクションの一覧に、トランザクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="af0f6-118">The transaction appears in the list of transactions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af0f6-119">参照</span><span class="sxs-lookup"><span data-stu-id="af0f6-119">See Also</span></span>  
 [<span data-ttu-id="af0f6-120">PeopleSoft HTTP ホストおよびポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="af0f6-120">Creating a PeopleSoft HTTP Host and Port</span></span>](../core/creating-a-peoplesoft-http-host-and-port.md)