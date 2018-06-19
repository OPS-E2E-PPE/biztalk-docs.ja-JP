---
title: 使用量ルールの検証を削除する |Microsoft ドキュメント
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
ms.openlocfilehash: 017184e5f530096dc0ca166fdaaa9810a3372cfa
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25962120"
---
# <a name="removing-usage-rule-validation"></a><span data-ttu-id="7ecb8-102">使用量ルールの検証を削除します。</span><span class="sxs-lookup"><span data-stu-id="7ecb8-102">Removing Usage Rule Validation</span></span>
<span data-ttu-id="7ecb8-103">使用に関する規則は SWIFT 標準で定義され、によって強制[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]メッセージの種類ごとに固有のビジネス ポリシー。</span><span class="sxs-lookup"><span data-stu-id="7ecb8-103">Usage rules are defined in SWIFT standards and enforced by [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] business policies specific to each message type.</span></span> <span data-ttu-id="7ecb8-104">これらの使用に関する規則は、使用できるフィールドの追加の検証を提供するガイドラインを示します。</span><span class="sxs-lookup"><span data-stu-id="7ecb8-104">These usage rules are guidelines that you can use to provide extra validation for a field.</span></span> <span data-ttu-id="7ecb8-105">ネットワーク検証ルールは、必須とは異なり、メッセージ型の使用状況規則を必要とならないを選択できます。</span><span class="sxs-lookup"><span data-stu-id="7ecb8-105">Unlike network validation rules, which are mandatory, you can choose not to require usage rules for a message type.</span></span> <span data-ttu-id="7ecb8-106">場合がある場合は、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="7ecb8-106">If that is the case, you can do either of the following:</span></span>  
  
-   <span data-ttu-id="7ecb8-107">メッセージの種類の検証ポリシーから使用状況規則を適用する特定のビジネス ルールを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="7ecb8-107">You can remove a specific business rule that enforces a usage rule from the message-type validation policy.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="7ecb8-108">ポリシーから、ルールの削除が完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="7ecb8-108">Removing a rule from the policy will remove it permanently.</span></span>  
  
-   <span data-ttu-id="7ecb8-109">いずれかの使用状況規則を適用しないようにする場合は、メッセージの種類の検証ポリシーを展開解除することができます。</span><span class="sxs-lookup"><span data-stu-id="7ecb8-109">If you do not want to enforce any of the usage rules, you can undeploy the validation policy for a message type.</span></span>  
  
### <a name="to-remove-a-rule-from-a-policy"></a><span data-ttu-id="7ecb8-110">ポリシーのルールを削除するには</span><span class="sxs-lookup"><span data-stu-id="7ecb8-110">To remove a rule from a policy</span></span>  
  
1.  <span data-ttu-id="7ecb8-111">メモ帳などのテキスト エディターで開いて検証ポリシーで MT103_Validation_Policy など、変更する*\<ドライブ\>*: \Program Files\ Microsoft BizTalk Accelerator 用 SWIFT \<バージョン\>メッセージ Pack\SWIFT Messages\A4SWIFT SRG\<バージョン\>\Category 1\MT103 です。</span><span class="sxs-lookup"><span data-stu-id="7ecb8-111">In a text editor, such as Notepad, open the validation policy that you want to change, for example, MT103_Validation_Policy in *\<drive\>*:\Program Files\ Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version\>\Category 1\MT103.</span></span>  
  
2.  <span data-ttu-id="7ecb8-112">できませんし、ポリシーを保存し、ルール ノードを削除します。</span><span class="sxs-lookup"><span data-stu-id="7ecb8-112">Remove the rule node that you do not want, and then save the policy.</span></span>  
  
3.  <span data-ttu-id="7ecb8-113">ビジネス ルール エンジン展開ウィザードを使用して、公開したり、ポリシーを展開します。</span><span class="sxs-lookup"><span data-stu-id="7ecb8-113">Use the Business Rules Engine Deployment Wizard to publish and deploy the policy.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7ecb8-114">ポリシーのコピーを作成する、特定の規則を削除して、変更されたポリシーを展開し、検証ポリシーからルールを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="7ecb8-114">You can also remove a rule from a validation policy by creating a copy of the policy, removing the specific rule, and then deploying the modified policy.</span></span> <span data-ttu-id="7ecb8-115">以前のバージョンのポリシーを展開解除します。</span><span class="sxs-lookup"><span data-stu-id="7ecb8-115">Undeploy the previous version of the policy.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7ecb8-116">ビジネス ルール作成ツールには、パブリッシュまたは配置済みのポリシーから規則を削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="7ecb8-116">In Business Rule Composer, you cannot delete a rule from a published or deployed policy.</span></span>  
  
### <a name="to-remove-the-policy-for-a-message-type"></a><span data-ttu-id="7ecb8-117">メッセージの種類のポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="7ecb8-117">To remove the policy for a message type</span></span>  
  
1.  <span data-ttu-id="7ecb8-118">をクリックして**開始**、 をポイント**プログラム**、 をポイント**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリック**ビジネス ルール作成ツール**です。</span><span class="sxs-lookup"><span data-stu-id="7ecb8-118">Click **Start**, point to **Programs**, point to **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)], and then click **Business Rule Composer**.</span></span>  
  
2.  <span data-ttu-id="7ecb8-119">ポリシー エクスプ ローラーには、MT103_Validation_Policy など、メッセージの種類の展開の検証ポリシーを検索します。</span><span class="sxs-lookup"><span data-stu-id="7ecb8-119">In Policy Explorer, find the deployed validation policy for the message type, for example, MT103_Validation_Policy.</span></span>  
  
3.  <span data-ttu-id="7ecb8-120">ポリシーを右クリックし、をクリックして**Undeploy**、 をクリックして**削除**、順にクリック**はい**です。</span><span class="sxs-lookup"><span data-stu-id="7ecb8-120">Right-click the policy, click **Undeploy**, click **Delete**, and then click **Yes**.</span></span>