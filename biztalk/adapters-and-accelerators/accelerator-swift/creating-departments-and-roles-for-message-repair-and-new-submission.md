---
title: Message Repair and New Submission の部門とロールの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- departments, creating
- creating, roles
- roles, requirements
- roles, creating
- creating, departments
- certificates, messages
- messages, certificates
ms.assetid: 6337bd57-63c5-4d97-b558-ac27d5eb60d7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3fbfe21ff49a8793e818215b72fe7f844cae85e5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378409"
---
# <a name="creating-departments-and-roles-for-message-repair-and-new-submission"></a><span data-ttu-id="8f8a5-102">Message Repair and New Submission の部門とロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="8f8a5-102">Creating Departments and Roles for Message Repair and New Submission</span></span>
<span data-ttu-id="8f8a5-103">Message Repair and New Submission 次の 4 つの異なる操作が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8f8a5-103">Message Repair and New Submission involves the following four different operations:</span></span>  
  
- <span data-ttu-id="8f8a5-104">検証が失敗したメッセージの修復</span><span class="sxs-lookup"><span data-stu-id="8f8a5-104">Repair of a message that has failed validation</span></span>  
  
- <span data-ttu-id="8f8a5-105">修復 (キーの更新を含む) の検証</span><span class="sxs-lookup"><span data-stu-id="8f8a5-105">Verification of the repair (including rekeying)</span></span>  
  
- <span data-ttu-id="8f8a5-106">修復の承認</span><span class="sxs-lookup"><span data-stu-id="8f8a5-106">Approval of the repair</span></span>  
  
- <span data-ttu-id="8f8a5-107">新しいメッセージの作成</span><span class="sxs-lookup"><span data-stu-id="8f8a5-107">Creation of a new message</span></span>  
  
  <span data-ttu-id="8f8a5-108">これらの操作のいずれかを実行するには、ユーザーは、操作に関連付けられているロールを想定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f8a5-108">To perform one of these operations, a user must assume the role associated with the operation.</span></span> <span data-ttu-id="8f8a5-109">役割の処理部門の (後述) の一部である必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f8a5-109">The role must also be a part of the processing department (described below).</span></span> <span data-ttu-id="8f8a5-110">ワークフローのステージを実行した後に、メッセージを送信するには、ユーザー、ユーザーに関連付けられた有効な証明書メッセージに署名する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f8a5-110">To submit the message after performing a stage in the workflow, the user must sign the message with a valid certificate associated with the user.</span></span>  
  
## <a name="creating-departments-and-roles"></a><span data-ttu-id="8f8a5-111">部門とロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="8f8a5-111">Creating Departments and Roles</span></span>  
 <span data-ttu-id="8f8a5-112">プロファイル Web クライアントのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f8a5-112">Refer Profile Web client documentation.</span></span>  
  
## <a name="rules-of-role-use"></a><span data-ttu-id="8f8a5-113">ロールの使用規則</span><span class="sxs-lookup"><span data-stu-id="8f8a5-113">Rules of Role Use</span></span>  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] <span data-ttu-id="8f8a5-114">ユーザー、ロール、および部門は、次の規則に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f8a5-114">users, roles, and departments must conform to the following rules:</span></span>  
  
- <span data-ttu-id="8f8a5-115">修復されたメッセージの完全なワークフローが、修復、検証、およびその後、メッセージを承認します。</span><span class="sxs-lookup"><span data-stu-id="8f8a5-115">The full workflow for a repaired message is to repair, verify, and then approve the message.</span></span> <span data-ttu-id="8f8a5-116">作成されたメッセージの完全なワークフローが、作成、修復、検証、およびその後、メッセージを承認します。</span><span class="sxs-lookup"><span data-stu-id="8f8a5-116">The full workflow for a created message is to create, repair, verify, and then approve the message.</span></span> <span data-ttu-id="8f8a5-117">検証と承認の手順は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="8f8a5-117">The verification and approval steps are optional.</span></span>  
  
