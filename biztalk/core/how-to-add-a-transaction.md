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
ms.openlocfilehash: e3a4fcb1116e5b4a0cd3a8b62dc1283abc3215c6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009971"
---
# <a name="how-to-add-a-transaction"></a><span data-ttu-id="ee027-102">トランザクションを追加する方法</span><span class="sxs-lookup"><span data-stu-id="ee027-102">How to Add a Transaction</span></span>
<span data-ttu-id="ee027-103">以下の手順に従ってトランザクションを追加します。</span><span class="sxs-lookup"><span data-stu-id="ee027-103">Follow these steps to add a transaction.</span></span>  
  
### <a name="to-add-a-transaction"></a><span data-ttu-id="ee027-104">トランザクションを追加するには</span><span class="sxs-lookup"><span data-stu-id="ee027-104">To add a transaction</span></span>  
  
1. <span data-ttu-id="ee027-105">をクリックして、**トランザクション**タブ。</span><span class="sxs-lookup"><span data-stu-id="ee027-105">Click the **Transactions** tab.</span></span>  
  
2. <span data-ttu-id="ee027-106">クリックして**トランザクション追加**します。</span><span class="sxs-lookup"><span data-stu-id="ee027-106">Click **Add Transaction**.</span></span>  
  
3. <span data-ttu-id="ee027-107">クリックして**新しい値を追加**します。</span><span class="sxs-lookup"><span data-stu-id="ee027-107">Click **Add a New Value**.</span></span> <span data-ttu-id="ee027-108">次の情報を入力し、クリックして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="ee027-108">Enter the following information, and then click **Add**.</span></span>  
  
   1. <span data-ttu-id="ee027-109">**ノード名:** はこのことを確認して**MSEXTERNAL**します。</span><span class="sxs-lookup"><span data-stu-id="ee027-109">**Node Name:** Verify that this is **MSEXTERNAL**.</span></span>  
  
   2. <span data-ttu-id="ee027-110">**トランザクションの種類:** はこのことを確認して**Outbound Asynchronous**します。</span><span class="sxs-lookup"><span data-stu-id="ee027-110">**Transaction Type:** Verify that this is **Outbound Asynchronous**.</span></span>  
  
   3. <span data-ttu-id="ee027-111">**要求メッセージ:** 入力`LOCATION_SYNC`します。</span><span class="sxs-lookup"><span data-stu-id="ee027-111">**Request Message:** Enter `LOCATION_SYNC`.</span></span>  
  
   4. <span data-ttu-id="ee027-112">**要求メッセージのバージョン:** 入力`VERSION_1`します。</span><span class="sxs-lookup"><span data-stu-id="ee027-112">**Request Message Version:** Enter `VERSION_1`.</span></span>  
  
      <span data-ttu-id="ee027-113">![](../core/media/psadapter-38-task-gatewayaddtransaction.gif "PSAdapter_38_Task_GatewayAddTransaction")</span><span class="sxs-lookup"><span data-stu-id="ee027-113">![](../core/media/psadapter-38-task-gatewayaddtransaction.gif "PSAdapter_38_Task_GatewayAddTransaction")</span></span>  
  
4. <span data-ttu-id="ee027-114">**Transaction Detail**  タブで、次の設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="ee027-114">On the **Transaction Detail** tab, verify the following settings:</span></span>  
  
   1. <span data-ttu-id="ee027-115">**状態:** アクティブです。</span><span class="sxs-lookup"><span data-stu-id="ee027-115">**Status:** Active.</span></span>  
  
   2. <span data-ttu-id="ee027-116">**ルーティング:** 暗黙の型。</span><span class="sxs-lookup"><span data-stu-id="ee027-116">**Routing:** Implicit.</span></span>  
  
      <span data-ttu-id="ee027-117">![](../core/media/psadapter-39-task-gatewaytransdetail.gif "PSAdapter_39_Task_GatewayTransDetail")</span><span class="sxs-lookup"><span data-stu-id="ee027-117">![](../core/media/psadapter-39-task-gatewaytransdetail.gif "PSAdapter_39_Task_GatewayTransDetail")</span></span>  
  
5. <span data-ttu-id="ee027-118">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ee027-118">Click **Save**.</span></span>  
  
6. <span data-ttu-id="ee027-119">をクリックして、 **Return to Transaction List**リンク。</span><span class="sxs-lookup"><span data-stu-id="ee027-119">Click the **Return to Transaction List** link.</span></span>  
  
    <span data-ttu-id="ee027-120">トランザクションの一覧に、トランザクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ee027-120">The transaction appears in the list of transactions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee027-121">参照</span><span class="sxs-lookup"><span data-stu-id="ee027-121">See Also</span></span>  
 [<span data-ttu-id="ee027-122">PeopleSoft の HTTP ホストとポートを作成する</span><span class="sxs-lookup"><span data-stu-id="ee027-122">Creating a PeopleSoft HTTP Host and Port</span></span>](../core/creating-a-peoplesoft-http-host-and-port.md)