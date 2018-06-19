---
title: SSO データベース情報を表示する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [SSO], viewing SSO database
- SSO database, viewing
- viewing, SSO database
ms.assetid: 0ebadd2e-6ea5-460c-b0a8-f48589e6bf1c
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e834874cb87da598db0bc92e516b58dfe2da9069
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969328"
---
# <a name="how-to-display-the-sso-database-information"></a><span data-ttu-id="66ab5-102">SSO データベース情報を表示する方法</span><span class="sxs-lookup"><span data-stu-id="66ab5-102">How to Display the SSO Database Information</span></span>
<span data-ttu-id="66ab5-103">SSO データベース情報は、MMC スナップインまたはコマンド ライン (ssomanage) ユーティリティを使用して表示できます。</span><span class="sxs-lookup"><span data-stu-id="66ab5-103">You can view SSO database information by using the MMC Snap-In or the command line (ssomanage) utility.</span></span>  
  
### <a name="to-display-the-sso-database-information-using-the-mmc-snap-in"></a><span data-ttu-id="66ab5-104">MMC スナップインを使用して SSO データベース情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="66ab5-104">To display the SSO database information using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="66ab5-105">**開始** メニューのをクリックして**すべてのプログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、クリックして**SSO 管理**です。</span><span class="sxs-lookup"><span data-stu-id="66ab5-105">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="66ab5-106">ENTSSO MMC スナップインの [スコープ] ウィンドウで、展開、**エンタープライズ シングル サインオン**ノード。</span><span class="sxs-lookup"><span data-stu-id="66ab5-106">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="66ab5-107">右クリック**システム**、クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="66ab5-107">Right-click **System**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="66ab5-108">タブをクリックし、**システム プロパティ**ダイアログ ボックスに SSO データベース情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="66ab5-108">Click the tabs on the  **System Properties** dialog box to view SSO database information.</span></span>  
  
### <a name="to-display-the-sso-database-information-using-the-command-line"></a><span data-ttu-id="66ab5-109">コマンド ラインを使用して SSO データベース情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="66ab5-109">To display the SSO database information using the command line</span></span>  
  
1.  <span data-ttu-id="66ab5-110">**開始** メニューのをクリックして**実行**、し、入力**cmd**です。</span><span class="sxs-lookup"><span data-stu-id="66ab5-110">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="66ab5-111">コマンド ライン プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="66ab5-111">At the command line prompt, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="66ab5-112">既定のインストール ディレクトリは**\<ドライブ\>**: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="66ab5-112">The default installation directory is **\<drive\>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="66ab5-113">型**ssomanage – displaydb**です。</span><span class="sxs-lookup"><span data-stu-id="66ab5-113">Type **ssomanage –displaydb**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="66ab5-114">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="66ab5-114">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-display-the-sso-database-the-sso-server-is-connected-to-using-the-command-line"></a><span data-ttu-id="66ab5-115">コマンド ラインを使用して SSO サーバーの接続先 SSO データベースを表示するには</span><span class="sxs-lookup"><span data-stu-id="66ab5-115">To display the SSO database the SSO Server is connected to using the command line</span></span>  
  
1.  <span data-ttu-id="66ab5-116">**開始** メニューのをクリックして**実行**、し、入力**cmd**です。</span><span class="sxs-lookup"><span data-stu-id="66ab5-116">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="66ab5-117">コマンド ライン プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="66ab5-117">At the command line prompt, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="66ab5-118">既定のインストール ディレクトリは**\<ドライブ\>**: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="66ab5-118">The default installation directory is **\<drive\>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="66ab5-119">型**ssomanage – showdb**です。</span><span class="sxs-lookup"><span data-stu-id="66ab5-119">Type **ssomanage –showdb**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="66ab5-120">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="66ab5-120">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
 <span data-ttu-id="66ab5-121">次の表では、上記の手順で返される値について説明します。</span><span class="sxs-lookup"><span data-stu-id="66ab5-121">The following table describes the values displayed by these procedures.</span></span>  
  
