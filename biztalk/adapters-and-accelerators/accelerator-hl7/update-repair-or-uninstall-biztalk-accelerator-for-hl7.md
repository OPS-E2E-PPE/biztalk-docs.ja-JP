---
title: 更新、修復、または for HL7 の BizTalk アクセラレータのアンインストール |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e2fc84d2-1262-4a6e-ae9c-488a00ab4099
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d9ab8aa171c814ed353e289911c31e8c08fcb11
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65286415"
---
# <a name="update-repair-or-uninstall-biztalk-accelerator-for-hl7"></a><span data-ttu-id="f1aed-102">更新、修復、または for HL7 の BizTalk アクセラレータのアンインストール</span><span class="sxs-lookup"><span data-stu-id="f1aed-102">Update, repair, or uninstall BizTalk Accelerator for HL7</span></span>

<span data-ttu-id="f1aed-103">変更、修復、アンインストール、[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="f1aed-103">Change, repair or uninstall the [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)].</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f1aed-104">アンインストールすることを確認する[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]アンインストールする前に[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="f1aed-104">Be sure to uninstall [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] before uninstalling [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] <span data-ttu-id="f1aed-105">場合はアンインストールできません[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]はインストールされません。</span><span class="sxs-lookup"><span data-stu-id="f1aed-105">cannot be uninstalled if [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] is no longer installed.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="f1aed-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="f1aed-106">Prerequisites</span></span>
* <span data-ttu-id="f1aed-107">メンバーであるアカウントを使用してサインイン、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理者グループ。</span><span class="sxs-lookup"><span data-stu-id="f1aed-107">Sign in using an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  

* <span data-ttu-id="f1aed-108">このユーザー アカウントを Administrators グループのメンバーがあります、 [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] BizTalk Accelerator for HL7 のデータを格納します。</span><span class="sxs-lookup"><span data-stu-id="f1aed-108">This user account must also be a member of the Administrators group on the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] that stores the BizTalk Accelerator for HL7 data.</span></span>  
    
## <a name="update-an-existing-installation"></a><span data-ttu-id="f1aed-109">更新プログラムの既存のインストール</span><span class="sxs-lookup"><span data-stu-id="f1aed-109">Update an existing installation</span></span>

> [!NOTE]
>  <span data-ttu-id="f1aed-110">インストールを変更するときに[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]、エンド ツー エンドのチュートリアルは自動的に実行されません。</span><span class="sxs-lookup"><span data-stu-id="f1aed-110">When you modify your installation of [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)], the End-to-End Tutorial does not automatically run.</span></span> 
> 
> <span data-ttu-id="f1aed-111">チュートリアルを実行し、変更後のインストールが正しく実行されることを確認します実行から手動でチュートリアル、 ***\<ドライブ\>*** **\Program Files\Microsoft BizTalk \< 。バージョン\>HL7\SDK\End ツー エンドのチュートリアルのアクセラレータ**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="f1aed-111">To run the tutorial and verify that the modified installation executed correctly, run the tutorial manually from the ***\<drive\>*** **\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial** folder.</span></span>
  
1. <span data-ttu-id="f1aed-112">実行、 [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] **setup.exe**に管理者として</span><span class="sxs-lookup"><span data-stu-id="f1aed-112">Run the [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] **setup.exe** as an administrator</span></span> 
  
2. <span data-ttu-id="f1aed-113">[ようこそ] ページで、次のように選択します。**次**します。</span><span class="sxs-lookup"><span data-stu-id="f1aed-113">On the welcome page, select **Next**.</span></span>  
  
3. <span data-ttu-id="f1aed-114">**プログラムのメンテナンス**を選択します**変更**、し、**次**します。</span><span class="sxs-lookup"><span data-stu-id="f1aed-114">In **Program Maintenance**, select **Modify**, and then select **Next**.</span></span>  
  
4. <span data-ttu-id="f1aed-115">**カスタム セットアップ**をインストールする機能を選択して、チェック ボックスをオフの機能はありませんしを選択し、**次**します。</span><span class="sxs-lookup"><span data-stu-id="f1aed-115">In **Custom Setup**, select the features that you want to install, clear the features you don't want, and then select **Next**.</span></span>  
  
5. <span data-ttu-id="f1aed-116">概要では、次のように選択します。**次**します。</span><span class="sxs-lookup"><span data-stu-id="f1aed-116">In the summary, select **Next**.</span></span>  
  
6. <span data-ttu-id="f1aed-117">**[インストール]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f1aed-117">Select **Install**.</span></span>  
  
7. <span data-ttu-id="f1aed-118">完了すると、選択**完了**します。</span><span class="sxs-lookup"><span data-stu-id="f1aed-118">When complete, select **Finish**.</span></span>  

## <a name="repair-an-existing-installation"></a><span data-ttu-id="f1aed-119">既存のインストールを修復します。</span><span class="sxs-lookup"><span data-stu-id="f1aed-119">Repair an existing installation</span></span>
<span data-ttu-id="f1aed-120">[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]ウィザードが見つからないか壊れているファイル、ショートカット、またはレジストリ エントリを修正して、インストールを修復します。</span><span class="sxs-lookup"><span data-stu-id="f1aed-120">The [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] Wizard repairs an installation by fixing missing or corrupt files, shortcuts, or registry entries.</span></span>  
  
1. <span data-ttu-id="f1aed-121">実行、 [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] **setup.exe**管理者として。</span><span class="sxs-lookup"><span data-stu-id="f1aed-121">Run the [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] **setup.exe** as administrator.</span></span>  
  
2. <span data-ttu-id="f1aed-122">[ようこそ] ページで、次のように選択します。**次**します。</span><span class="sxs-lookup"><span data-stu-id="f1aed-122">On the welcome page, select **Next**.</span></span>  
  
