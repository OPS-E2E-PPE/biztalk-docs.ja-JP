---
title: SSO 管理者を指定し、関連管理者アカウントをどのように |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- administrator accounts, SSO
- enabling, SSO
- SSO, enabling
- disabling, SSO
- SSO, disabling
- managing [SSO], configuring administrator accounts
- managing [SSO], enabling
- managing [SSO], disabling
- SSO, administrator accounts
ms.assetid: 6c300e09-b781-45de-b2da-b1083164a1c0
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c96e2d99bd6071098a65b3635bb466de44a455d
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-specify-sso-administrators-and-affiliate-administrators-accounts"></a><span data-ttu-id="91724-102">SSO 管理者を指定し、関連管理者アカウント方法</span><span class="sxs-lookup"><span data-stu-id="91724-102">How to Specify SSO Administrators and Affiliate Administrators Accounts</span></span>
<span data-ttu-id="91724-103">エンタープライズ シングル サインオン (SSO) 管理者アカウントと関連管理者アカウントは、ホスト グループまたは個別のアカウントにすることができます。</span><span class="sxs-lookup"><span data-stu-id="91724-103">The Enterprise Single Sign-On (SSO) Administrators and Affiliate Administrators accounts can be host group or individual accounts.</span></span> <span data-ttu-id="91724-104">これらのアカウントは、SSO システムを構成する前に作成しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="91724-104">You must create these accounts before you configure the SSO system.</span></span>  
  
 <span data-ttu-id="91724-105">ドメイン アカウントを使用する場合する必要があります、SSO 管理者および SSO 関連管理者アカウント ドメインとしてグローバル セキュリティ グループを作成ドメイン コント ローラーです。</span><span class="sxs-lookup"><span data-stu-id="91724-105">When using domain accounts, you must create the SSO Administrators and SSO Affiliate Administrators accounts as a domain global security groups in the domain controller.</span></span> <span data-ttu-id="91724-106">これらのアカウントは、ドメイン管理者が作成します。</span><span class="sxs-lookup"><span data-stu-id="91724-106">The domain administrator must create these accounts.</span></span>  
  
 <span data-ttu-id="91724-107">シングル サインオン管理者アカウントと関連管理者アカウントは、SSO データベースで指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="91724-107">You must specify the Single Sign-On Administrators and Affiliate Administrators accounts in the SSO database.</span></span> <span data-ttu-id="91724-108">SSO データベースを更新して SSO 管理者グループを指定する場合、更新する前にシングル サインオン システムを無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="91724-108">You must disable the Single Sign-On system before you update the SSO database with the SSO Administrators group.</span></span>  
  
 <span data-ttu-id="91724-109">次の XML コードは、SSO データベースを更新する場合のサンプル XML です。</span><span class="sxs-lookup"><span data-stu-id="91724-109">The following XML code shows a sample XML for updating the SSO database:</span></span>  
  
```  
<sso>  
<globalInfo>  
<ssoAdminAccount>Domain\Accountname</ssoAdminAccount>  
<ssoAffiliateAdminAccount>Domain\Accountname</ssoAffiliateAdminAccount>  
</globalInfo>  
</sso>  
```  
  
> [!NOTE]
>  <span data-ttu-id="91724-110">構成ウィザードでは、SSO データベースの SSO 管理者グループと SSO 関連管理者グループが自動的に指定されます。</span><span class="sxs-lookup"><span data-stu-id="91724-110">The Configuration Wizard automatically specifies the SSO administrator and SSO affiliate administrator groups in the SSO database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="91724-111">SSO が構成されない場合、ユーザーがドメイン ローカル アカウントが、混在モード ドメインで使用されているかどうかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="91724-111">If SSO does not configure, users should check whether Domain Local Accounts are being used in a mixed-mode domain.</span></span>  
  
### <a name="to-disable-the-enterprise-single-sign-on-system-using-the-mmc-snap-in"></a><span data-ttu-id="91724-112">MMC スナップインでエンタープライズ シングル サインオン システムを無効にするには</span><span class="sxs-lookup"><span data-stu-id="91724-112">To disable the Enterprise Single Sign-On system using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="91724-113">**開始**  メニューのをクリックして **すべてのプログラム**, 、 をクリックして **Microsoft エンタープライズ シングル サインオン**, 、 をクリックし、 **SSO 管理**します。</span><span class="sxs-lookup"><span data-stu-id="91724-113">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="91724-114">ENTSSO MMC スナップインのスコープ ペインで、展開、 **エンタープライズ シングル サインオン** ノードです。</span><span class="sxs-lookup"><span data-stu-id="91724-114">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="91724-115">右クリック **システム**, 、クリックして **を無効にする**です。</span><span class="sxs-lookup"><span data-stu-id="91724-115">Right-click **System**, and then click **Disable**.</span></span>  
  
### <a name="to-disable-the-enterprise-single-sign-on-system-using-the-command-line"></a><span data-ttu-id="91724-116">コマンド ラインでエンタープライズ シングル サインオン システムを無効にするには</span><span class="sxs-lookup"><span data-stu-id="91724-116">To disable the Enterprise Single Sign-On system using the command line</span></span>  
  
