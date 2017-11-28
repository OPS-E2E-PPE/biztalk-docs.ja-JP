---
title: "BAM ポータルの既知の問題 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e681e910-c664-479c-86f3-a6ae0ec97775
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0aa12d0f25a004f2e713f360e00c0f0c1192d304
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues-in-the-bam-portal"></a><span data-ttu-id="befaf-102">BAM ポータルでの既知の問題</span><span class="sxs-lookup"><span data-stu-id="befaf-102">Known Issues in the BAM Portal</span></span>
<span data-ttu-id="befaf-103">このトピックでは、BAM ポータルの使用中に発生する可能性がある問題の特定と解決に役立つ情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="befaf-103">This topic contains information to help you identify and resolve issues that can occur while you are using the BAM portal.</span></span>  
  
## <a name="errors-are-generated-when-the-bam-portal-and-internet-explorer-7-or-internet-explorer-8-are-on-the-same-computer-and-the-security-settings-are-set-to-low"></a><span data-ttu-id="befaf-104">BAM ポータルと Internet Explorer 7 または Internet Explorer 8 が同じコンピューター上にあり、セキュリティの設定が [低] に設定されている場合に発生するエラー</span><span class="sxs-lookup"><span data-stu-id="befaf-104">Errors Are Generated When the BAM Portal and Internet Explorer 7 or Internet Explorer 8 Are on the Same Computer and the Security Settings Are Set to Low</span></span>  
 <span data-ttu-id="befaf-105">**問題**</span><span class="sxs-lookup"><span data-stu-id="befaf-105">**Problem**</span></span>  
  
 <span data-ttu-id="befaf-106">Internet Explorer 7 または Internet Explorer 7 または Internet Explorer 8 を使用するときに[!INCLUDE[btsWinVista](../includes/btswinvista-md.md)]、 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]、または[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]エラー メッセージが発生する可能性があります**でサーバー エラー '/BAM' アプリケーション**次で状況:</span><span class="sxs-lookup"><span data-stu-id="befaf-106">When using Internet Explorer 7 or Internet Explorer 7 or Internet Explorer 8 with [!INCLUDE[btsWinVista](../includes/btswinvista-md.md)], [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], or [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] you may encounter the error message **Server Error in '/BAM' Application** under the following circumstances:</span></span>  
  
-   <span data-ttu-id="befaf-107">存在しないアクティビティ インスタンスを参照している関連アクティビティをクリックした場合</span><span class="sxs-lookup"><span data-stu-id="befaf-107">While clicking a related activity that points to a non-existing activity instance.</span></span>  
  
