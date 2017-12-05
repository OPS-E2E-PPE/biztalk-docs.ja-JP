---
title: "BizTalk Accelerator 用 HL7 にアップグレード |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 91b6747f-e560-4cf8-99b5-af0d150599bf
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d4df85c965943f2f2c916fef6b558f98caf2175f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="upgrade-biztalk-accelerator-for-hl7"></a><span data-ttu-id="5d251-102">アップグレードの BizTalk Accelerator 用 HL7</span><span class="sxs-lookup"><span data-stu-id="5d251-102">Upgrade BizTalk Accelerator for HL7</span></span>
<span data-ttu-id="5d251-103">概要については、[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]プロセスをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="5d251-103">Overview of the [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] upgrade process.</span></span> 
  
<a name="BKMK_BeforeUpgrade"></a>   
## <a name="before-you-upgrade"></a><span data-ttu-id="5d251-104">アップグレードする前に</span><span class="sxs-lookup"><span data-stu-id="5d251-104">Before you upgrade</span></span>  
  
-   <span data-ttu-id="5d251-105">アップグレードを実行しているユーザーは、BizTalk 管理者グループのメンバーにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d251-105">The user running the upgrade must be a member of the BizTalk Administrators group.</span></span>  
  
-   <span data-ttu-id="5d251-106">アップグレードを実行するときに、SQL Server (MSSQLSERVER) サービスを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d251-106">The SQL Server (MSSQLSERVER) service must be running when you perform an upgrade.</span></span>  
  
-   <span data-ttu-id="5d251-107">サイレント インストールのアップグレードは実行されません。</span><span class="sxs-lookup"><span data-stu-id="5d251-107">Do not run a silent installation to upgrade.</span></span>  
  
-   <span data-ttu-id="5d251-108">セットアップ プログラムでは、既存の移行アップグレードすると、[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]構成については、新しいバージョンにします。</span><span class="sxs-lookup"><span data-stu-id="5d251-108">When you upgrade, the setup program migrates the existing [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] configuration information to the newer version.</span></span>  
  
-   <span data-ttu-id="5d251-109">アップグレードすると、レジストリ キーとデータベースに自動的にバックアップされます。</span><span class="sxs-lookup"><span data-stu-id="5d251-109">When you upgrade, the registry keys and databases are automatically backed up.</span></span>  
  
-   <span data-ttu-id="5d251-110">内のファイル、 *\<ドライブ\>*: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator for HL7 フォルダーが更新されます。</span><span class="sxs-lookup"><span data-stu-id="5d251-110">The files in the *\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7 folder are updated.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5d251-111">アップグレードがアップグレードされたファイル用の新しいフォルダーを作成できません。 また、既存のフォルダーの名前は変更。</span><span class="sxs-lookup"><span data-stu-id="5d251-111">The upgrade does not create a new folder for the upgraded files, nor does it change the name of the existing folder.</span></span>  
  
<a name="BKMK_UpgradePaths"></a>   
## <a name="supported-upgrade-paths"></a><span data-ttu-id="5d251-112">サポートされるアップグレード パス</span><span class="sxs-lookup"><span data-stu-id="5d251-112">Supported Upgrade Paths</span></span>  
 <span data-ttu-id="5d251-113">次の表に、サポートされている一覧[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]バージョンをアップグレードすることができます。</span><span class="sxs-lookup"><span data-stu-id="5d251-113">The following table lists the supported [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] versions that can be upgraded.</span></span> <span data-ttu-id="5d251-114">"Yes"手段、[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]バージョンをアップグレードすることができます。</span><span class="sxs-lookup"><span data-stu-id="5d251-114">“Yes” means the [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] version can be upgraded.</span></span> <span data-ttu-id="5d251-115">"No"の意味、[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]バージョンをアップグレードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="5d251-115">“No” means the [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] version cannot be upgraded.</span></span> <span data-ttu-id="5d251-116">場合、[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]バージョンが記載されていない、そのバージョンをアップグレードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="5d251-116">If the [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] version is not listed, that version cannot be upgraded.</span></span>  