- <span data-ttu-id="8f8a5-118">部門のワークフローは、ロールの作成または修復のロールを開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f8a5-118">A department's workflow must begin with a create role or repair role.</span></span> <span data-ttu-id="8f8a5-119">ワークフローには、両方の作成と修復の手順 (作成されたメッセージのワークフロー) が含まれている場合、修復手順の直前に作成手順があります。</span><span class="sxs-lookup"><span data-stu-id="8f8a5-119">If a workflow includes both create and repair steps (a workflow for a created message), the create step must come immediately before the repair step.</span></span>  
  
- <span data-ttu-id="8f8a5-120">作成されたメッセージのワークフローを作成する機能を持つ 1 つだけの役割を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f8a5-120">A workflow for a created message must contain one and only one role that has a capability of create.</span></span>  
  
- <span data-ttu-id="8f8a5-121">各ワークフローは、修復の機能を持つロールが 1 つだけを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f8a5-121">Each workflow must contain one and only one role that has a capability of repair.</span></span>  
  
- <span data-ttu-id="8f8a5-122">[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ユーザーが 1 つ以上のロールを関連付けることができますが、1 人のユーザーで実行できますない 1 つ以上の手順を 1 つのワークフロー。</span><span class="sxs-lookup"><span data-stu-id="8f8a5-122">An [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] user can be associated with more than one role, but no single user can execute more than one step in a single workflow.</span></span> <span data-ttu-id="8f8a5-123">たとえば、ユーザー A はメッセージを修復すると、ユーザー B がメッセージを検証、し、ユーザー A も B のユーザーを承認できますメッセージ。</span><span class="sxs-lookup"><span data-stu-id="8f8a5-123">For example, if user A repairs a message and user B verifies the message, then neither user A nor user B can approve the message.</span></span>  
  
- <span data-ttu-id="8f8a5-124">その他の役割を基準とした RekeyVerify または承認の機能を持つ RekeyVerify または承認の機能を持つロールの順序のチェックはありません。</span><span class="sxs-lookup"><span data-stu-id="8f8a5-124">There is no check on the order of roles with the capability of RekeyVerify or Approve relative to other roles with the capability of RekeyVerify or Approve.</span></span>  
  
- <span data-ttu-id="8f8a5-125">修復が既にメッセージには、もう一度検証が失敗した場合に戻る MRSR サイト ドキュメント ライブラリの修復の受信トレイです。</span><span class="sxs-lookup"><span data-stu-id="8f8a5-125">If a message that you have already repaired fails validation again, it goes back into the repair inbox in the MRSR site document library.</span></span> <span data-ttu-id="8f8a5-126">この場合、(ワークフローの役割を実行したユーザーが既にに基づく) の検証と承認者のロールでは、以前の制限は適用されません。</span><span class="sxs-lookup"><span data-stu-id="8f8a5-126">When this happens, the previous limitations on the verification and approver roles (based on who has already performed a role in the workflow) no longer apply.</span></span> <span data-ttu-id="8f8a5-127">たとえば、メッセージ、ユーザー B を A のユーザーの修復には、検証、およびユーザー A の修復でメッセージが拒否された場合メッセージし、ユーザー B は別のユーザーに、もう一度でしたメッセージを確認します。</span><span class="sxs-lookup"><span data-stu-id="8f8a5-127">For example, if user A repairs a message, user B rejects the message in verification, and user A repairs the message a second time, then a user other than user B could verify the message.</span></span> <span data-ttu-id="8f8a5-128">場合は、ユーザー B がメッセージを承認します。</span><span class="sxs-lookup"><span data-stu-id="8f8a5-128">If that is the case, then user B could approve the message.</span></span> <span data-ttu-id="8f8a5-129">別の例されている場合、ユーザー A はメッセージを作成、ユーザー B は検証フェーズでメッセージを拒否、およびユーザー C は、メッセージを修復し、ユーザー A は、メッセージを確認できます。</span><span class="sxs-lookup"><span data-stu-id="8f8a5-129">Another example is that if user A creates a message, user B rejects the message in verification, and user C repairs the message, then user A could verify the message.</span></span>  
  
- <span data-ttu-id="8f8a5-130">[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]検証が失敗した場合、メッセージを作成するユーザーはそのメッセージを修復もできます。</span><span class="sxs-lookup"><span data-stu-id="8f8a5-130">An [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] user who creates a message can also repair that message if it fails validation.</span></span>  
  
- <span data-ttu-id="8f8a5-131">のみ[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ワークフローに関連付けられている部門のユーザーはワークフローのステップを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="8f8a5-131">Only [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] users in the department associated with a workflow can perform a step in the workflow.</span></span> <span data-ttu-id="8f8a5-132">ときに、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ユーザーが、メッセージを送信する[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]メッセージに関連付けられている部門のユーザーがロールを持っていることを確認します (ユーザー プロファイル (この場合、部門は、既定ではありません) web クライアントのプロファイルで)。</span><span class="sxs-lookup"><span data-stu-id="8f8a5-132">When an [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] user submits a message, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] verifies that the user has a role in the department associated with the message (through the User profiles (in case the department is not default) in Profile web client).</span></span>  
  
- <span data-ttu-id="8f8a5-133">管理者が、1 つを与える[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ユーザーの部門内の複数のロール。</span><span class="sxs-lookup"><span data-stu-id="8f8a5-133">An administrator can give a single [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] user multiple roles within a department.</span></span> <span data-ttu-id="8f8a5-134">1 人のユーザーには、修復、検証、承認、または作成、またはこれらのロールは、上記で説明した任意の 1 つのワークフローでの制限が適用の任意のサブセットを実行できます。</span><span class="sxs-lookup"><span data-stu-id="8f8a5-134">A single user can perform repair, verification, approval, or creation, or any subset of those roles, subject to the limitations on any one workflow described above.</span></span>  
  
## <a name="certificates"></a><span data-ttu-id="8f8a5-135">証明書</span><span class="sxs-lookup"><span data-stu-id="8f8a5-135">Certificates</span></span>  
 <span data-ttu-id="8f8a5-136">修復、検証、承認、または、作成した後、ローカル コンピューター上のメッセージを送信する、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ユーザーが自分の証明書をメッセージに署名する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f8a5-136">To submit a message on your local computer after repair, verification, approval, or creation, the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] user must sign the message with his or her certificate.</span></span> <span data-ttu-id="8f8a5-137">証明書の作成の詳細については、次を参照してください。[証明書のインストール](../../adapters-and-accelerators/accelerator-swift/installing-certificates.md)します。</span><span class="sxs-lookup"><span data-stu-id="8f8a5-137">For more information about creating certificates, see [Installing Certificates](../../adapters-and-accelerators/accelerator-swift/installing-certificates.md).</span></span>  
  
 <span data-ttu-id="8f8a5-138">修復、確認、承認、またはリモート クライアント コンピューターから MRSR サイトへのアクセス、メッセージを作成して、ユーザーは、(ユーザーが自身のクライアント コンピューターの現在のユーザー/個人/証明書ストアに証明書で自分の証明書を追加する必要があります。そのためには管理者である)。</span><span class="sxs-lookup"><span data-stu-id="8f8a5-138">To be able to repair, verify, approve, or create a message by accessing the MRSR site from a remote client computer, the user must add his or her certificate in the Certificates - Current User/Personal/Certificates store of their client computer (the user does not have to be an administrator to do so).</span></span> <span data-ttu-id="8f8a5-139">さらに、サーバーの管理者する必要がありますユーザーの証明書 (および、クライアント コンピューターからサーバーにアクセスする他のユーザーの)、証明書を追加 (ローカル コンピューター)]、[その他のユーザー/証明書がサーバーに格納します。</span><span class="sxs-lookup"><span data-stu-id="8f8a5-139">In addition, an administrator on the server must add the user's certificate (and those of any other users who access the server from their client computer) to the Certificates (Local Computer)/Other People/Certificates store on the server.</span></span>  
  
 <span data-ttu-id="8f8a5-140">1 人のユーザーは、いくつかの割り当てられたロールがあり、それらのロールのいずれかを実行するときに、同じ証明書を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f8a5-140">A single user might have several allotted roles, and should use the same certificate when performing any of those roles.</span></span>