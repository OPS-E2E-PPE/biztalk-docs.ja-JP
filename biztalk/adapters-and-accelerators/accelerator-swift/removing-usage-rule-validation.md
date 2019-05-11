---
title: 使用規則の検証を削除する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- policies, deleting rules
- rules
ms.assetid: b2b0dabf-8f99-4b85-95da-6bbf3e79ad41
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb3747ca3cf950ecb7897ff9e77b9d46950296e0
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530229"
---
# <a name="removing-usage-rule-validation"></a><span data-ttu-id="85265-102">使用規則の検証を削除します。</span><span class="sxs-lookup"><span data-stu-id="85265-102">Removing Usage Rule Validation</span></span>
<span data-ttu-id="85265-103">使用に関する規則は SWIFT 標準で定義され、によって適用される[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]メッセージの種類ごとに固有のビジネス ポリシー。</span><span class="sxs-lookup"><span data-stu-id="85265-103">Usage rules are defined in SWIFT standards and enforced by [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] business policies specific to each message type.</span></span> <span data-ttu-id="85265-104">これらの使用に関する規則では、フィールドの追加の検証を提供する際のガイドラインを示します。</span><span class="sxs-lookup"><span data-stu-id="85265-104">These usage rules are guidelines that you can use to provide extra validation for a field.</span></span> <span data-ttu-id="85265-105">必須のネットワークの検証規則とは異なり、メッセージ型の使用に関する規則を必要としないを選択できます。</span><span class="sxs-lookup"><span data-stu-id="85265-105">Unlike network validation rules, which are mandatory, you can choose not to require usage rules for a message type.</span></span> <span data-ttu-id="85265-106">ケースがある場合は、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="85265-106">If that is the case, you can do either of the following:</span></span>  

-   <span data-ttu-id="85265-107">メッセージの種類の検証ポリシーから使用状況規則を適用する特定のビジネス ルールを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="85265-107">You can remove a specific business rule that enforces a usage rule from the message-type validation policy.</span></span>  

    > [!IMPORTANT]
    >  <span data-ttu-id="85265-108">ポリシーから、ルールの削除が完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="85265-108">Removing a rule from the policy will remove it permanently.</span></span>  

-   <span data-ttu-id="85265-109">使用状況規則を適用しない場合のメッセージの種類の検証ポリシーの展開を解除できます。</span><span class="sxs-lookup"><span data-stu-id="85265-109">If you do not want to enforce any of the usage rules, you can undeploy the validation policy for a message type.</span></span>  

### <a name="to-remove-a-rule-from-a-policy"></a><span data-ttu-id="85265-110">ポリシーのルールを削除するには</span><span class="sxs-lookup"><span data-stu-id="85265-110">To remove a rule from a policy</span></span>  

1.  <span data-ttu-id="85265-111">メモ帳などのテキスト エディターで、たとえばで MT103_Validation_Policy を変更する検証ポリシーを開きます*\<ドライブ\>*: Microsoft BizTalk Accelerator for SWIFT \ProgramFiles\\<バージョン\>メッセージ Pack\SWIFT Messages\A4SWIFT-SRG\<バージョン\>\Category 1\MT103 します。</span><span class="sxs-lookup"><span data-stu-id="85265-111">In a text editor, such as Notepad, open the validation policy that you want to change, for example, MT103_Validation_Policy in *\<drive\>*:\Program Files\ Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version\>\Category 1\MT103.</span></span>  

2.  <span data-ttu-id="85265-112">できませんし、ポリシーを保存ルール ノードを削除します。</span><span class="sxs-lookup"><span data-stu-id="85265-112">Remove the rule node that you do not want, and then save the policy.</span></span>  

3.  <span data-ttu-id="85265-113">ビジネス ルール エンジン展開ウィザードを使用して、発行し、ポリシーを展開します。</span><span class="sxs-lookup"><span data-stu-id="85265-113">Use the Business Rules Engine Deployment Wizard to publish and deploy the policy.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="85265-114">ポリシーのコピーを作成する、特定のルールを削除して、変更したポリシーを展開し、検証ポリシーからルールを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="85265-114">You can also remove a rule from a validation policy by creating a copy of the policy, removing the specific rule, and then deploying the modified policy.</span></span> <span data-ttu-id="85265-115">以前のバージョンのポリシーを展開解除します。</span><span class="sxs-lookup"><span data-stu-id="85265-115">Undeploy the previous version of the policy.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="85265-116">ビジネス ルール作成ツールでは、発行またはデプロイされたポリシーからルールを削除できません。</span><span class="sxs-lookup"><span data-stu-id="85265-116">In Business Rule Composer, you cannot delete a rule from a published or deployed policy.</span></span>  

### <a name="to-remove-the-policy-for-a-message-type"></a><span data-ttu-id="85265-117">メッセージの種類のポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="85265-117">To remove the policy for a message type</span></span>  

1. <span data-ttu-id="85265-118">クリックして**開始**、 をポイント**プログラム**、 をポイント**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリックします**ビジネス ルール作成ツール**します。</span><span class="sxs-lookup"><span data-stu-id="85265-118">Click **Start**, point to **Programs**, point to **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)], and then click **Business Rule Composer**.</span></span>  

2. <span data-ttu-id="85265-119">ポリシー エクスプ ローラーでは、メッセージの種類、MT103_Validation_Policy などの展開の検証ポリシーを紹介します。</span><span class="sxs-lookup"><span data-stu-id="85265-119">In Policy Explorer, find the deployed validation policy for the message type, for example, MT103_Validation_Policy.</span></span>  

3. <span data-ttu-id="85265-120">ポリシーを右クリックし、をクリックして**Undeploy**、 をクリックして**削除**、順にクリックします**はい**します。</span><span class="sxs-lookup"><span data-stu-id="85265-120">Right-click the policy, click **Undeploy**, click **Delete**, and then click **Yes**.</span></span>