3. <span data-ttu-id="f1aed-123">**プログラムのメンテナンス**を選択します**修復**、し、**次**します。</span><span class="sxs-lookup"><span data-stu-id="f1aed-123">In **Program Maintenance**, select **Repair**, and then select **Next**.</span></span>  
  
4. <span data-ttu-id="f1aed-124">**サービス アカウントのログ記録**、ユーザー アカウントを再入力し、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="f1aed-124">In **Logging Service Account**, re-enter the user account, and then select **OK**.</span></span>  
  
5. <span data-ttu-id="f1aed-125">メッセージが表示されたら**アカウント名が許可されているログオン適切なサービスとして**を選択し、 **OK**を続行します。</span><span class="sxs-lookup"><span data-stu-id="f1aed-125">If prompted **The account name has been granted logon as a service right**, then select **OK** to continue.</span></span>  
  
6. <span data-ttu-id="f1aed-126">修復する準備が完了したら、選択**インストール**します。</span><span class="sxs-lookup"><span data-stu-id="f1aed-126">When ready to repair, select **Install**.</span></span>  
  
7. <span data-ttu-id="f1aed-127">完了したら、選択**完了**します。</span><span class="sxs-lookup"><span data-stu-id="f1aed-127">When completed, select **Finish**.</span></span> 

  
## <a name="uninstall-btahl7"></a><span data-ttu-id="f1aed-128">BTAHL7 をアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="f1aed-128">Uninstall BTAHL7</span></span>  

> [!IMPORTANT]
>  <span data-ttu-id="f1aed-129">ある場合、受信場所または送信ポートの MLLP トランスポートの種類を使用して、BTAHL7 セットアップの BTAHL7 のアンインストール時に MLLP アダプターは削除されません。</span><span class="sxs-lookup"><span data-stu-id="f1aed-129">If there is a receive location or send port using the MLLP transport type, the BTAHL7 setup does not remove the MLLP adapter during the uninstall of BTAHL7.</span></span> <span data-ttu-id="f1aed-130">アンインストールする前に削除のすべての受信場所または送信ポートの MLLP トランスポートを使用しています。</span><span class="sxs-lookup"><span data-stu-id="f1aed-130">Before you uninstall, remove all receive locations or send ports using the MLLP transport.</span></span> <span data-ttu-id="f1aed-131">または、別の型 MLLP からトランスポートの種類を変更します。</span><span class="sxs-lookup"><span data-stu-id="f1aed-131">Or, change the transport type from MLLP to another type.</span></span> <span data-ttu-id="f1aed-132">次に、アンインストール、MLLP アダプターが削除されます。</span><span class="sxs-lookup"><span data-stu-id="f1aed-132">Then, the uninstall will remove the MLLP adapter.</span></span>  
      
1. <span data-ttu-id="f1aed-133">開いている**プログラムと機能**します。</span><span class="sxs-lookup"><span data-stu-id="f1aed-133">Open **Programs and Features**.</span></span>  
  
2. <span data-ttu-id="f1aed-134">選択[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]、し、**アンインストール**します。</span><span class="sxs-lookup"><span data-stu-id="f1aed-134">Select [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)], and then select **Uninstall**.</span></span>  
  
3. <span data-ttu-id="f1aed-135">選択**はい**ことを確認するように求められる場合。</span><span class="sxs-lookup"><span data-stu-id="f1aed-135">Select **Yes** if asked to confirm.</span></span> 
  
4. <span data-ttu-id="f1aed-136">完了したら、選択**完了**します。</span><span class="sxs-lookup"><span data-stu-id="f1aed-136">When completed, select **Finish**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="f1aed-137">BTAHL7 が自動的にアンインストールされない[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アイテムとアセンブリです。</span><span class="sxs-lookup"><span data-stu-id="f1aed-137">BTAHL7 does not automatically uninstall [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] artifacts and assemblies.</span></span>  
  

  
## <a name="troubleshooting-installation-issues"></a><span data-ttu-id="f1aed-138">インストールに関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="f1aed-138">Troubleshooting Installation Issues</span></span>  
 <span data-ttu-id="f1aed-139">かどうか、サーバーでは、ユーザーがいるかどうかを検証できない、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理者は、BTAHL7 をアンインストールする、次のエラーを返します。</span><span class="sxs-lookup"><span data-stu-id="f1aed-139">If the server is unable to validate whether the user is a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrator, uninstalling BTAHL7 returns the following error:</span></span> 
 
 `Fatal error during uninstallation`  
  
<span data-ttu-id="f1aed-140">アンインストールを続行するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f1aed-140">To continue with uninstallation, do the following:</span></span>  
  
1. <span data-ttu-id="f1aed-141">ローカル管理者としてサーバーにサインインします。</span><span class="sxs-lookup"><span data-stu-id="f1aed-141">Sign in to the server as a local administrator.</span></span>  
  
2. <span data-ttu-id="f1aed-142">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] をアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="f1aed-142">Uninstall [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
3. <span data-ttu-id="f1aed-143">[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] をアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="f1aed-143">Uninstall [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1aed-144">参照</span><span class="sxs-lookup"><span data-stu-id="f1aed-144">See Also</span></span>  
[<span data-ttu-id="f1aed-145">Microsoft BizTalk Accelerator for HL7 のインストールまたはアップグレード</span><span class="sxs-lookup"><span data-stu-id="f1aed-145">Install or upgrade Microsoft BizTalk Accelerator for HL7</span></span>](../../adapters-and-accelerators/accelerator-hl7/install-or-upgrade-microsoft-biztalk-accelerator-for-hl7.md)