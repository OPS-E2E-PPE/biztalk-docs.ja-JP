---
title: Message Repair and New Submission の部門とロールの作成 |Microsoft ドキュメント
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
ms.openlocfilehash: d033ab3910657373f6e48b1f6e6bed076f730b51
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210538"
---
# <a name="creating-departments-and-roles-for-message-repair-and-new-submission"></a><span data-ttu-id="88677-102">Message Repair and New Submission の部門とロールの作成</span><span class="sxs-lookup"><span data-stu-id="88677-102">Creating Departments and Roles for Message Repair and New Submission</span></span>
<span data-ttu-id="88677-103">Message Repair and New Submission には、次の 4 つの異なる操作が含まれます。</span><span class="sxs-lookup"><span data-stu-id="88677-103">Message Repair and New Submission involves the following four different operations:</span></span>  
  
-   <span data-ttu-id="88677-104">検証が失敗したメッセージの修復</span><span class="sxs-lookup"><span data-stu-id="88677-104">Repair of a message that has failed validation</span></span>  
  
-   <span data-ttu-id="88677-105">修復 (キー更新を含む) の検証</span><span class="sxs-lookup"><span data-stu-id="88677-105">Verification of the repair (including rekeying)</span></span>  
  
-   <span data-ttu-id="88677-106">修復の承認</span><span class="sxs-lookup"><span data-stu-id="88677-106">Approval of the repair</span></span>  
  
-   <span data-ttu-id="88677-107">新しいメッセージの作成</span><span class="sxs-lookup"><span data-stu-id="88677-107">Creation of a new message</span></span>  
  
 <span data-ttu-id="88677-108">これらの操作のいずれかを実行するには、ユーザーは、操作に関連付けられている役割を想定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="88677-108">To perform one of these operations, a user must assume the role associated with the operation.</span></span> <span data-ttu-id="88677-109">ロールは、処理部門の (後述) の一部もあります。</span><span class="sxs-lookup"><span data-stu-id="88677-109">The role must also be a part of the processing department (described below).</span></span> <span data-ttu-id="88677-110">をワークフローにステージを実行した後、メッセージを送信するには、ユーザー、ユーザーに関連付けられた有効な証明書メッセージに署名する必要があります。</span><span class="sxs-lookup"><span data-stu-id="88677-110">To submit the message after performing a stage in the workflow, the user must sign the message with a valid certificate associated with the user.</span></span>  
  
## <a name="creating-departments-and-roles"></a><span data-ttu-id="88677-111">部門とロールの作成</span><span class="sxs-lookup"><span data-stu-id="88677-111">Creating Departments and Roles</span></span>  
 <span data-ttu-id="88677-112">プロファイルの Web クライアントのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="88677-112">Refer Profile Web client documentation.</span></span>  
  
## <a name="rules-of-role-use"></a><span data-ttu-id="88677-113">ロールの使用の規則</span><span class="sxs-lookup"><span data-stu-id="88677-113">Rules of Role Use</span></span>  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="88677-114">ユーザー、ロール、および部門は、次の規則に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="88677-114"> users, roles, and departments must conform to the following rules:</span></span>  
  
-   <span data-ttu-id="88677-115">修復されたメッセージの完全ワークフローでは、修復、検証、およびメッセージを承認します。</span><span class="sxs-lookup"><span data-stu-id="88677-115">The full workflow for a repaired message is to repair, verify, and then approve the message.</span></span> <span data-ttu-id="88677-116">作成したメッセージの完全ワークフローでは、作成、修復、検証、およびメッセージを承認します。</span><span class="sxs-lookup"><span data-stu-id="88677-116">The full workflow for a created message is to create, repair, verify, and then approve the message.</span></span> <span data-ttu-id="88677-117">検証と承認の手順は省略できます。</span><span class="sxs-lookup"><span data-stu-id="88677-117">The verification and approval steps are optional.</span></span>  
  
