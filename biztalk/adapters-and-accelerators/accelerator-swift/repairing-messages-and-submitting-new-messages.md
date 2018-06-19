---
title: メッセージの修復し、新しいメッセージを送信する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- repairing messages
- Message Repair and New Submission
- submitting, messages
- submitting, Message Repair and New Submission
- messages, Message Repair and New Submission
- messages, submitting
- Message Repair and New Submission. about Message Repair and New Submission
ms.assetid: 6abcce90-f611-422a-b3c8-e25f1e75b039
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 59ece524ce06430492a3927c0cd1437eef4b216d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214026"
---
# <a name="repairing-messages-and-submitting-new-messages"></a><span data-ttu-id="f40b1-102">メッセージの修復し、新しいメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="f40b1-102">Repairing Messages and Submitting New Messages</span></span>
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="f40b1-103">Message Repair and New Submission を使用すると、XML またはビジネス ルール エンジンの検証に失敗したメッセージを修復できます。</span><span class="sxs-lookup"><span data-stu-id="f40b1-103"> Message Repair and New Submission enables you to repair a message that has failed XML or Business Rules Engine validation.</span></span> <span data-ttu-id="f40b1-104">修復処理には、精度とメッセージの修復の妥当性を確保するための検証と承認の手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f40b1-104">The repair process includes verification and approval steps that ensure the accuracy and appropriateness of the message repair.</span></span> <span data-ttu-id="f40b1-105">使用して、このプロセスが実行される[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] MRSR サイト内のフォームです。</span><span class="sxs-lookup"><span data-stu-id="f40b1-105">This process is performed using [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)][!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] forms within MRSR site.</span></span>  
  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="f40b1-106">このプロセスを使用して、新しいメッセージを送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="f40b1-106"> also enables you to submit a new message using this process.</span></span> <span data-ttu-id="f40b1-107">作成者が、メッセージを送信して、ワークフローは、修理会社の検証機能、およびメッセージの修復と同様に同じタスクを実行する承認者を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="f40b1-107">A creator submits the message, and the workflow can include a repairer, a verifier, and an approver performing the same tasks as in message repair.</span></span>  
  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="f40b1-108">各タスクを実行する別のユーザーに割り当てることで、このプロセスのセキュリティを確保します。</span><span class="sxs-lookup"><span data-stu-id="f40b1-108"> ensures the security of this process by assigning different users to perform each task.</span></span> <span data-ttu-id="f40b1-109">適切な修復を割り当てるまたはことを確認するには、これらのユーザーの各ロールの承認を実行して、各ユーザーは、特定の証明書を使用してタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f40b1-109">You assign the appropriate repair, verify, or approve role to each of these users, and each user must use a specific certificate to perform the task.</span></span> [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="f40b1-110">修復と送信されたメッセージの処理には、部門の使用をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="f40b1-110"> also supports the use of departments in processing repaired and submitted messages.</span></span> <span data-ttu-id="f40b1-111">各部門には、特定のメッセージ セットで実行されるタスクの特定のワークフローが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f40b1-111">Each department involves a specific workflow of tasks performed on a specific set of messages.</span></span> <span data-ttu-id="f40b1-112">作成のいずれか、修復、ことを確認する、または、メッセージを送信するときに、手順についてを承認[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]BRE 検証を呼び出すし、ユーザーが適切な部門のメンバーであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f40b1-112">In any of the create, repair, verify, or approve steps, when you submit the message, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] calls BRE validation and verifies that the user is a member of the appropriate department.</span></span> <span data-ttu-id="f40b1-113">メッセージの修復と新しい送信の詳細については、次を参照してください。[メッセージ修復 and New Submission](../../adapters-and-accelerators/accelerator-swift/message-repair-and-new-submission.md)です。</span><span class="sxs-lookup"><span data-stu-id="f40b1-113">For more information about message repair and new submission, see [Message Repair and New Submission](../../adapters-and-accelerators/accelerator-swift/message-repair-and-new-submission.md).</span></span>  
  
 <span data-ttu-id="f40b1-114">メッセージが表示される未解析、Message Repair および New Submission メッセージとエラーの説明を表示する場合、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]が形成され、メッセージを印刷またはファイルに保存することができます。</span><span class="sxs-lookup"><span data-stu-id="f40b1-114">If you receive an unparsed message, Message Repair and New Submission displays the message and a description of the failure in an [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form, and enables you to print the message or save it to a file.</span></span> <span data-ttu-id="f40b1-115">修復し、メッセージを再送信します。</span><span class="sxs-lookup"><span data-stu-id="f40b1-115">You can then repair and resubmit the message.</span></span> <span data-ttu-id="f40b1-116">ただし、 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] BRE 検証を呼び出すまたは修復する未解析のメッセージを送信するときに、部署内のメンバーシップを確認しません。</span><span class="sxs-lookup"><span data-stu-id="f40b1-116">However, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] does not call BRE validation or check membership in a department when you submit an unparsed message that you have repaired.</span></span> <span data-ttu-id="f40b1-117">さらに、未解析の再送信されたメッセージまたはされていないことを確認を承認します。</span><span class="sxs-lookup"><span data-stu-id="f40b1-117">In addition, a resubmitted unparsed message is not verified or approved.</span></span> <span data-ttu-id="f40b1-118">未解析のメッセージの詳細については、次を参照してください。[未解析のメッセージの修復](../../adapters-and-accelerators/accelerator-swift/repairing-unparsed-messages.md)です。</span><span class="sxs-lookup"><span data-stu-id="f40b1-118">For more information about unparsed messages, see [Repairing Unparsed Messages](../../adapters-and-accelerators/accelerator-swift/repairing-unparsed-messages.md).</span></span>  
  
 <span data-ttu-id="f40b1-119">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f40b1-119">This section contains:</span></span>  
  
-   [<span data-ttu-id="f40b1-120">メッセージの修復</span><span class="sxs-lookup"><span data-stu-id="f40b1-120">Repairing a Message</span></span>](../../adapters-and-accelerators/accelerator-swift/repairing-a-message.md)  
  
-   [<span data-ttu-id="f40b1-121">メッセージの検証</span><span class="sxs-lookup"><span data-stu-id="f40b1-121">Verifying a Message</span></span>](../../adapters-and-accelerators/accelerator-swift/verifying-a-message.md)  
  
-   [<span data-ttu-id="f40b1-122">メッセージを承認します。</span><span class="sxs-lookup"><span data-stu-id="f40b1-122">Approving a Message</span></span>](../../adapters-and-accelerators/accelerator-swift/approving-a-message.md)  
  
-   [<span data-ttu-id="f40b1-123">未解析のメッセージの処理</span><span class="sxs-lookup"><span data-stu-id="f40b1-123">Handling an Unparsed Message</span></span>](../../adapters-and-accelerators/accelerator-swift/handling-an-unparsed-message.md)  
  
-   [<span data-ttu-id="f40b1-124">作成して、新しいメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="f40b1-124">Creating and Submitting a New Message</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-and-submitting-a-new-message.md)  
  
-   [<span data-ttu-id="f40b1-125">新しいメッセージ テンプレートの作成</span><span class="sxs-lookup"><span data-stu-id="f40b1-125">Creating a New Message Template</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-a-new-message-template.md)