1.  <span data-ttu-id="91724-117">**開始**  メニューのをクリックして **実行**, 、し、入力 **cmd**します。</span><span class="sxs-lookup"><span data-stu-id="91724-117">On the **Start** menu, click **run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="91724-118">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="91724-118">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="91724-119">既定のインストール ディレクトリは\<*ドライブ*\>: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="91724-119">The default installation directory is \<*drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="91724-120">型 **ssomanage** –**disablesso**します。</span><span class="sxs-lookup"><span data-stu-id="91724-120">Type **ssomanage** –**disablesso**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="91724-121">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="91724-121">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-update-the-sso-database-using-the-mmc-snap-in"></a><span data-ttu-id="91724-122">MMC スナップインを使用して SSO データベースを更新するには</span><span class="sxs-lookup"><span data-stu-id="91724-122">To update the SSO database using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="91724-123">**開始**  メニューのをクリックして **すべてのプログラム**, 、**Microsoft エンタープライズ シングル サインオン**, 、し **SSO 管理**します。</span><span class="sxs-lookup"><span data-stu-id="91724-123">On the **Start** menu, click **All Programs**, **Microsoft Enterprise Single Sign-On**, and then **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="91724-124">ENTSSO MMC スナップインのスコープ ペインで、展開、 **エンタープライズ シングル サインオン** ノードです。</span><span class="sxs-lookup"><span data-stu-id="91724-124">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="91724-125">右クリック **システム**, 、クリックして **更新**します。</span><span class="sxs-lookup"><span data-stu-id="91724-125">Right-click **System**, and then click **Update**.</span></span>  
  
### <a name="to-update-the-sso-database-using-the-command-line"></a><span data-ttu-id="91724-126">コマンド ラインを使用して SSO データベースを更新するには</span><span class="sxs-lookup"><span data-stu-id="91724-126">To update the SSO database using the command line</span></span>  
  
1.  <span data-ttu-id="91724-127">**開始**  メニューのをクリックして **実行**, 、し、入力 **cmd**します。</span><span class="sxs-lookup"><span data-stu-id="91724-127">On the **Start** menu, click **run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="91724-128">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="91724-128">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="91724-129">既定のインストール ディレクトリは*\<ドライブ\>*: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="91724-129">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="91724-130">型 * * ssomanage – updatedb *\<更新ファイル\>* * *、どこで*\<更新ファイル\>* XML ファイルの名前とパスは、します。</span><span class="sxs-lookup"><span data-stu-id="91724-130">Type **ssomanage –updatedb *\<update file\>***, where *\<update file\>* is the path and name of the XML file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="91724-131">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="91724-131">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-enable-the-enterprise-single-sign-on-system-using-the-mmc-snap-in"></a><span data-ttu-id="91724-132">MMC スナップインでエンタープライズ シングル サインオン システムを有効にするには</span><span class="sxs-lookup"><span data-stu-id="91724-132">To enable the Enterprise Single Sign-On system using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="91724-133">**開始**  メニューのをクリックして **すべてのプログラム**, 、**Microsoft エンタープライズ シングル サインオン**, 、し **SSO 管理**します。</span><span class="sxs-lookup"><span data-stu-id="91724-133">On the **Start** menu, click **All Programs**, **Microsoft Enterprise Single Sign-On**, and then **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="91724-134">ENTSSO MMC スナップインのスコープ ペインで、展開、 **エンタープライズ シングル サインオン** ノードです。</span><span class="sxs-lookup"><span data-stu-id="91724-134">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="91724-135">右クリック **システム**, 、クリックして **を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="91724-135">Right-click **System**, and then click **Enable**.</span></span>  
  
### <a name="to-enable-the-enterprise-single-sign-on-system-using-the-command-line"></a><span data-ttu-id="91724-136">コマンド ラインでエンタープライズ シングル サインオン システムを有効にするには</span><span class="sxs-lookup"><span data-stu-id="91724-136">To enable the Enterprise Single Sign-On system using the command line</span></span>  
  
1.  <span data-ttu-id="91724-137">**開始**  メニューのをクリックして **実行**, 、し、入力 **cmd**します。</span><span class="sxs-lookup"><span data-stu-id="91724-137">On the **Start** menu, click **run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="91724-138">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="91724-138">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="91724-139">既定のインストール ディレクトリは*\<ドライブ\>*: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="91724-139">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="91724-140">型 **ssomanage – enablesso**します。</span><span class="sxs-lookup"><span data-stu-id="91724-140">Type **ssomanage –enablesso**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="91724-141">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="91724-141">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91724-142">参照</span><span class="sxs-lookup"><span data-stu-id="91724-142">See Also</span></span>  
 [<span data-ttu-id="91724-143">SSO ユーザー グループ</span><span class="sxs-lookup"><span data-stu-id="91724-143">SSO User Groups</span></span>](../core/sso-user-groups.md)