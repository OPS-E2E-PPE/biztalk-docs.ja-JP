---
title: 移行とアップグレードのトラブルシューティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- upgrading, troubleshooting
- troubleshooting, upgrading
- troubleshooting, migrating
- migrating, troubleshooting
ms.assetid: 6e6c0ff9-7897-4de6-9e9b-b502b3a1785b
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad7f575038257bc876e3fc822e624e91c93451ff
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994643"
---
# <a name="migration-and-upgrade-troubleshooting"></a><span data-ttu-id="ad63f-102">移行とアップグレードのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="ad63f-102">Migration and Upgrade Troubleshooting</span></span>
## <a name="assemblies-need-to-be-undeployed-before-an-upgrade"></a><span data-ttu-id="ad63f-103">アセンブリは、アップグレードの前に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad63f-103">Assemblies need to be undeployed before an upgrade</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="ad63f-104">現象</span><span class="sxs-lookup"><span data-stu-id="ad63f-104">Symptom</span></span>  
 <span data-ttu-id="ad63f-105">A4SWIFT をアップグレードしようとしたときに、アップグレード プロセスは失敗します。</span><span class="sxs-lookup"><span data-stu-id="ad63f-105">When you attempt to upgrade A4SWIFT, the upgrade process fails.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="ad63f-106">考えられる原因</span><span class="sxs-lookup"><span data-stu-id="ad63f-106">Possible Cause</span></span>  
 <span data-ttu-id="ad63f-107">アップグレードが完了したら、次の A4SWIFT アセンブリは引き続き展開: Microsoft.Solutions.FinancialServices.SWIFT.FrrOrchestration、Microsoft.Solutions.FinancialServices.SWIFT.FrrSchemas、Microsoft.Solutions.FinancialServices.SWIFT.MrsrService します。</span><span class="sxs-lookup"><span data-stu-id="ad63f-107">The following A4SWIFT assemblies are still deployed when the upgrade is done:  Microsoft.Solutions.FinancialServices.SWIFT.FrrOrchestration, Microsoft.Solutions.FinancialServices.SWIFT.FrrSchemas, Microsoft.Solutions.FinancialServices.SWIFT.MrsrService.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ad63f-108">Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas を再デプロイする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ad63f-108">You do not have to redeploy Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.</span></span> <span data-ttu-id="ad63f-109">インストール プログラムは、そのアセンブリを再デプロイします。</span><span class="sxs-lookup"><span data-stu-id="ad63f-109">The installation program redeploys that assembly.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="ad63f-110">解決方法</span><span class="sxs-lookup"><span data-stu-id="ad63f-110">Solution</span></span>  
 <span data-ttu-id="ad63f-111">次の順序で 4 つの A4SWIFT アセンブリを手動で解除するには。</span><span class="sxs-lookup"><span data-stu-id="ad63f-111">Manually undeploy the four A4SWIFT assemblies in the following order:</span></span>  
  
- <span data-ttu-id="ad63f-112">Microsoft.Solutions.FinancialServices.SWIFT.FrrOrchestration</span><span class="sxs-lookup"><span data-stu-id="ad63f-112">Microsoft.Solutions.FinancialServices.SWIFT.FrrOrchestration</span></span>  
  
- <span data-ttu-id="ad63f-113">Microsoft.Solutions.FinancialServices.SWIFT.FrrSchemas</span><span class="sxs-lookup"><span data-stu-id="ad63f-113">Microsoft.Solutions.FinancialServices.SWIFT.FrrSchemas</span></span>  
  
- <span data-ttu-id="ad63f-114">Microsoft.Solutions.FinancialServices.SWIFT.MrsrService します。</span><span class="sxs-lookup"><span data-stu-id="ad63f-114">Microsoft.Solutions.FinancialServices.SWIFT.MrsrService.</span></span>  
  
  <span data-ttu-id="ad63f-115">にアップグレードした後は、これらのアセンブリを再デプロイ (を使用して**BTSTask.exe**) 逆の順序で。</span><span class="sxs-lookup"><span data-stu-id="ad63f-115">After you have upgraded, redeploy these assemblies (using **BTSTask.exe**) in the reverse order.</span></span>  
  
## <a name="an-upgrade-removes-access-permissions-for-the-service-folder"></a><span data-ttu-id="ad63f-116">アップグレードは、サービスのフォルダーのアクセス許可を削除します。</span><span class="sxs-lookup"><span data-stu-id="ad63f-116">An upgrade removes access permissions for the Service folder</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="ad63f-117">現象</span><span class="sxs-lookup"><span data-stu-id="ad63f-117">Symptom</span></span>  
 <span data-ttu-id="ad63f-118">アップグレード後[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]、%programfiles%\Microsoft BizTalk Accelerator for SWIFT\Service フォルダーに対するアクセス許可が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="ad63f-118">After an upgrade to [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)], the access permission for the %programfiles%\Microsoft BizTalk Accelerator for SWIFT\Service folder is incorrect.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="ad63f-119">考えられる原因</span><span class="sxs-lookup"><span data-stu-id="ad63f-119">Possible Cause</span></span>  
 <span data-ttu-id="ad63f-120">アップグレードすると[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]、アップグレード プロセスは、%programfiles%\Microsoft BizTalk Accelerator for SWIFT\Service フォルダーから A4SWIFT 管理者と A4SWIFT ユーザーのグループのアクセス許可を削除します。</span><span class="sxs-lookup"><span data-stu-id="ad63f-120">When you upgrade to [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)], the upgrade process removes access permissions for the A4SWIFT Administrators and A4SWIFT Users groups from the %programfiles%\Microsoft BizTalk Accelerator for SWIFT\Service folder.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="ad63f-121">解決方法</span><span class="sxs-lookup"><span data-stu-id="ad63f-121">Solution</span></span>  
 <span data-ttu-id="ad63f-122">この問題が発生した場合、サービスのフォルダーの次のアクセス許可を手動で設定します。</span><span class="sxs-lookup"><span data-stu-id="ad63f-122">If you encounter this problem, manually set the following access permissions for the Service folder:</span></span>  
  
