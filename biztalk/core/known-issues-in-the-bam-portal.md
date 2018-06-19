---
title: BAM ポータルに既知の問題 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e681e910-c664-479c-86f3-a6ae0ec97775
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61cbfa298590c62b359045b6c7372501d8ef397e
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2018
ms.locfileid: "29710757"
---
# <a name="known-issues-in-the-bam-portal"></a><span data-ttu-id="bdfcb-102">BAM ポータルでの既知の問題</span><span class="sxs-lookup"><span data-stu-id="bdfcb-102">Known Issues in the BAM Portal</span></span>
<span data-ttu-id="bdfcb-103">このトピックでは、BAM ポータルの使用中に発生する可能性がある問題の特定と解決に役立つ情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="bdfcb-103">This topic contains information to help you identify and resolve issues that can occur while you are using the BAM portal.</span></span>  
  
## <a name="errors-occur-when-the-bam-portal-and-ie-are-on-the-same-computer-and-security-settings-are-low"></a><span data-ttu-id="bdfcb-104">IE、BAM ポータルは、同一コンピューター上、およびセキュリティ設定が低いときにエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="bdfcb-104">Errors occur when the BAM Portal and IE are on the same computer, and Security Settings are Low</span></span>  
 <span data-ttu-id="bdfcb-105">**問題**</span><span class="sxs-lookup"><span data-stu-id="bdfcb-105">**Problem**</span></span>  
  
 <span data-ttu-id="bdfcb-106">Internet Explorer を使用する場合は、エラー メッセージが発生する可能性があります**でサーバー エラー '/BAM' アプリケーション**次の状況で。</span><span class="sxs-lookup"><span data-stu-id="bdfcb-106">When using Internet Explorer, you may encounter the error message **Server Error in '/BAM' Application** under the following circumstances:</span></span>  
  
-   <span data-ttu-id="bdfcb-107">存在しないアクティビティ インスタンスを参照している関連アクティビティをクリックした場合</span><span class="sxs-lookup"><span data-stu-id="bdfcb-107">While clicking a related activity that points to a non-existing activity instance.</span></span>  
  
-   <span data-ttu-id="bdfcb-108">ながらクリックすると、 **警告の保存** 次のシナリオでボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bdfcb-108">While clicking the **Save Alert** button in the following scenario:</span></span>  
  
    -   <span data-ttu-id="bdfcb-109">に対するクエリを作成する、 **アクティビティの検索** ページをクリックして **警告の設定**します。</span><span class="sxs-lookup"><span data-stu-id="bdfcb-109">You create a query on the **ActivitySearch** page and then click **Set Alert**.</span></span>  
  
    -   <span data-ttu-id="bdfcb-110">警告フィールドに入力し、クリックする **警告の保存**します。</span><span class="sxs-lookup"><span data-stu-id="bdfcb-110">You complete the alert fields and then click **Save Alert**.</span></span>  
  
    -   <span data-ttu-id="bdfcb-111">[戻る] ボタンをクリックした。</span><span class="sxs-lookup"><span data-stu-id="bdfcb-111">You click the back button.</span></span>  
  
    -   <span data-ttu-id="bdfcb-112">クリックする、 **警告の保存** をもう一度クリックします。</span><span class="sxs-lookup"><span data-stu-id="bdfcb-112">You click the **Save Alert** button again.</span></span>  
  
 <span data-ttu-id="bdfcb-113">**原因**</span><span class="sxs-lookup"><span data-stu-id="bdfcb-113">**Cause**</span></span>  
  
 <span data-ttu-id="bdfcb-114">低、Web 要求に設定するとセキュリティ レベルで Internet Explorer を実行すると、低い特権で実行されます。</span><span class="sxs-lookup"><span data-stu-id="bdfcb-114">When running Internet Explorer with the security level set to low, Web requests are executed with low privileges.</span></span> <span data-ttu-id="bdfcb-115">Windows 統合セキュリティの問題に対応するために、Internet Explorer はユーザー トークンに対し、低レベルの特権しか渡しません。</span><span class="sxs-lookup"><span data-stu-id="bdfcb-115">To fulfill the Windows integrated security challenge, Internet Explorer passes a user token with low privileges.</span></span>  
  
 <span data-ttu-id="bdfcb-116">BAM ポータルがインストールされているコンピューターと同じコンピューターで Internet Explorer を使用し、Internet Explorer のセキュリティ レベルが [低] に設定されている場合、ポータルは低いレベルの特権トークンを持つユーザーの権限を借用します。</span><span class="sxs-lookup"><span data-stu-id="bdfcb-116">If you are using Internet Explorer on the same computer as the one on which the BAM portal is installed, and you set the security level in Internet Explorer to low, the portal impersonates the user with the low privileges token.</span></span> <span data-ttu-id="bdfcb-117">このトークンには、イベント ログに書き込むためのアクセス許可がありません。</span><span class="sxs-lookup"><span data-stu-id="bdfcb-117">This token does not have the permissions to write to the event log.</span></span> <span data-ttu-id="bdfcb-118">ポータルでエラーが発生すると、ポータルはイベント ログにそのエラーを記録しようとしますが、ユーザー トークンにはイベント ログにアクセスできる十分な権限がないため、操作は失敗します。</span><span class="sxs-lookup"><span data-stu-id="bdfcb-118">If the portal encounters an error, it attempts to log it to the event log and will fail since the reduced privileges of the user token are not sufficient to access the event log.</span></span>  
  
 <span data-ttu-id="bdfcb-119">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="bdfcb-119">**Resolution**</span></span>  
  
 <span data-ttu-id="bdfcb-120">ローカル コンピューターから参照する必要がある場合は、信頼済みサイトに http://localhost を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bdfcb-120">If you need to browse from the local computer, you should add http://localhost to the list of trusted sites.</span></span>  
  
