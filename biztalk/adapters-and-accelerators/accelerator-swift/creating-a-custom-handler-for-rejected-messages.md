---
title: メッセージを拒否するカスタム ハンドラーを作成 |Microsoft ドキュメント
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
ms.openlocfilehash: baa02ad0fcb0236ec879e43b44a891fcdf591beb
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963784"
---
# <a name="creating-a-custom-handler-for-rejected-messages"></a><span data-ttu-id="520e8-102">拒否されたメッセージのカスタム ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="520e8-102">Creating a Custom Handler for Rejected Messages</span></span>
<span data-ttu-id="520e8-103">検証または承認の段階でメッセージを拒否した場合[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)](ここでは常に修復する場合でも、作成は、ワークフローの最初のステージ) をワークフローに対して定義されている最初のステージにメッセージが返されます。</span><span class="sxs-lookup"><span data-stu-id="520e8-103">If you reject a message in the verification or approval stage, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] returns the message to the first stage defined for the workflow (which in this case is always repair, even if Create is the first stage in the workflow).</span></span> <span data-ttu-id="520e8-104">ただし、ワークフローの最初の段階では、メッセージを拒否する場合、修復オーケストレーションは、メッセージ公開メッセージ ボックスに MrsrRepair オーケストレーションにメッセージが拒否されたことを示す昇格させたプロパティを持つ。</span><span class="sxs-lookup"><span data-stu-id="520e8-104">However, if the first stage of the workflow rejects the message, the repair orchestration publishes the message to the MessageBox with promoted properties indicating that the MrsrRepair orchestration rejected the message.</span></span> <span data-ttu-id="520e8-105">これらのメッセージを処理するには、これらの昇格させたプロパティをサブスクライブし、必要に応じてメッセージを処理するカスタム ハンドラー (オーケストレーション) を作成できます。</span><span class="sxs-lookup"><span data-stu-id="520e8-105">To handle these messages, you can create a custom handler (orchestration) that subscribes to these promoted properties and processes the messages as required.</span></span>  
  
 <span data-ttu-id="520e8-106">メッセージは、MrsrRepair オーケストレーションで複数の理由により失敗します。</span><span class="sxs-lookup"><span data-stu-id="520e8-106">A message can fail in the MrsrRepair orchestration for multiple reasons.</span></span> <span data-ttu-id="520e8-107">オーケストレーションは、次の表に、プロパティを昇格し、値、またはテーブルの右側の列に示すように、値のいずれか、これらのプロパティを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="520e8-107">When it does, the orchestration promotes the properties in the following table, and assigns these properties the value, or one of the values, shown in the right column of the table.</span></span>  
  
|<span data-ttu-id="520e8-108">プロパティ</span><span class="sxs-lookup"><span data-stu-id="520e8-108">Property</span></span>|<span data-ttu-id="520e8-109">値</span><span class="sxs-lookup"><span data-stu-id="520e8-109">Values</span></span>|  
|--------------|------------|  
|<span data-ttu-id="520e8-110">BTS です。操作</span><span class="sxs-lookup"><span data-stu-id="520e8-110">BTS.Operation</span></span>|<span data-ttu-id="520e8-111">A4SWIFT_MRSRFailed</span><span class="sxs-lookup"><span data-stu-id="520e8-111">A4SWIFT_MRSRFailed</span></span>|  
|<span data-ttu-id="520e8-112">A4SWIFT_MRSRFailedReason</span><span class="sxs-lookup"><span data-stu-id="520e8-112">A4SWIFT_MRSRFailedReason</span></span>|<span data-ttu-id="520e8-113">Timeout</span><span class="sxs-lookup"><span data-stu-id="520e8-113">Timeout</span></span><br /><br /> <span data-ttu-id="520e8-114">拒否された (場合は、メッセージは、最初のステージから拒否されました)</span><span class="sxs-lookup"><span data-stu-id="520e8-114">Rejected (means the message has been rejected from the first stage)</span></span><br /><br /> <span data-ttu-id="520e8-115">CantRepairInInfoPath</span><span class="sxs-lookup"><span data-stu-id="520e8-115">CantRepairInInfoPath</span></span>|  
|<span data-ttu-id="520e8-116">A4SWIFT_MRSRLastStage</span><span class="sxs-lookup"><span data-stu-id="520e8-116">A4SWIFT_MRSRLastStage</span></span>|<span data-ttu-id="520e8-117">\<最後のステージ (ロール) が失敗する前にあったメッセージの名前\></span><span class="sxs-lookup"><span data-stu-id="520e8-117">\<name of last stage (role) that the message was in before failing\></span></span>|  
|<span data-ttu-id="520e8-118">A4SWIFT_MRSRDepartment</span><span class="sxs-lookup"><span data-stu-id="520e8-118">A4SWIFT_MRSRDepartment</span></span>|<span data-ttu-id="520e8-119">\<部門の名前\></span><span class="sxs-lookup"><span data-stu-id="520e8-119">\<name of department\></span></span>|