-   <span data-ttu-id="befaf-108">ながらクリックすると、**警告の保存**次のシナリオでボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="befaf-108">While clicking the **Save Alert** button in the following scenario:</span></span>  
  
    -   <span data-ttu-id="befaf-109">クエリを作成する、**アクティビティの検索**ページし、をクリックして**警告の設定**です。</span><span class="sxs-lookup"><span data-stu-id="befaf-109">You create a query on the **ActivitySearch** page and then click **Set Alert**.</span></span>  
  
    -   <span data-ttu-id="befaf-110">警告フィールドに入力し、をクリックして**警告の保存**です。</span><span class="sxs-lookup"><span data-stu-id="befaf-110">You complete the alert fields and then click **Save Alert**.</span></span>  
  
    -   <span data-ttu-id="befaf-111">[戻る] ボタンをクリックした。</span><span class="sxs-lookup"><span data-stu-id="befaf-111">You click the back button.</span></span>  
  
    -   <span data-ttu-id="befaf-112">クリックする、**警告の保存**を再度クリックします。</span><span class="sxs-lookup"><span data-stu-id="befaf-112">You click the **Save Alert** button again.</span></span>  
  
 <span data-ttu-id="befaf-113">**原因**</span><span class="sxs-lookup"><span data-stu-id="befaf-113">**Cause**</span></span>  
  
 <span data-ttu-id="befaf-114">[!INCLUDE[btsWinVista](../includes/btswinvista-md.md)] または [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] で、セキュリティ レベルを [低] に設定して Internet Explorer 7 または Internet Explorer 8 を実行している場合、Web 要求は低レベルの特権で実行されます。</span><span class="sxs-lookup"><span data-stu-id="befaf-114">When running [!INCLUDE[btsWinVista](../includes/btswinvista-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] and Internet Explorer 7 or Internet Explorer 8 with the security level set to low, Web requests are executed with low privileges.</span></span> <span data-ttu-id="befaf-115">Windows 統合セキュリティの問題に対応するために、Internet Explorer はユーザー トークンに対し、低レベルの特権しか渡しません。</span><span class="sxs-lookup"><span data-stu-id="befaf-115">To fulfill the Windows integrated security challenge, Internet Explorer passes a user token with low privileges.</span></span>  
  
 <span data-ttu-id="befaf-116">BAM ポータルがインストールされているコンピューターと同じコンピューターで Internet Explorer を使用し、Internet Explorer のセキュリティ レベルが [低] に設定されている場合、ポータルは低いレベルの特権トークンを持つユーザーの権限を借用します。</span><span class="sxs-lookup"><span data-stu-id="befaf-116">If you are using Internet Explorer on the same computer as the one on which the BAM portal is installed, and you set the security level in Internet Explorer to low, the portal impersonates the user with the low privileges token.</span></span> <span data-ttu-id="befaf-117">このトークンには、イベント ログに書き込むためのアクセス許可がありません。</span><span class="sxs-lookup"><span data-stu-id="befaf-117">This token does not have the permissions to write to the event log.</span></span> <span data-ttu-id="befaf-118">ポータルでエラーが発生すると、ポータルはイベント ログにそのエラーを記録しようとしますが、ユーザー トークンにはイベント ログにアクセスできる十分な権限がないため、操作は失敗します。</span><span class="sxs-lookup"><span data-stu-id="befaf-118">If the portal encounters an error, it attempts to log it to the event log and will fail since the reduced privileges of the user token are not sufficient to access the event log.</span></span>  
  
 <span data-ttu-id="befaf-119">**解決策**</span><span class="sxs-lookup"><span data-stu-id="befaf-119">**Resolution**</span></span>  
  
 <span data-ttu-id="befaf-120">ローカル コンピューターから参照する必要がある場合は、信頼済みサイトに http://localhost を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="befaf-120">If you need to browse from the local computer, you should add http://localhost to the list of trusted sites.</span></span>  
  
#### <a name="to-add-localhost-to-the-list-of-trusted-sites"></a><span data-ttu-id="befaf-121">信頼済みサイトに localhost を追加するには</span><span class="sxs-lookup"><span data-stu-id="befaf-121">To add localhost to the list of trusted sites</span></span>  
  
1.  <span data-ttu-id="befaf-122">Internet Explorer で、をクリックして**ツール**、クリックして**インターネット オプション**です。</span><span class="sxs-lookup"><span data-stu-id="befaf-122">In Internet Explorer, click **Tools**, and then click **Internet Options**.</span></span>  
  
2.  <span data-ttu-id="befaf-123">クリックして、**セキュリティ** タブをクリックして**信頼済みサイト**で、**を表示またはセキュリティ設定を変更するゾーンを選択して**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="befaf-123">Click the **Security** tab, and then click **Trusted Sites** in the **Select a zone to view or change security settings** window.</span></span>  
  
3.  <span data-ttu-id="befaf-124">クリックして、**サイト**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="befaf-124">Click the **Sites** button.</span></span>  
  
4.  <span data-ttu-id="befaf-125">**この web サイトをゾーンに追加**テキスト ボックスで、「 **http://localhost**です。</span><span class="sxs-lookup"><span data-stu-id="befaf-125">In the **Add this website to the zone** text box, type **http://localhost**.</span></span> <span data-ttu-id="befaf-126">場合、**サーバーの確認 (https:) このゾーン内のすべてのサイトの**チェック ボックスがオン、オフにし、をクリックして、**追加**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="befaf-126">If the **Require server verification (https:) for all sites in this zone** check box is selected, clear it and then click the **Add** button.</span></span> <span data-ttu-id="befaf-127">サイト、http://localhost に表示されます、 **web サイト** ボックスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="befaf-127">The site, http://localhost, will appear in the **Websites** list.</span></span>  
  
5.  <span data-ttu-id="befaf-128">必要に応じて、復元、**サーバーの確認 (https:) このゾーン内のすべてのサイトの**を元の状態のチェック ボックスです。</span><span class="sxs-lookup"><span data-stu-id="befaf-128">If necessary, restore the **Require server verification (https:) for all sites in this zone** check box to its original state.</span></span>  
  
6.  <span data-ttu-id="befaf-129">クリックして、**閉じる**ボタンをクリックし、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="befaf-129">Click the **Close** button, and then click **OK**.</span></span>  
  
## <a name="bam-portal-aggregations-do-not-populate-existing-data-when-using-an-ip-address-as-a-url-in-internet-explorer-7"></a><span data-ttu-id="befaf-130">Internet Explorer 7 で IP アドレスを URL として使用すると、BAM ポータルの集計に既存のデータが表示されない</span><span class="sxs-lookup"><span data-stu-id="befaf-130">Bam Portal Aggregations Do Not Populate Existing Data When Using an IP Address as a URL in Internet Explorer 7</span></span>  
 <span data-ttu-id="befaf-131">**問題**</span><span class="sxs-lookup"><span data-stu-id="befaf-131">**Problem**</span></span>  
  
 <span data-ttu-id="befaf-132">Internet Explorer 7 または Internet Explorer 8 を URL として IP アドレスを使用する場合と[!INCLUDE[btsWinVista](../includes/btswinvista-md.md)]、 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]、または[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]集計を BAM ポータルを表示するには、次のメッセージが表示します。"詳細なし。</span><span class="sxs-lookup"><span data-stu-id="befaf-132">When using an IP address as a URL with Internet Explorer 7 or Internet Explorer 8 and [!INCLUDE[btsWinVista](../includes/btswinvista-md.md)], [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], or [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] to view the BAM portal, aggregations display the following message: "No detail.</span></span> <span data-ttu-id="befaf-133">クエリを実行できませんでした。"</span><span class="sxs-lookup"><span data-stu-id="befaf-133">The query could not be processed."</span></span>  
  
 <span data-ttu-id="befaf-134">**原因**</span><span class="sxs-lookup"><span data-stu-id="befaf-134">**Cause**</span></span>  
  
 <span data-ttu-id="befaf-135">Internet Explorer 7 または Internet Explorer 8 の既定のセキュリティ設定では、IPv4 および IPv6 のアドレスを URL として使用してサイトにアクセスすることができません。</span><span class="sxs-lookup"><span data-stu-id="befaf-135">The default security settings in Internet Explorer 7 or Internet Explorer 8 prevents access to sites using IPv4 and IPv6 addresses as URLs.</span></span>  
  
 <span data-ttu-id="befaf-136">**解決策**</span><span class="sxs-lookup"><span data-stu-id="befaf-136">**Resolution**</span></span>  
  
 <span data-ttu-id="befaf-137">信頼済みサイトの一覧にサイト アドレスを追加し、ドメイン間でのデータ ソースのアクセスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="befaf-137">Add the site address to the trusted sites list and enable access to data sources across domains.</span></span>  
  
