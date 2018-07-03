---
title: メッセージの修復と新しいメッセージの送信 |Microsoft Docs
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
ms.openlocfilehash: 569ab44588c2bd89c3533af8cc765e58f743a229
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003315"
---
# <a name="repairing-messages-and-submitting-new-messages"></a><span data-ttu-id="48a68-102">メッセージの修復と新しいメッセージの送信</span><span class="sxs-lookup"><span data-stu-id="48a68-102">Repairing Messages and Submitting New Messages</span></span>
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="48a68-103"> Message Repair and New Submission を使用すると、XML またはビジネス ルール エンジンの検証が失敗したメッセージを修復できます。</span><span class="sxs-lookup"><span data-stu-id="48a68-103"> Message Repair and New Submission enables you to repair a message that has failed XML or Business Rules Engine validation.</span></span> <span data-ttu-id="48a68-104">修復処理には、精度とメッセージの修復の妥当性を保証する検証と承認の手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="48a68-104">The repair process includes verification and approval steps that ensure the accuracy and appropriateness of the message repair.</span></span> <span data-ttu-id="48a68-105">このプロセスは Microsoft を使用して実行[!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] MRSR サイト内のフォームです。</span><span class="sxs-lookup"><span data-stu-id="48a68-105">This process is performed using Microsoft [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)][!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] forms within MRSR site.</span></span>  
  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="48a68-106"> このプロセスを使用して新しいメッセージを送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="48a68-106"> also enables you to submit a new message using this process.</span></span> <span data-ttu-id="48a68-107">作成者は、メッセージを送信して、ワークフローは、修理会社、検証機能をおよびメッセージ修復のように同じタスクを実行する承認者を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="48a68-107">A creator submits the message, and the workflow can include a repairer, a verifier, and an approver performing the same tasks as in message repair.</span></span>  
  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="48a68-108"> 各タスクを実行する別のユーザーを割り当てることで、このプロセスのセキュリティを確保します。</span><span class="sxs-lookup"><span data-stu-id="48a68-108"> ensures the security of this process by assigning different users to perform each task.</span></span> <span data-ttu-id="48a68-109">適切な修復を割り当てるかを確認するには、これらのユーザーの各ロールの承認を実行して、各ユーザーは、特定の証明書を使用してタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="48a68-109">You assign the appropriate repair, verify, or approve role to each of these users, and each user must use a specific certificate to perform the task.</span></span> [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="48a68-110"> 修復と送信されたメッセージの処理には、部門の使用をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="48a68-110"> also supports the use of departments in processing repaired and submitted messages.</span></span> <span data-ttu-id="48a68-111">各部門には、特定のメッセージ セットで実行するタスクの特定のワークフローが含まれます。</span><span class="sxs-lookup"><span data-stu-id="48a68-111">Each department involves a specific workflow of tasks performed on a specific set of messages.</span></span> <span data-ttu-id="48a68-112">作成のような修復、検証、または、メッセージを送信するときに、手順を承認[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]BRE 検証を呼び出すし、ユーザーが適切な部門のメンバーであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="48a68-112">In any of the create, repair, verify, or approve steps, when you submit the message, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] calls BRE validation and verifies that the user is a member of the appropriate department.</span></span> <span data-ttu-id="48a68-113">メッセージの修復と新しい送信の詳細については、次を参照してください。[メッセージ修復 and New Submission](../../adapters-and-accelerators/accelerator-swift/message-repair-and-new-submission.md)します。</span><span class="sxs-lookup"><span data-stu-id="48a68-113">For more information about message repair and new submission, see [Message Repair and New Submission](../../adapters-and-accelerators/accelerator-swift/message-repair-and-new-submission.md).</span></span>  
  
 <span data-ttu-id="48a68-114">Message Repair、未解析メッセージの受信および New Submission は、メッセージとエラーの説明が表示されます。 場合、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]が形成され、メッセージを印刷したり、ファイルに保存することができます。</span><span class="sxs-lookup"><span data-stu-id="48a68-114">If you receive an unparsed message, Message Repair and New Submission displays the message and a description of the failure in an [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form, and enables you to print the message or save it to a file.</span></span> <span data-ttu-id="48a68-115">修復し、メッセージを再送信します。</span><span class="sxs-lookup"><span data-stu-id="48a68-115">You can then repair and resubmit the message.</span></span> <span data-ttu-id="48a68-116">ただし、 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] BRE 検証を呼び出すまたは修復が未解析メッセージを送信するときに、部署内のメンバシップを確認しません。</span><span class="sxs-lookup"><span data-stu-id="48a68-116">However, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] does not call BRE validation or check membership in a department when you submit an unparsed message that you have repaired.</span></span> <span data-ttu-id="48a68-117">さらに、未解析の再送信されたメッセージが検証されません、または承認は。</span><span class="sxs-lookup"><span data-stu-id="48a68-117">In addition, a resubmitted unparsed message is not verified or approved.</span></span> <span data-ttu-id="48a68-118">未解析メッセージの詳細については、次を参照してください。[未解析メッセージの修復](../../adapters-and-accelerators/accelerator-swift/repairing-unparsed-messages.md)します。</span><span class="sxs-lookup"><span data-stu-id="48a68-118">For more information about unparsed messages, see [Repairing Unparsed Messages](../../adapters-and-accelerators/accelerator-swift/repairing-unparsed-messages.md).</span></span>  
  
 <span data-ttu-id="48a68-119">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="48a68-119">This section contains:</span></span>  
  
-   [<span data-ttu-id="48a68-120">メッセージの修復</span><span class="sxs-lookup"><span data-stu-id="48a68-120">Repairing a Message</span></span>](../../adapters-and-accelerators/accelerator-swift/repairing-a-message.md)  
  
-   [<span data-ttu-id="48a68-121">メッセージの検証</span><span class="sxs-lookup"><span data-stu-id="48a68-121">Verifying a Message</span></span>](../../adapters-and-accelerators/accelerator-swift/verifying-a-message.md)  
  
-   [<span data-ttu-id="48a68-122">メッセージの承認</span><span class="sxs-lookup"><span data-stu-id="48a68-122">Approving a Message</span></span>](../../adapters-and-accelerators/accelerator-swift/approving-a-message.md)  
  
-   [<span data-ttu-id="48a68-123">未解析メッセージの処理</span><span class="sxs-lookup"><span data-stu-id="48a68-123">Handling an Unparsed Message</span></span>](../../adapters-and-accelerators/accelerator-swift/handling-an-unparsed-message.md)  
  
-   [<span data-ttu-id="48a68-124">新しいメッセージの作成と送信</span><span class="sxs-lookup"><span data-stu-id="48a68-124">Creating and Submitting a New Message</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-and-submitting-a-new-message.md)  
  
-   [<span data-ttu-id="48a68-125">新しいメッセージ テンプレートの作成</span><span class="sxs-lookup"><span data-stu-id="48a68-125">Creating a New Message Template</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-a-new-message-template.md)