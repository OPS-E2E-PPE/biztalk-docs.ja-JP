---
title: 実行プロファイル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 98ac0a0c-91d8-4d12-aa40-2ad2e29ec784
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a1281fa77956d96e4461a91fffb737499327ef2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982091"
---
# <a name="run-as-profiles"></a><span data-ttu-id="cc2d5-102">実行プロファイル</span><span class="sxs-lookup"><span data-stu-id="cc2d5-102">Run As Profiles</span></span>
<span data-ttu-id="cc2d5-103">BizTalk Server コア ライブラリ管理パックが最初にインポートされた 2 つの新しい実行プロファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="cc2d5-103">When the BizTalk Server Core Library Management Pack is first imported, it creates two new Run As Profiles:</span></span>  
  
- <span data-ttu-id="cc2d5-104">**BizTalk Server 検出アカウント**します。</span><span class="sxs-lookup"><span data-stu-id="cc2d5-104">**BizTalk Server Discovery Account**.</span></span> <span data-ttu-id="cc2d5-105">このプロファイルは、BizTalk Server ロールのコンポーネントのすべての検出に関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="cc2d5-105">This profile is associated with all discoveries of BizTalk Server role components.</span></span>  
  
- <span data-ttu-id="cc2d5-106">**BizTalk Server の監視アカウント**します。</span><span class="sxs-lookup"><span data-stu-id="cc2d5-106">**BizTalk Server Monitoring Account**.</span></span> <span data-ttu-id="cc2d5-107">このプロファイルは、すべての監視およびタスクに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="cc2d5-107">This profile is associated with all monitors and tasks.</span></span>  
  
  <span data-ttu-id="cc2d5-108">で、既定、すべての検出、モニター、および「既定のアクション アカウント」実行プロファイルで定義されているアカウントを使用する既定の BizTalk Server 管理パックで定義されているタスク。</span><span class="sxs-lookup"><span data-stu-id="cc2d5-108">By default, all discoveries, monitors, and tasks defined in the BizTalk Server Management Packs default to using the accounts defined in the “Default Action Account” Run As Profile.</span></span>  <span data-ttu-id="cc2d5-109">特定のシステムの既定のアクション アカウントが検出または BizTalk の監視に必要なアクセス許可を持たない場合、これらのシステムは、BizTalk Server 実行プロファイルの BizTalk Server へのアクセスを持つ特定の資格情報にバインドできます。</span><span class="sxs-lookup"><span data-stu-id="cc2d5-109">If the default action account for a given system does not have the necessary permissions to discover or monitor BizTalk, then those systems can be bound to more specific credentials in the BizTalk Server Run As Profiles, which do have access to BizTalk Server.</span></span>  
  
  <span data-ttu-id="cc2d5-110">以下は、BizTalk Server の実行プロファイルを構成する汎用的な手順です。</span><span class="sxs-lookup"><span data-stu-id="cc2d5-110">The following are the generic steps to configure Run As Profiles for BizTalk Server:</span></span>  
  
### <a name="to-configure-run-as-profiles"></a><span data-ttu-id="cc2d5-111">実行プロファイルを構成するには</span><span class="sxs-lookup"><span data-stu-id="cc2d5-111">To configure Run As profiles</span></span>  
  
1.  <span data-ttu-id="cc2d5-112">既定のアクション アカウントが BizTalk Server を監視するのに十分な権限を持つ対象のコンピューターの名前を識別します。</span><span class="sxs-lookup"><span data-stu-id="cc2d5-112">Identify the name(s) of the target computer(s) where the default action account has insufficient rights to monitor BizTalk Server.</span></span>  
  
2.  <span data-ttu-id="cc2d5-113">各システムを作成または既存の BizTalk Server の権限について少なくともが資格情報のセットを使用して、[低い特権の環境](../technical-guides/low-privilege-environments.md)この管理パック ガイドの「します。</span><span class="sxs-lookup"><span data-stu-id="cc2d5-113">For each system create or use an existing set of credentials that have at least the BizTalk Server privileges discussed in the [Low-Privilege Environments](../technical-guides/low-privilege-environments.md) section of this management pack guide.</span></span>  
  
3.  <span data-ttu-id="cc2d5-114">手順 2. で識別した資格情報のセットごとに、対応する実行アカウントが、管理グループに存在するを確認します。</span><span class="sxs-lookup"><span data-stu-id="cc2d5-114">For each set of credentials identified in step 2, make sure that a corresponding Run As Account exists in the management group.</span></span> <span data-ttu-id="cc2d5-115">必要がある場合は、実行アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="cc2d5-115">Create the Run As Account if it is necessary.</span></span>  
  
4.  <span data-ttu-id="cc2d5-116">ターゲットと実行アカウントは、間のマッピングを設定、**アカウントとして実行**実行プロファイルのそれぞれのタブ。</span><span class="sxs-lookup"><span data-stu-id="cc2d5-116">Set up the mappings between the targets and the Run As Account(s) on the **Run As Accounts** tab of each of the Run As Profiles.</span></span>