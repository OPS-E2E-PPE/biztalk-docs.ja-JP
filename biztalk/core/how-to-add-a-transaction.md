---
title: トランザクションを追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adding, transactions
- transactions, adding
ms.assetid: 25385c20-3025-4cf1-bc1f-ef266e081bad
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2734828dad1a236fa6bd599588f5b34094cfeb13
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387285"
---
# <a name="how-to-add-a-transaction"></a><span data-ttu-id="a7fec-102">トランザクションを追加する方法</span><span class="sxs-lookup"><span data-stu-id="a7fec-102">How to Add a Transaction</span></span>
<span data-ttu-id="a7fec-103">トランザクションを追加する次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="a7fec-103">Follow these steps to add a transaction.</span></span>  
  
### <a name="to-add-a-transaction"></a><span data-ttu-id="a7fec-104">トランザクションを追加するには</span><span class="sxs-lookup"><span data-stu-id="a7fec-104">To add a transaction</span></span>  
  
1. <span data-ttu-id="a7fec-105">をクリックして、**トランザクション**タブ。</span><span class="sxs-lookup"><span data-stu-id="a7fec-105">Click the **Transactions** tab.</span></span>  
  
2. <span data-ttu-id="a7fec-106">クリックして**トランザクション追加**します。</span><span class="sxs-lookup"><span data-stu-id="a7fec-106">Click **Add Transaction**.</span></span>  
  
3. <span data-ttu-id="a7fec-107">クリックして**新しい値を追加**します。</span><span class="sxs-lookup"><span data-stu-id="a7fec-107">Click **Add a New Value**.</span></span> <span data-ttu-id="a7fec-108">次の情報を入力し、クリックして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="a7fec-108">Enter the following information, and then click **Add**.</span></span>  
  
   1. <span data-ttu-id="a7fec-109">**ノード名:** あることを確認**MSEXTERNAL**します。</span><span class="sxs-lookup"><span data-stu-id="a7fec-109">**Node Name:** Verify that this is **MSEXTERNAL**.</span></span>  
  
   2. <span data-ttu-id="a7fec-110">**トランザクションの種類:** あることを確認**Outbound Asynchronous**します。</span><span class="sxs-lookup"><span data-stu-id="a7fec-110">**Transaction Type:** Verify that this is **Outbound Asynchronous**.</span></span>  
  
   3. <span data-ttu-id="a7fec-111">**要求メッセージ。** 入力`LOCATION_SYNC`します。</span><span class="sxs-lookup"><span data-stu-id="a7fec-111">**Request Message:** Enter `LOCATION_SYNC`.</span></span>  
  
   4. <span data-ttu-id="a7fec-112">**要求メッセージのバージョン:** 入力`VERSION_1`します。</span><span class="sxs-lookup"><span data-stu-id="a7fec-112">**Request Message Version:** Enter `VERSION_1`.</span></span>  
  
      <span data-ttu-id="a7fec-113">![](../core/media/psadapter-38-task-gatewayaddtransaction.gif "PSAdapter_38_Task_GatewayAddTransaction")</span><span class="sxs-lookup"><span data-stu-id="a7fec-113">![](../core/media/psadapter-38-task-gatewayaddtransaction.gif "PSAdapter_38_Task_GatewayAddTransaction")</span></span>  
  
4. <span data-ttu-id="a7fec-114">**Transaction Detail**  タブで、次の設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="a7fec-114">On the **Transaction Detail** tab, verify the following settings:</span></span>  
  
   1. <span data-ttu-id="a7fec-115">**状態:** アクティブ:</span><span class="sxs-lookup"><span data-stu-id="a7fec-115">**Status:** Active.</span></span>  
  
   2. <span data-ttu-id="a7fec-116">**ルーティング。** 暗黙の型。</span><span class="sxs-lookup"><span data-stu-id="a7fec-116">**Routing:** Implicit.</span></span>  
  
      <span data-ttu-id="a7fec-117">![](../core/media/psadapter-39-task-gatewaytransdetail.gif "PSAdapter_39_Task_GatewayTransDetail")</span><span class="sxs-lookup"><span data-stu-id="a7fec-117">![](../core/media/psadapter-39-task-gatewaytransdetail.gif "PSAdapter_39_Task_GatewayTransDetail")</span></span>  
  
5. <span data-ttu-id="a7fec-118">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7fec-118">Click **Save**.</span></span>  
  
6. <span data-ttu-id="a7fec-119">をクリックして、 **Return to Transaction List**リンク。</span><span class="sxs-lookup"><span data-stu-id="a7fec-119">Click the **Return to Transaction List** link.</span></span>  
  
    <span data-ttu-id="a7fec-120">トランザクションは、トランザクションの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a7fec-120">The transaction appears in the list of transactions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7fec-121">参照</span><span class="sxs-lookup"><span data-stu-id="a7fec-121">See Also</span></span>  
 [<span data-ttu-id="a7fec-122">PeopleSoft の HTTP ホストとポートを作成する</span><span class="sxs-lookup"><span data-stu-id="a7fec-122">Creating a PeopleSoft HTTP Host and Port</span></span>](../core/creating-a-peoplesoft-http-host-and-port.md)