#### <a name="add-localhost-to-the-list-of-trusted-sites"></a><span data-ttu-id="bdfcb-121">Localhost を信頼済みサイトの一覧に追加します。</span><span class="sxs-lookup"><span data-stu-id="bdfcb-121">Add localhost to the list of trusted sites</span></span>  
  
1.  <span data-ttu-id="bdfcb-122">Internet Explorer でクリックして **ツール**, 、 をクリックし、 **インターネット オプション**します。</span><span class="sxs-lookup"><span data-stu-id="bdfcb-122">In Internet Explorer, click **Tools**, and then click **Internet Options**.</span></span>  
  
2.  <span data-ttu-id="bdfcb-123">クリックして、 **セキュリティ** タブをクリックし、をクリックして **信頼済みサイト** で、 **を表示またはセキュリティ設定を変更するゾーンを選択** ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="bdfcb-123">Click the **Security** tab, and then click **Trusted Sites** in the **Select a zone to view or change security settings** window.</span></span>  
  
3.  <span data-ttu-id="bdfcb-124">クリックして、 **サイト**  ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bdfcb-124">Click the **Sites** button.</span></span>  
  
4.  <span data-ttu-id="bdfcb-125">**この web サイトをゾーンに追加** テキスト ボックスに「 **http://localhost**します。</span><span class="sxs-lookup"><span data-stu-id="bdfcb-125">In the **Add this website to the zone** text box, type **http://localhost**.</span></span> <span data-ttu-id="bdfcb-126">場合、 **サーバーの確認 (https:) のこのゾーン内のすべてのサイト**  チェック ボックスをオン、オフにし、をクリックして、 **追加**  ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bdfcb-126">If the **Require server verification (https:) for all sites in this zone** check box is selected, clear it and then click the **Add** button.</span></span> <span data-ttu-id="bdfcb-127">サイト、http://localhost に表示されます、 **Websites**  ボックスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="bdfcb-127">The site, http://localhost, will appear in the **Websites** list.</span></span>  
  
5.  <span data-ttu-id="bdfcb-128">必要に応じて、復元、 **サーバーの確認 (https:) このゾーン内のすべてのサイトの** を元の状態のチェック ボックスです。</span><span class="sxs-lookup"><span data-stu-id="bdfcb-128">If necessary, restore the **Require server verification (https:) for all sites in this zone** check box to its original state.</span></span>  
  
