---
title: メッセージは拒否のカスタム ハンドラーの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- custom handlers
- Message Repair and New Submission, rejected messages
- Message Repair and New Submission, custom handlers
ms.assetid: 28d74504-6c62-427a-b75d-456fbe43ec3a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7fb2ebe02d4f64923239bb67aa3667ac4f3ff0b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378496"
---
# <a name="creating-a-custom-handler-for-rejected-messages"></a><span data-ttu-id="d5b09-102">拒否されたメッセージのカスタム ハンドラーを作成します。</span><span class="sxs-lookup"><span data-stu-id="d5b09-102">Creating a Custom Handler for Rejected Messages</span></span>
<span data-ttu-id="d5b09-103">認証または承認ステージでは、メッセージを拒否した場合[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)](ここでは常に修復する場合でも、作成は、ワークフローの最初のステージ) をワークフローに対して定義されている最初のステージにメッセージが返されます。</span><span class="sxs-lookup"><span data-stu-id="d5b09-103">If you reject a message in the verification or approval stage, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] returns the message to the first stage defined for the workflow (which in this case is always repair, even if Create is the first stage in the workflow).</span></span> <span data-ttu-id="d5b09-104">ただし、ワークフローの最初の段階では、メッセージを拒否する場合、修復オーケストレーションは、メッセージ公開メッセージ ボックスに MrsrRepair オーケストレーションにメッセージが拒否されたことを示す昇格させたプロパティ。</span><span class="sxs-lookup"><span data-stu-id="d5b09-104">However, if the first stage of the workflow rejects the message, the repair orchestration publishes the message to the MessageBox with promoted properties indicating that the MrsrRepair orchestration rejected the message.</span></span> <span data-ttu-id="d5b09-105">これらのメッセージを処理するには、これらの昇格させたプロパティをサブスクライブし、必要に応じてメッセージを処理するカスタム ハンドラー (オーケストレーション) を作成できます。</span><span class="sxs-lookup"><span data-stu-id="d5b09-105">To handle these messages, you can create a custom handler (orchestration) that subscribes to these promoted properties and processes the messages as required.</span></span>  
  
 <span data-ttu-id="d5b09-106">メッセージは、複数の理由から MrsrRepair オーケストレーションで失敗することができます。</span><span class="sxs-lookup"><span data-stu-id="d5b09-106">A message can fail in the MrsrRepair orchestration for multiple reasons.</span></span> <span data-ttu-id="d5b09-107">オーケストレーションは次の表にプロパティを昇格し、値、またはテーブルの右側の列に表示される、値の 1 つは、これらのプロパティを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d5b09-107">When it does, the orchestration promotes the properties in the following table, and assigns these properties the value, or one of the values, shown in the right column of the table.</span></span>  
  
|<span data-ttu-id="d5b09-108">プロパティ</span><span class="sxs-lookup"><span data-stu-id="d5b09-108">Property</span></span>|<span data-ttu-id="d5b09-109">値</span><span class="sxs-lookup"><span data-stu-id="d5b09-109">Values</span></span>|  
|--------------|------------|  
|<span data-ttu-id="d5b09-110">BTS します。操作</span><span class="sxs-lookup"><span data-stu-id="d5b09-110">BTS.Operation</span></span>|<span data-ttu-id="d5b09-111">A4SWIFT_MRSRFailed</span><span class="sxs-lookup"><span data-stu-id="d5b09-111">A4SWIFT_MRSRFailed</span></span>|  
|<span data-ttu-id="d5b09-112">A4SWIFT_MRSRFailedReason</span><span class="sxs-lookup"><span data-stu-id="d5b09-112">A4SWIFT_MRSRFailedReason</span></span>|<span data-ttu-id="d5b09-113">Timeout</span><span class="sxs-lookup"><span data-stu-id="d5b09-113">Timeout</span></span><br /><br /> <span data-ttu-id="d5b09-114">拒否された (場合は、最初の段階から、メッセージは拒否されました)</span><span class="sxs-lookup"><span data-stu-id="d5b09-114">Rejected (means the message has been rejected from the first stage)</span></span><br /><br /> <span data-ttu-id="d5b09-115">CantRepairInInfoPath</span><span class="sxs-lookup"><span data-stu-id="d5b09-115">CantRepairInInfoPath</span></span>|  
|<span data-ttu-id="d5b09-116">A4SWIFT_MRSRLastStage</span><span class="sxs-lookup"><span data-stu-id="d5b09-116">A4SWIFT_MRSRLastStage</span></span>|<span data-ttu-id="d5b09-117">\<メッセージが失敗するまでが含まれる最後のステージ (ロール) の名前\></span><span class="sxs-lookup"><span data-stu-id="d5b09-117">\<name of last stage (role) that the message was in before failing\></span></span>|  
|<span data-ttu-id="d5b09-118">A4SWIFT_MRSRDepartment</span><span class="sxs-lookup"><span data-stu-id="d5b09-118">A4SWIFT_MRSRDepartment</span></span>|<span data-ttu-id="d5b09-119">\<部門の名前\></span><span class="sxs-lookup"><span data-stu-id="d5b09-119">\<name of department\></span></span>|