|<span data-ttu-id="66ab5-122">プロパティ</span><span class="sxs-lookup"><span data-stu-id="66ab5-122">Property</span></span>|<span data-ttu-id="66ab5-123">値</span><span class="sxs-lookup"><span data-stu-id="66ab5-123">Value</span></span>|  
|--------------|-----------|  
|<span data-ttu-id="66ab5-124">SQL Server</span><span class="sxs-lookup"><span data-stu-id="66ab5-124">SQL Server</span></span>|<span data-ttu-id="66ab5-125">**\<SQL Server 名\>**</span><span class="sxs-lookup"><span data-stu-id="66ab5-125">**\<SQL Server name\>**</span></span>|  
|<span data-ttu-id="66ab5-126">シングル サインオン データベース</span><span class="sxs-lookup"><span data-stu-id="66ab5-126">Single Sign-On database</span></span>|<span data-ttu-id="66ab5-127">**\<SQL Server データベース名\>**</span><span class="sxs-lookup"><span data-stu-id="66ab5-127">**\<SQL Server database name\>**</span></span>|  
|<span data-ttu-id="66ab5-128">シングル サインオン シークレット サーバー名</span><span class="sxs-lookup"><span data-stu-id="66ab5-128">Single Sign-On Secret Server name</span></span>|<span data-ttu-id="66ab5-129">**\<シングル サインオン サーバーの名前\>**</span><span class="sxs-lookup"><span data-stu-id="66ab5-129">**\<Single Sign-On Server name\>**</span></span>|  
|<span data-ttu-id="66ab5-130">シングル サインオン管理者アカウント</span><span class="sxs-lookup"><span data-stu-id="66ab5-130">Single Sign-On Administrators account</span></span>|<span data-ttu-id="66ab5-131">ドメイン\アカウント名</span><span class="sxs-lookup"><span data-stu-id="66ab5-131">Domain\account name</span></span>|  
|<span data-ttu-id="66ab5-132">シングル サインオン関連管理者アカウント</span><span class="sxs-lookup"><span data-stu-id="66ab5-132">Single Sign-On Affiliate Administrators account</span></span>|<span data-ttu-id="66ab5-133">ドメイン\アカウント名</span><span class="sxs-lookup"><span data-stu-id="66ab5-133">Domain\account name</span></span>|  
|<span data-ttu-id="66ab5-134">削除したアプリケーションの監査テーブルのサイズ (監査エントリの数)</span><span class="sxs-lookup"><span data-stu-id="66ab5-134">Size of audit table for deleted applications (number of audit entries)</span></span>|<span data-ttu-id="66ab5-135">1,000 (既定値)</span><span class="sxs-lookup"><span data-stu-id="66ab5-135">1,000 (default)</span></span>|  
|<span data-ttu-id="66ab5-136">削除したユーザー マッピングの監査テーブルのサイズ (監査エントリの数)</span><span class="sxs-lookup"><span data-stu-id="66ab5-136">Size of audit table for deleted user mappings (number of audit entries)</span></span>|<span data-ttu-id="66ab5-137">1,000 (既定値)</span><span class="sxs-lookup"><span data-stu-id="66ab5-137">1,000 (default)</span></span>|  
|<span data-ttu-id="66ab5-138">外部資格情報参照の監査テーブルのサイズ (監査エントリの数)</span><span class="sxs-lookup"><span data-stu-id="66ab5-138">Size of audit table for external credential lookups (number of audit entries)</span></span>|<span data-ttu-id="66ab5-139">1,000 (既定値)</span><span class="sxs-lookup"><span data-stu-id="66ab5-139">1,000 (default)</span></span>|  
|<span data-ttu-id="66ab5-140">チケットのタイムアウト (分)</span><span class="sxs-lookup"><span data-stu-id="66ab5-140">Ticket timeout (in minutes)</span></span>|<span data-ttu-id="66ab5-141">2 (既定)</span><span class="sxs-lookup"><span data-stu-id="66ab5-141">2 (default)</span></span><br /><br /> <span data-ttu-id="66ab5-142">この値には、1 ～ 525,600 の整数値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="66ab5-142">This value can be an integer from1 through 525,600</span></span>|  
|<span data-ttu-id="66ab5-143">資格情報キャッシュ タイムアウト (分)</span><span class="sxs-lookup"><span data-stu-id="66ab5-143">Credential cache timeout (in minutes)</span></span>|<span data-ttu-id="66ab5-144">60 (既定値)</span><span class="sxs-lookup"><span data-stu-id="66ab5-144">60 (default)</span></span>|  
|<span data-ttu-id="66ab5-145">シングル サインオンの状態</span><span class="sxs-lookup"><span data-stu-id="66ab5-145">Single Sign-On Status</span></span>|<span data-ttu-id="66ab5-146">有効/無効</span><span class="sxs-lookup"><span data-stu-id="66ab5-146">Enabled/disabled</span></span>|  
|<span data-ttu-id="66ab5-147">[許可されたチケット]</span><span class="sxs-lookup"><span data-stu-id="66ab5-147">Tickets allowed</span></span>|<span data-ttu-id="66ab5-148">Yes/no (既定値)</span><span class="sxs-lookup"><span data-stu-id="66ab5-148">Yes/no (default)</span></span>|  
|<span data-ttu-id="66ab5-149">[チケットの検証]</span><span class="sxs-lookup"><span data-stu-id="66ab5-149">Validate tickets</span></span>|<span data-ttu-id="66ab5-150">Yes (既定値)/no</span><span class="sxs-lookup"><span data-stu-id="66ab5-150">Yes (default)/no</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="66ab5-151">参照</span><span class="sxs-lookup"><span data-stu-id="66ab5-151">See Also</span></span>  
 <span data-ttu-id="66ab5-152">[SSO チケットを構成する方法](../core/how-to-configure-the-sso-tickets.md) </span><span class="sxs-lookup"><span data-stu-id="66ab5-152">[How to Configure the SSO Tickets](../core/how-to-configure-the-sso-tickets.md) </span></span>  
 [<span data-ttu-id="66ab5-153">SSO の使用</span><span class="sxs-lookup"><span data-stu-id="66ab5-153">Using SSO</span></span>](../core/using-sso.md)