6.  <span data-ttu-id="bdfcb-129">クリックして、 **閉じる** ボタンをクリックし、をクリックし、 **[ok]** します。</span><span class="sxs-lookup"><span data-stu-id="bdfcb-129">Click the **Close** button, and then click **OK**.</span></span>  
  
## <a name="bam-portal-aggregations-do-not-populate-existing-data-when-using-an-ip-address-as-a-url-in-internet-explorer"></a><span data-ttu-id="bdfcb-130">ユーザーは、IP アドレスを Internet Explorer での URL として使用する場合は、Bam ポータルの集計には既存のデータは設定されません。</span><span class="sxs-lookup"><span data-stu-id="bdfcb-130">Bam Portal Aggregations Do Not Populate Existing Data When Using an IP Address as a URL in Internet Explorer</span></span>
 <span data-ttu-id="bdfcb-131">**問題**</span><span class="sxs-lookup"><span data-stu-id="bdfcb-131">**Problem**</span></span>  
  
 <span data-ttu-id="bdfcb-132">Internet Explorer を URL として IP アドレスを使用して、BAM ポータルを表示する、集計に次のメッセージが表示します。"詳細なし。</span><span class="sxs-lookup"><span data-stu-id="bdfcb-132">When using an IP address as a URL with Internet Explorer to view the BAM portal, aggregations display the following message: "No detail.</span></span> <span data-ttu-id="bdfcb-133">クエリを実行できませんでした。"</span><span class="sxs-lookup"><span data-stu-id="bdfcb-133">The query could not be processed."</span></span>  
  
 <span data-ttu-id="bdfcb-134">**原因**</span><span class="sxs-lookup"><span data-stu-id="bdfcb-134">**Cause**</span></span>  
  
 <span data-ttu-id="bdfcb-135">Internet Explorer の既定のセキュリティ設定によっては、IPv4 と IPv6 アドレスを Url として使用してサイトにアクセスができなくなります。</span><span class="sxs-lookup"><span data-stu-id="bdfcb-135">The default security settings in Internet Explorer may prevent access to sites using IPv4 and IPv6 addresses as URLs.</span></span>  
  
 <span data-ttu-id="bdfcb-136">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="bdfcb-136">**Resolution**</span></span>  
  
 <span data-ttu-id="bdfcb-137">信頼済みサイトの一覧にサイト アドレスを追加し、ドメイン間でのデータ ソースのアクセスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="bdfcb-137">Add the site address to the trusted sites list and enable access to data sources across domains.</span></span>  
  
#### <a name="add-the-ip-address-to-the-trusted-sites-list"></a><span data-ttu-id="bdfcb-138">信頼済みサイト一覧に IP アドレスを追加します。</span><span class="sxs-lookup"><span data-stu-id="bdfcb-138">Add the IP address to the trusted sites list</span></span>  
  
1.  <span data-ttu-id="bdfcb-139">Internet Explorer でクリックして **ツール**, 、 をクリックし、 **インターネット オプション**します。</span><span class="sxs-lookup"><span data-stu-id="bdfcb-139">In Internet Explorer, click **Tools**, and then click **Internet Options**.</span></span>  
  
2.  <span data-ttu-id="bdfcb-140">クリックして、 **セキュリティ** タブをクリックし、をクリックして、 **信頼済みサイト** セキュリティ ゾーンです。</span><span class="sxs-lookup"><span data-stu-id="bdfcb-140">Click the **Security** tab, and then click the **Trusted sites** security zone.</span></span>  
  
3.  <span data-ttu-id="bdfcb-141">クリックして、 **サイト**  ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bdfcb-141">Click the **Sites** button.</span></span>  
  
4.  <span data-ttu-id="bdfcb-142">**この web サイトをゾーンに追加**, を BAM ポータルの IP アドレスを入力して、クリックして **追加**します。</span><span class="sxs-lookup"><span data-stu-id="bdfcb-142">In **Add this website to the zone**, type the IP address of the BAM portal, and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="bdfcb-143">**[閉じる]** をクリックし、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bdfcb-143">Click **Close**, and then click **OK**.</span></span>  
  
