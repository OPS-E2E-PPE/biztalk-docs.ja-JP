---
title: 実行プロファイル |Microsoft ドキュメント
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
ms.openlocfilehash: 69fa6c9401f606619b2fb8d22d95ded48c18a092
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22301978"
---
# <a name="run-as-profiles"></a><span data-ttu-id="6c8d0-102">実行プロファイル</span><span class="sxs-lookup"><span data-stu-id="6c8d0-102">Run As Profiles</span></span>
<span data-ttu-id="6c8d0-103">BizTalk Server コア ライブラリ管理パックが最初にインポートされると、2 つの新しい実行プロファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="6c8d0-103">When the BizTalk Server Core Library Management Pack is first imported, it creates two new Run As Profiles:</span></span>  
  
-   <span data-ttu-id="6c8d0-104">**BizTalk Server 検出アカウント**です。</span><span class="sxs-lookup"><span data-stu-id="6c8d0-104">**BizTalk Server Discovery Account**.</span></span> <span data-ttu-id="6c8d0-105">このプロファイルは、BizTalk Server ロール コンポーネントのすべての検出に関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="6c8d0-105">This profile is associated with all discoveries of BizTalk Server role components.</span></span>  
  
-   <span data-ttu-id="6c8d0-106">**BizTalk Server 監視アカウント**です。</span><span class="sxs-lookup"><span data-stu-id="6c8d0-106">**BizTalk Server Monitoring Account**.</span></span> <span data-ttu-id="6c8d0-107">このプロファイルは、すべての監視およびタスクに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="6c8d0-107">This profile is associated with all monitors and tasks.</span></span>  
  
 <span data-ttu-id="6c8d0-108">既定ですべての検出、モニター、や「既定のアクション アカウント」実行プロファイルで定義されているアカウントを使用する既定の BizTalk Server 管理パックで定義されているタスクです。</span><span class="sxs-lookup"><span data-stu-id="6c8d0-108">By default, all discoveries, monitors, and tasks defined in the BizTalk Server Management Packs default to using the accounts defined in the “Default Action Account” Run As Profile.</span></span>  <span data-ttu-id="6c8d0-109">指定したシステムの既定のアクション アカウントが検出または BizTalk の監視に必要なアクセス許可を持たない場合、これらのシステムは、BizTalk Server 実行プロファイルに、BizTalk Server へのアクセスを持つ特定の資格情報をバインドできます。</span><span class="sxs-lookup"><span data-stu-id="6c8d0-109">If the default action account for a given system does not have the necessary permissions to discover or monitor BizTalk, then those systems can be bound to more specific credentials in the BizTalk Server Run As Profiles, which do have access to BizTalk Server.</span></span>  
  
 <span data-ttu-id="6c8d0-110">BizTalk Server の実行プロファイルを構成する汎用的な手順を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6c8d0-110">The following are the generic steps to configure Run As Profiles for BizTalk Server:</span></span>  
  
### <a name="to-configure-run-as-profiles"></a><span data-ttu-id="6c8d0-111">実行プロファイルを構成するには</span><span class="sxs-lookup"><span data-stu-id="6c8d0-111">To configure Run As profiles</span></span>  
  
1.  <span data-ttu-id="6c8d0-112">既定のアクション アカウントが BizTalk Server の監視に必要な権限を持つ、対象コンピューターの名前を識別します。</span><span class="sxs-lookup"><span data-stu-id="6c8d0-112">Identify the name(s) of the target computer(s) where the default action account has insufficient rights to monitor BizTalk Server.</span></span>  
  
2.  <span data-ttu-id="6c8d0-113">各システムを作成または既存の特権を持つには、少なくとも、BizTalk Server で説明されている資格情報のセットを使用して、[低い特権の環境](../technical-guides/low-privilege-environments.md)この管理パック ガイドの「します。</span><span class="sxs-lookup"><span data-stu-id="6c8d0-113">For each system create or use an existing set of credentials that have at least the BizTalk Server privileges discussed in the [Low-Privilege Environments](../technical-guides/low-privilege-environments.md) section of this management pack guide.</span></span>  
  
3.  <span data-ttu-id="6c8d0-114">手順 2. で識別した資格情報のセットごとに、管理グループ内に対応する実行アカウントが存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="6c8d0-114">For each set of credentials identified in step 2, make sure that a corresponding Run As Account exists in the management group.</span></span> <span data-ttu-id="6c8d0-115">必要がある場合は、実行アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="6c8d0-115">Create the Run As Account if it is necessary.</span></span>  
  
4.  <span data-ttu-id="6c8d0-116">ターゲットと実行アカウントのマッピングを設定、**アカウントとして実行**の実行プロファイルは、それぞれのタブです。</span><span class="sxs-lookup"><span data-stu-id="6c8d0-116">Set up the mappings between the targets and the Run As Account(s) on the **Run As Accounts** tab of each of the Run As Profiles.</span></span>