-   <span data-ttu-id="88677-118">部門のワークフローは、ロールの作成または修復のロールで始まる必要があります。</span><span class="sxs-lookup"><span data-stu-id="88677-118">A department's workflow must begin with a create role or repair role.</span></span> <span data-ttu-id="88677-119">ワークフローには、作成と修復の両方の手順 (のワークフローを作成したメッセージ) が含まれている場合、修復手順の直前に作成する手順を引き起こすことがあります。</span><span class="sxs-lookup"><span data-stu-id="88677-119">If a workflow includes both create and repair steps (a workflow for a created message), the create step must come immediately before the repair step.</span></span>  
  
-   <span data-ttu-id="88677-120">作成したメッセージのワークフローを作成する機能を持つ 1 つだけの役割を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="88677-120">A workflow for a created message must contain one and only one role that has a capability of create.</span></span>  
  
-   <span data-ttu-id="88677-121">各ワークフローでは、修復の機能を持つ 1 つだけの役割を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="88677-121">Each workflow must contain one and only one role that has a capability of repair.</span></span>  
  
-   <span data-ttu-id="88677-122">[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ユーザーは、複数のロールを関連付けることができますが、1 人のユーザーはも実行されない 1 つ以上の手順で 1 つのワークフローです。</span><span class="sxs-lookup"><span data-stu-id="88677-122">An [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] user can be associated with more than one role, but no single user can execute more than one step in a single workflow.</span></span> <span data-ttu-id="88677-123">たとえば、ユーザー A はメッセージを修復すると、ユーザー B がメッセージを検証、し、ユーザー A も B のユーザーを承認できますメッセージ。</span><span class="sxs-lookup"><span data-stu-id="88677-123">For example, if user A repairs a message and user B verifies the message, then neither user A nor user B can approve the message.</span></span>  
  
-   <span data-ttu-id="88677-124">その他のロール基準とした RekeyVerify または承認の機能を持つ RekeyVerify または承認の機能を持つロールの順序のチェックはありません。</span><span class="sxs-lookup"><span data-stu-id="88677-124">There is no check on the order of roles with the capability of RekeyVerify or Approve relative to other roles with the capability of RekeyVerify or Approve.</span></span>  
  
-   <span data-ttu-id="88677-125">既にに修復をメッセージには、もう一度検証が失敗した場合に戻る MRSR サイト ドキュメント ライブラリで修復の受信トレイです。</span><span class="sxs-lookup"><span data-stu-id="88677-125">If a message that you have already repaired fails validation again, it goes back into the repair inbox in the MRSR site document library.</span></span> <span data-ttu-id="88677-126">この場合、(ワークフロー内のロールを実行したユーザーが既にに基づいた) の検証および承認者の役割は、以前の制限は適用されません。</span><span class="sxs-lookup"><span data-stu-id="88677-126">When this happens, the previous limitations on the verification and approver roles (based on who has already performed a role in the workflow) no longer apply.</span></span> <span data-ttu-id="88677-127">たとえば、メッセージ、ユーザー B のユーザー A 修復検証、およびユーザー A の修復でメッセージを拒否した場合は、メッセージし、ユーザー B は別のユーザーに、もう一度でしたメッセージを確認します。</span><span class="sxs-lookup"><span data-stu-id="88677-127">For example, if user A repairs a message, user B rejects the message in verification, and user A repairs the message a second time, then a user other than user B could verify the message.</span></span> <span data-ttu-id="88677-128">場合は、ユーザー B の間でメッセージが承認可能性があります。</span><span class="sxs-lookup"><span data-stu-id="88677-128">If that is the case, then user B could approve the message.</span></span> <span data-ttu-id="88677-129">別の例です。 ユーザー A がメッセージを作成し、ユーザー B は、検証でメッセージを拒否し、ユーザー C は、メッセージを修復し、ユーザー A はメッセージを確認できます。</span><span class="sxs-lookup"><span data-stu-id="88677-129">Another example is that if user A creates a message, user B rejects the message in verification, and user C repairs the message, then user A could verify the message.</span></span>  
  
-   <span data-ttu-id="88677-130">[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]検証が失敗した場合、メッセージを作成したユーザーはそのメッセージを修復もできます。</span><span class="sxs-lookup"><span data-stu-id="88677-130">An [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] user who creates a message can also repair that message if it fails validation.</span></span>  
  
-   <span data-ttu-id="88677-131">のみ[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ワークフローに関連付けられている部門のユーザーには、ワークフローで、手順を実行できます。</span><span class="sxs-lookup"><span data-stu-id="88677-131">Only [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] users in the department associated with a workflow can perform a step in the workflow.</span></span> <span data-ttu-id="88677-132">ときに、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ユーザーは、メッセージを送信する[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]メッセージに関連付けられている部門のユーザーがロールを持っていることを確認 (を通じて、ユーザー プロファイル (この場合、部門は、既定ではありません) にプロファイル web クライアント)。</span><span class="sxs-lookup"><span data-stu-id="88677-132">When an [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] user submits a message, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] verifies that the user has a role in the department associated with the message (through the User profiles (in case the department is not default) in Profile web client).</span></span>  
  
-   <span data-ttu-id="88677-133">管理者は、1 つを移すことができる[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ユーザーの部門内の複数の役割です。</span><span class="sxs-lookup"><span data-stu-id="88677-133">An administrator can give a single [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] user multiple roles within a department.</span></span> <span data-ttu-id="88677-134">1 人のユーザーには、修復、検証、承認、または作成、またはそれらのロールは、上記で説明した任意の 1 つのワークフローでの制限が適用の任意のサブセットを実行できます。</span><span class="sxs-lookup"><span data-stu-id="88677-134">A single user can perform repair, verification, approval, or creation, or any subset of those roles, subject to the limitations on any one workflow described above.</span></span>  
  
## <a name="certificates"></a><span data-ttu-id="88677-135">証明書</span><span class="sxs-lookup"><span data-stu-id="88677-135">Certificates</span></span>  
 <span data-ttu-id="88677-136">修復、検証、承認、または、作成した後、ローカル コンピューター上のメッセージを送信する、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ユーザーが自分の証明書をメッセージに署名する必要があります。</span><span class="sxs-lookup"><span data-stu-id="88677-136">To submit a message on your local computer after repair, verification, approval, or creation, the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] user must sign the message with his or her certificate.</span></span> <span data-ttu-id="88677-137">証明書の作成の詳細については、次を参照してください。[証明書のインストール](../../adapters-and-accelerators/accelerator-swift/installing-certificates.md)です。</span><span class="sxs-lookup"><span data-stu-id="88677-137">For more information about creating certificates, see [Installing Certificates](../../adapters-and-accelerators/accelerator-swift/installing-certificates.md).</span></span>  
  
 <span data-ttu-id="88677-138">修復、ことを確認、承認、またはリモート クライアント コンピューターから MRSR サイトへのアクセス、メッセージを作成するには、ユーザーは、(ユーザーが、クライアント コンピューターの現在のユーザー/個人/証明書ストアに証明書で、ユーザー証明書を追加する必要があります。そのためには管理者である)。</span><span class="sxs-lookup"><span data-stu-id="88677-138">To be able to repair, verify, approve, or create a message by accessing the MRSR site from a remote client computer, the user must add his or her certificate in the Certificates - Current User/Personal/Certificates store of their client computer (the user does not have to be an administrator to do so).</span></span> <span data-ttu-id="88677-139">さらに、サーバーの管理者である必要がありますユーザーの証明書 (および追加、クライアント コンピューターから、サーバーにアクセスできる他のユーザーの) 証明書 (ローカル コンピューター) に/その他のユーザー/証明書がサーバーに格納します。</span><span class="sxs-lookup"><span data-stu-id="88677-139">In addition, an administrator on the server must add the user's certificate (and those of any other users who access the server from their client computer) to the Certificates (Local Computer)/Other People/Certificates store on the server.</span></span>  
  
 <span data-ttu-id="88677-140">1 人のユーザーは、いくつかの割り当てられた役割があり、これらのロールのいずれかを実行するときに、同じ証明書を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="88677-140">A single user might have several allotted roles, and should use the same certificate when performing any of those roles.</span></span>