#### <a name="to-add-the-ip-address-to-the-trusted-sites-list"></a><span data-ttu-id="befaf-138">信頼済みサイト一覧に IP アドレスを追加するには</span><span class="sxs-lookup"><span data-stu-id="befaf-138">To add the IP address to the trusted sites list</span></span>  
  
1.  <span data-ttu-id="befaf-139">Internet Explorer で、をクリックして**ツール**、クリックして**インターネット オプション**です。</span><span class="sxs-lookup"><span data-stu-id="befaf-139">In Internet Explorer, click **Tools**, and then click **Internet Options**.</span></span>  
  
2.  <span data-ttu-id="befaf-140">クリックして、**セキュリティ** タブをクリックして、**信頼済みサイト**セキュリティ ゾーンです。</span><span class="sxs-lookup"><span data-stu-id="befaf-140">Click the **Security** tab, and then click the **Trusted sites** security zone.</span></span>  
  
3.  <span data-ttu-id="befaf-141">クリックして、**サイト**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="befaf-141">Click the **Sites** button.</span></span>  
  
4.  <span data-ttu-id="befaf-142">**この web サイトをゾーンに追加**、BAM ポータルの IP アドレスを入力して、をクリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="befaf-142">In **Add this website to the zone**, type the IP address of the BAM portal, and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="befaf-143">**[閉じる]**をクリックし、 **[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="befaf-143">Click **Close**, and then click **OK**.</span></span>  
  
#### <a name="to-enable-access-to-data-sources-across-domains"></a><span data-ttu-id="befaf-144">ドメイン間でのデータ ソースのアクセスを有効にするには</span><span class="sxs-lookup"><span data-stu-id="befaf-144">To enable access to data sources across domains</span></span>  
  
1.  <span data-ttu-id="befaf-145">Internet Explorer で、をクリックして**ツール**、クリックして**インターネット オプション**です。</span><span class="sxs-lookup"><span data-stu-id="befaf-145">In Internet Explorer, click **Tools**, and then click **Internet Options**.</span></span>  
  
2.  <span data-ttu-id="befaf-146">クリックして、**セキュリティ** タブをクリックして、**信頼済みサイト**セキュリティ ゾーンです。</span><span class="sxs-lookup"><span data-stu-id="befaf-146">Click the **Security** tab, and then click the **Trusted Sites** security zone.</span></span>  
  
3.  <span data-ttu-id="befaf-147">クリックして、**レベルのカスタマイズ**ボタンの下にスクロールすると、 **[その他]**のノード、**設定**ツリー。</span><span class="sxs-lookup"><span data-stu-id="befaf-147">Click the **Custom Level** button as you scroll down to the **Miscellaneous** node of the **Settings** tree.</span></span>  
  
4.  <span data-ttu-id="befaf-148">**ドメイン間でデータ ソースにアクセス**ノード、をクリックして、**オプションを有効にする**ボタンをクリックし、をクリックして**[ok]**です。</span><span class="sxs-lookup"><span data-stu-id="befaf-148">In the **Access data sources across domains** node, click the **Enable radio** button, and then click **OK**.</span></span>  
  
## <a name="bmexe-does-not-run-in-powershell"></a><span data-ttu-id="befaf-149">BM.exe が PowerShell で実行されない</span><span class="sxs-lookup"><span data-stu-id="befaf-149">BM.exe does not run in PowerShell</span></span>  
 <span data-ttu-id="befaf-150">**問題**</span><span class="sxs-lookup"><span data-stu-id="befaf-150">**Problem**</span></span>  
  
 <span data-ttu-id="befaf-151">次のコマンドを PowerShell で実行すると、エラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="befaf-151">The following command throws an error when run in PowerShell.</span></span>  
  
```  
bm.exe get-config -FileName:config.xml  
```  
  
 <span data-ttu-id="befaf-152">**原因**</span><span class="sxs-lookup"><span data-stu-id="befaf-152">**Cause**</span></span>  
  
 <span data-ttu-id="befaf-153">PowerShell が、.exe ファイルおよび構成ファイルのパスを見つけることができませんでした。</span><span class="sxs-lookup"><span data-stu-id="befaf-153">PowerShell could not locate the path of .exe and config files.</span></span>  
  
 <span data-ttu-id="befaf-154">**解決策**</span><span class="sxs-lookup"><span data-stu-id="befaf-154">**Resolution**</span></span>  
  
 <span data-ttu-id="befaf-155">PowerShell で bm.exe を使用する場合、.exe ファイルおよび構成ファイルの完全なパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="befaf-155">If you use bm.exe in PowerShell, specify the full path of .exe and config files.</span></span> <span data-ttu-id="befaf-156">例:`bm.exe get-config -FileName:config.xml`として指定する必要があります`“%BizTalkPathTracking%”\bm.exe get-config -FileName:”%InstallDir%”\Tracking\config.xml`です。</span><span class="sxs-lookup"><span data-stu-id="befaf-156">For example: `bm.exe get-config -FileName:config.xml` should be specified as `“%BizTalkPathTracking%”\bm.exe get-config -FileName:”%InstallDir%”\Tracking\config.xml`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="befaf-157">参照</span><span class="sxs-lookup"><span data-stu-id="befaf-157">See Also</span></span>  
 [<span data-ttu-id="befaf-158">BAM ポータルの計画</span><span class="sxs-lookup"><span data-stu-id="befaf-158">Planning for the BAM Portal</span></span>](../core/planning-for-the-bam-portal.md)