#### <a name="enable-access-to-data-sources-across-domains"></a><span data-ttu-id="bdfcb-144">ドメイン間でデータ ソースへのアクセスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="bdfcb-144">Enable access to data sources across domains</span></span>  
  
1.  <span data-ttu-id="bdfcb-145">Internet Explorer でクリックして **ツール**, 、 をクリックし、 **インターネット オプション**します。</span><span class="sxs-lookup"><span data-stu-id="bdfcb-145">In Internet Explorer, click **Tools**, and then click **Internet Options**.</span></span>  
  
2.  <span data-ttu-id="bdfcb-146">クリックして、 **セキュリティ** タブをクリックし、をクリックして、 **信頼済みサイト** セキュリティ ゾーンです。</span><span class="sxs-lookup"><span data-stu-id="bdfcb-146">Click the **Security** tab, and then click the **Trusted Sites** security zone.</span></span>  
  
3.  <span data-ttu-id="bdfcb-147">クリックして、 **レベルのカスタマイズ** ボタンまで下へスクロール、 **[その他]** のノード、 **設定** ツリーです。</span><span class="sxs-lookup"><span data-stu-id="bdfcb-147">Click the **Custom Level** button as you scroll down to the **Miscellaneous** node of the **Settings** tree.</span></span>  
  
4.  <span data-ttu-id="bdfcb-148">**ドメイン間でデータ ソースにアクセス**  ノードをクリックして、 **オプションを有効にする** ボタンをクリックし、をクリックして **ok**します。</span><span class="sxs-lookup"><span data-stu-id="bdfcb-148">In the **Access data sources across domains** node, click the **Enable radio** button, and then click **OK**.</span></span>  
  
## <a name="bmexe-does-not-run-in-powershell"></a><span data-ttu-id="bdfcb-149">BM.exe が PowerShell で実行されない</span><span class="sxs-lookup"><span data-stu-id="bdfcb-149">BM.exe does not run in PowerShell</span></span>  
 <span data-ttu-id="bdfcb-150">**問題**</span><span class="sxs-lookup"><span data-stu-id="bdfcb-150">**Problem**</span></span>  
  
 <span data-ttu-id="bdfcb-151">次のコマンドを PowerShell で実行すると、エラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="bdfcb-151">The following command throws an error when run in PowerShell.</span></span>  
  
```  
bm.exe get-config -FileName:config.xml  
```  
  
 <span data-ttu-id="bdfcb-152">**原因**</span><span class="sxs-lookup"><span data-stu-id="bdfcb-152">**Cause**</span></span>  
  
 <span data-ttu-id="bdfcb-153">PowerShell が、.exe ファイルおよび構成ファイルのパスを見つけることができませんでした。</span><span class="sxs-lookup"><span data-stu-id="bdfcb-153">PowerShell could not locate the path of .exe and config files.</span></span>  
  
 <span data-ttu-id="bdfcb-154">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="bdfcb-154">**Resolution**</span></span>  
  
 <span data-ttu-id="bdfcb-155">PowerShell で bm.exe を使用する場合、.exe ファイルおよび構成ファイルの完全なパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="bdfcb-155">If you use bm.exe in PowerShell, specify the full path of .exe and config files.</span></span> <span data-ttu-id="bdfcb-156">例: `bm.exe get-config -FileName:config.xml` として指定する必要があります `“%BizTalkPathTracking%”\bm.exe get-config -FileName:”%InstallDir%”\Tracking\config.xml`します。</span><span class="sxs-lookup"><span data-stu-id="bdfcb-156">For example: `bm.exe get-config -FileName:config.xml` should be specified as `“%BizTalkPathTracking%”\bm.exe get-config -FileName:”%InstallDir%”\Tracking\config.xml`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdfcb-157">参照</span><span class="sxs-lookup"><span data-stu-id="bdfcb-157">See Also</span></span>  
 [<span data-ttu-id="bdfcb-158">BAM ポータルの計画</span><span class="sxs-lookup"><span data-stu-id="bdfcb-158">Planning for the BAM Portal</span></span>](../core/planning-for-the-bam-portal.md)