|<span data-ttu-id="ad63f-123">[グループ名またはユーザー名]</span><span class="sxs-lookup"><span data-stu-id="ad63f-123">Group or User Name</span></span>|<span data-ttu-id="ad63f-124">権限</span><span class="sxs-lookup"><span data-stu-id="ad63f-124">Permission</span></span>|  
|------------------------|----------------|  
|<span data-ttu-id="ad63f-125">A4SWIFT 管理者</span><span class="sxs-lookup"><span data-stu-id="ad63f-125">A4SWIFT Administrators</span></span>|<span data-ttu-id="ad63f-126">フル コントロール</span><span class="sxs-lookup"><span data-stu-id="ad63f-126">Full Control</span></span>|  
|<span data-ttu-id="ad63f-127">A4SWIFT ユーザー</span><span class="sxs-lookup"><span data-stu-id="ad63f-127">A4SWIFT Users</span></span>|<span data-ttu-id="ad63f-128">読み取りと実行</span><span class="sxs-lookup"><span data-stu-id="ad63f-128">Read & Execute</span></span>|  
  
 <span data-ttu-id="ad63f-129">これらのアクセス許可を設定するには、ように進めます。</span><span class="sxs-lookup"><span data-stu-id="ad63f-129">To set these permissions, proceed as follows:</span></span>  
  
 <span data-ttu-id="ad63f-130">[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーに移動 *%programfiles%* \Microsoft BizTalk Accelerator for SWIFT\Service します。</span><span class="sxs-lookup"><span data-stu-id="ad63f-130">In [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, move to *%programfiles%* \Microsoft BizTalk Accelerator for SWIFT\Service.</span></span>  
  
1.  <span data-ttu-id="ad63f-131">サービスのフォルダーを右クリックし、をクリックして**プロパティ**、 をクリックし、**セキュリティ**タブ。</span><span class="sxs-lookup"><span data-stu-id="ad63f-131">Right-click the Service folder, click **Properties**, and then click the **Security** tab.</span></span>  
  
2.  <span data-ttu-id="ad63f-132">グループまたはユーザー名ペインで、サービスのプロパティ ダイアログ ボックスの次のようにクリックします**追加**、入力 ***\<サーバー名\>* \A4SWIFT 管理者**、 をクリックし、 **ok。**.</span><span class="sxs-lookup"><span data-stu-id="ad63f-132">In the Group or user names pane of the Service Properties dialog box, click **Add**, enter ***\<server name\>*\A4SWIFT Administrators**, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ad63f-133">A4SWIFT の管理者グループがドメイン グループの場合は、次のように入力してください ***\<ドメイン名\>* \A4SWIFT 管理者**します。</span><span class="sxs-lookup"><span data-stu-id="ad63f-133">If the A4SWIFT Administrators group is a domain group, enter ***\<domain name\>*\A4SWIFT Administrators**.</span></span>  
  
3.  <span data-ttu-id="ad63f-134">手順 2. を繰り返します ***\<サーバー名\>* \A4SWIFT ユーザー**、または **\<*ドメイン名*\>\A4SWIFT ユーザー**場合、A4SWIFT ユーザーのグループは、ドメイン グループです。</span><span class="sxs-lookup"><span data-stu-id="ad63f-134">Repeat step 2 for ***\<server name\>*\A4SWIFT Users**, or **\<*domain name*\>\A4SWIFT Users** if the A4SWIFT Users group is a domain group.</span></span>  
  
4.  <span data-ttu-id="ad63f-135">グループまたはユーザーの名ペインで選択**A4SWIFT 管理者**します。</span><span class="sxs-lookup"><span data-stu-id="ad63f-135">In the Group or user names pane, select **A4SWIFT Administrators**.</span></span> <span data-ttu-id="ad63f-136">アクセス許可 ウィンドウで、次のように選択します。**許可**の**フルコントロール**します。</span><span class="sxs-lookup"><span data-stu-id="ad63f-136">In the Permissions pane, select **Allow** for **Full Control**.</span></span>  
  
5.  <span data-ttu-id="ad63f-137">グループまたはユーザーの名ペインで選択**A4SWIFT ユーザー**します。</span><span class="sxs-lookup"><span data-stu-id="ad63f-137">In the Group or user names pane, select **A4SWIFT Users**.</span></span> <span data-ttu-id="ad63f-138">アクセス許可 ウィンドウで、次のようにクリックします。**許可**の**読み取りと実行**、**フォルダー内容の一覧表示**、および**読み取り**します。</span><span class="sxs-lookup"><span data-stu-id="ad63f-138">In the Permissions pane, click **Allow** for **Read & Execute**, **List Folder Contents**, and **Read**.</span></span>  
  
6.  <span data-ttu-id="ad63f-139">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad63f-139">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad63f-140">参照</span><span class="sxs-lookup"><span data-stu-id="ad63f-140">See Also</span></span>  
 [<span data-ttu-id="ad63f-141">トラブルシューティング: 問題と解決策</span><span class="sxs-lookup"><span data-stu-id="ad63f-141">Troubleshooting: Issues and Resolutions</span></span>](../../adapters-and-accelerators/accelerator-swift/troubleshooting-issues-and-resolutions1.md)