||[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]|[!INCLUDE[bts2013r2](../../includes/bts2013r2-md.md)]|<span data-ttu-id="5d251-117">BizTalk Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d251-117">BizTalk Server 2013</span></span>|
|---|---|---|---|  
|[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="5d251-118"> 2013</span><span class="sxs-lookup"><span data-stu-id="5d251-118"> 2013</span></span>|<span data-ttu-id="5d251-119">可</span><span class="sxs-lookup"><span data-stu-id="5d251-119">Yes</span></span>|<span data-ttu-id="5d251-120">可</span><span class="sxs-lookup"><span data-stu-id="5d251-120">Yes</span></span>|<span data-ttu-id="5d251-121">不可</span><span class="sxs-lookup"><span data-stu-id="5d251-121">No</span></span>|  
|[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="5d251-122"> 2010</span><span class="sxs-lookup"><span data-stu-id="5d251-122"> 2010</span></span>|<span data-ttu-id="5d251-123">不可</span><span class="sxs-lookup"><span data-stu-id="5d251-123">No</span></span>|<span data-ttu-id="5d251-124">はい</span><span class="sxs-lookup"><span data-stu-id="5d251-124">Yes</span></span>|<span data-ttu-id="5d251-125">可</span><span class="sxs-lookup"><span data-stu-id="5d251-125">Yes</span></span>|  

<a name="BKMK_UpgradeSteps"></a>   
## <a name="upgrade-steps"></a><span data-ttu-id="5d251-126">アップグレード手順</span><span class="sxs-lookup"><span data-stu-id="5d251-126">Upgrade Steps</span></span>  
  
1.  <span data-ttu-id="5d251-127">アップグレード、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="5d251-127">Upgrade the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>   
  
2.  <span data-ttu-id="5d251-128">バックアップを[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]データベースと、HL7 メッセージ スキーマ。</span><span class="sxs-lookup"><span data-stu-id="5d251-128">Back up the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] databases and your HL7 message schemas.</span></span>  
  
3.  <span data-ttu-id="5d251-129">下位にあるファイルをバックアップ、  ***\<ドライブ\>*: \Program Files\Microsoft BizTalk Accelerator 用 HL7**を変更しているフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="5d251-129">Back up any files under the ***\<drive\>*:\Program Files\Microsoft BizTalk Accelerator for HL7** folder that you have changed.</span></span> <span data-ttu-id="5d251-130">たとえば、SDK 内のファイルをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="5d251-130">For example, back up files in the SDK.</span></span>  
  
4.  <span data-ttu-id="5d251-131">バージョンに適切な更新プログラムをインストール[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="5d251-131">Install the appropriate update for your version of [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]:</span></span>  
  
    -   <span data-ttu-id="5d251-132">BTAHL7 2010 からアップグレードする場合は、インストール**HL72010Patch.msp**です。</span><span class="sxs-lookup"><span data-stu-id="5d251-132">If upgrading from BTAHL7 2010, install **HL72010Patch.msp**.</span></span>  
  
    -   <span data-ttu-id="5d251-133">BTAHL7 2013 からアップグレードする場合は、インストール**HL72013Patch.msp**です。</span><span class="sxs-lookup"><span data-stu-id="5d251-133">If upgrading from BTAHL7 2013, install **HL72013Patch.msp**.</span></span>  
    
  
5.  <span data-ttu-id="5d251-134">[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] のセットアップを実行します。</span><span class="sxs-lookup"><span data-stu-id="5d251-134">Run the [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] setup.</span></span> <span data-ttu-id="5d251-135">参照してください[用 HL7 BizTalk アクセラレータをインストール](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md)です。</span><span class="sxs-lookup"><span data-stu-id="5d251-135">See [Install BizTalk Accelerator for HL7](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md).</span></span>  
  
6.  <span data-ttu-id="5d251-136">新しい BTAHL7V2 展開*x*共通プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="5d251-136">Deploy the new BTAHL7V2*x*Common project.</span></span>  
  
7.  <span data-ttu-id="5d251-137">その他のすべてのアセンブリを再展開します。</span><span class="sxs-lookup"><span data-stu-id="5d251-137">Redeploy all other assemblies.</span></span>  
  
8.  <span data-ttu-id="5d251-138">[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] アセンブリを参照するプロジェクトまたはアセンブリを再構築します。</span><span class="sxs-lookup"><span data-stu-id="5d251-138">Rebuild any projects or assemblies that have a reference to one or more of the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] assemblies.</span></span> <span data-ttu-id="5d251-139">使用して**BTSTask.exe**で\<*ドライブ*\>: \Program Files\Microsoft BizTalk Server\<バージョン\>を手動でこれらのプロジェクトを再展開します。</span><span class="sxs-lookup"><span data-stu-id="5d251-139">Using **BTSTask.exe** in \<*drive*\>:\Program Files\Microsoft BizTalk Server \<version\>, manually redeploy these projects.</span></span>  
  
9. <span data-ttu-id="5d251-140">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] サービスを再開します。</span><span class="sxs-lookup"><span data-stu-id="5d251-140">Restart the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] service.</span></span>  
  
<a name="BKMK_UpgradeMulti"></a>   
## <a name="upgrading-in-a-multi-server-environment"></a><span data-ttu-id="5d251-141">マルチ サーバー環境でのアップグレード</span><span class="sxs-lookup"><span data-stu-id="5d251-141">Upgrading in a Multi-server Environment</span></span>  
 <span data-ttu-id="5d251-142">マルチ サーバー[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]環境、アップグレード[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]秒、およびアップグレードしてから、[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]すべてのサーバーでします。</span><span class="sxs-lookup"><span data-stu-id="5d251-142">In a multi-server [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] environment, upgrade all [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]s, and then upgrade the [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] on all servers.</span></span> <span data-ttu-id="5d251-143">次の順序でサーバーを移行します。</span><span class="sxs-lookup"><span data-stu-id="5d251-143">Migrate your servers in the following order:</span></span>  
  
-   <span data-ttu-id="5d251-144">BizTalk グループをホストするサーバー</span><span class="sxs-lookup"><span data-stu-id="5d251-144">The server hosting the BizTalk Group</span></span>  
  
-   <span data-ttu-id="5d251-145">各処理ノード</span><span class="sxs-lookup"><span data-stu-id="5d251-145">Each processing node</span></span>  
  
-   <span data-ttu-id="5d251-146">BAM ポータル サーバー</span><span class="sxs-lookup"><span data-stu-id="5d251-146">The BAM portal server</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d251-147">参照</span><span class="sxs-lookup"><span data-stu-id="5d251-147">See Also</span></span>  
 [<span data-ttu-id="5d251-148">BizTalk Accelerator for HL7 のインストール</span><span class="sxs-lookup"><span data-stu-id="5d251-148">Install BizTalk Accelerator for HL7</span></span>](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md)