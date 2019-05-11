---
title: BAM ポータルの既知の問題 |Microsoft Docs
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
ms.openlocfilehash: 8a6eb2c711b654f5541c2c8fb7c42540b9210eb8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380954"
---
# <a name="known-issues-in-the-bam-portal"></a><span data-ttu-id="6ecb2-102">BAM ポータルでの既知の問題</span><span class="sxs-lookup"><span data-stu-id="6ecb2-102">Known Issues in the BAM Portal</span></span>
<span data-ttu-id="6ecb2-103">このトピックでには、特定し、BAM ポータルを使用しているときに発生する可能性がある問題を解決するのに役立つ情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6ecb2-103">This topic contains information to help you identify and resolve issues that can occur while you are using the BAM portal.</span></span>  
  
## <a name="errors-occur-when-the-bam-portal-and-ie-are-on-the-same-computer-and-security-settings-are-low"></a><span data-ttu-id="6ecb2-104">BAM ポータルと IE が同じコンピューター上とセキュリティ設定が低いときにエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="6ecb2-104">Errors occur when the BAM Portal and IE are on the same computer, and Security Settings are Low</span></span>  
 <span data-ttu-id="6ecb2-105">**問題**</span><span class="sxs-lookup"><span data-stu-id="6ecb2-105">**Problem**</span></span>  
  
 <span data-ttu-id="6ecb2-106">Internet Explorer を使用する場合は、エラー メッセージが発生する可能性があります**でサーバー エラー '/BAM' アプリケーション**次の状況で。</span><span class="sxs-lookup"><span data-stu-id="6ecb2-106">When using Internet Explorer, you may encounter the error message **Server Error in '/BAM' Application** under the following circumstances:</span></span>  
  
- <span data-ttu-id="6ecb2-107">ながら、存在しないアクティビティ インスタンスを指す関連アクティビティをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6ecb2-107">While clicking a related activity that points to a non-existing activity instance.</span></span>  
  
- <span data-ttu-id="6ecb2-108">クリックして、**警告の保存**次のシナリオでのボタン。</span><span class="sxs-lookup"><span data-stu-id="6ecb2-108">While clicking the **Save Alert** button in the following scenario:</span></span>  
  
  -   <span data-ttu-id="6ecb2-109">クエリを作成する、**アクティビティの検索**ページし、クリックして**警告の設定**します。</span><span class="sxs-lookup"><span data-stu-id="6ecb2-109">You create a query on the **ActivitySearch** page and then click **Set Alert**.</span></span>  
  
  -   <span data-ttu-id="6ecb2-110">アラートのフィールドをクリックした**警告の保存**します。</span><span class="sxs-lookup"><span data-stu-id="6ecb2-110">You complete the alert fields and then click **Save Alert**.</span></span>  
  
  -   <span data-ttu-id="6ecb2-111">[戻る] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6ecb2-111">You click the back button.</span></span>  
  
  -   <span data-ttu-id="6ecb2-112">クリックする、**警告の保存**もう一度ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6ecb2-112">You click the **Save Alert** button again.</span></span>  
  
  <span data-ttu-id="6ecb2-113">**原因**</span><span class="sxs-lookup"><span data-stu-id="6ecb2-113">**Cause**</span></span>  
  
  <span data-ttu-id="6ecb2-114">Web 要求を低に設定すると Internet Explorer を実行して、セキュリティ レベルでは、低レベルの特権で実行されます。</span><span class="sxs-lookup"><span data-stu-id="6ecb2-114">When running Internet Explorer with the security level set to low, Web requests are executed with low privileges.</span></span> <span data-ttu-id="6ecb2-115">Windows 統合セキュリティの問題を満たすためには、Internet Explorer は低レベルの特権でのユーザー トークンを渡します。</span><span class="sxs-lookup"><span data-stu-id="6ecb2-115">To fulfill the Windows integrated security challenge, Internet Explorer passes a user token with low privileges.</span></span>  
  
  <span data-ttu-id="6ecb2-116">優先度を低セキュリティを Internet Explorer で設定すると、BAM ポータルがインストールされているものと同じコンピューターに Internet Explorer を使用して、ポータルは、低レベルの特権トークンを使用してユーザーを偽装します。</span><span class="sxs-lookup"><span data-stu-id="6ecb2-116">If you are using Internet Explorer on the same computer as the one on which the BAM portal is installed, and you set the security level in Internet Explorer to low, the portal impersonates the user with the low privileges token.</span></span> <span data-ttu-id="6ecb2-117">このトークンには、イベント ログに書き込むアクセス許可がありません。</span><span class="sxs-lookup"><span data-stu-id="6ecb2-117">This token does not have the permissions to write to the event log.</span></span> <span data-ttu-id="6ecb2-118">ポータルには、エラーが発生すると、イベント ログにログを記録しようし、ユーザー トークンの権限は、イベント ログへのアクセスには不十分なために失敗します。</span><span class="sxs-lookup"><span data-stu-id="6ecb2-118">If the portal encounters an error, it attempts to log it to the event log and will fail since the reduced privileges of the user token are not sufficient to access the event log.</span></span>  
  
  <span data-ttu-id="6ecb2-119">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="6ecb2-119">**Resolution**</span></span>  
  
  <span data-ttu-id="6ecb2-120">追加するかどうかは、ローカル コンピューターから参照する必要があります、 http://localhost信頼済みサイトの一覧にします。</span><span class="sxs-lookup"><span data-stu-id="6ecb2-120">If you need to browse from the local computer, you should add http://localhost to the list of trusted sites.</span></span>  
  
#### <a name="add-localhost-to-the-list-of-trusted-sites"></a><span data-ttu-id="6ecb2-121">Localhost を信頼済みサイトの一覧に追加します。</span><span class="sxs-lookup"><span data-stu-id="6ecb2-121">Add localhost to the list of trusted sites</span></span>  
  
1.  <span data-ttu-id="6ecb2-122">Internet Explorer で、次のようにクリックします。**ツール**、 をクリックし、**インターネット オプション**します。</span><span class="sxs-lookup"><span data-stu-id="6ecb2-122">In Internet Explorer, click **Tools**, and then click **Internet Options**.</span></span>  
  
2.  <span data-ttu-id="6ecb2-123">をクリックして、**セキュリティ**タブをクリックし、をクリックし、**信頼済みサイト**で、**を表示またはセキュリティ設定を変更するゾーンを選択**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="6ecb2-123">Click the **Security** tab, and then click **Trusted Sites** in the **Select a zone to view or change security settings** window.</span></span>  
  
3.  <span data-ttu-id="6ecb2-124">をクリックして、**サイト**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6ecb2-124">Click the **Sites** button.</span></span>  
  
4.  <span data-ttu-id="6ecb2-125">**この web サイトをゾーンに追加**テキスト ボックスに「  **http://localhost**します。</span><span class="sxs-lookup"><span data-stu-id="6ecb2-125">In the **Add this website to the zone** text box, type **http://localhost**.</span></span> <span data-ttu-id="6ecb2-126">場合、**サーバーの確認が必要です (https:) すべてのサイトでこのゾーン** チェック ボックスをオン、オフにし、をクリックし、**追加**ボタン。</span><span class="sxs-lookup"><span data-stu-id="6ecb2-126">If the **Require server verification (https:) for all sites in this zone** check box is selected, clear it and then click the **Add** button.</span></span> <span data-ttu-id="6ecb2-127">サイト、 http://localhostに表示されます、 **Websites**一覧。</span><span class="sxs-lookup"><span data-stu-id="6ecb2-127">The site, http://localhost, will appear in the **Websites** list.</span></span>  
  
5.  <span data-ttu-id="6ecb2-128">必要に応じて、復元、**サーバーの確認 (https:) すべてのサイトでこのゾーン**を元の状態のチェック ボックス。</span><span class="sxs-lookup"><span data-stu-id="6ecb2-128">If necessary, restore the **Require server verification (https:) for all sites in this zone** check box to its original state.</span></span>  
  
6.  <span data-ttu-id="6ecb2-129">をクリックして、**閉じる**ボタンをクリックし、をクリックし、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="6ecb2-129">Click the **Close** button, and then click **OK**.</span></span>  
  
## <a name="bam-portal-aggregations-do-not-populate-existing-data-when-using-an-ip-address-as-a-url-in-internet-explorer"></a><span data-ttu-id="6ecb2-130">ユーザーは Internet Explorer で URL として IP アドレスを使用する場合は、Bam ポータルの集計には既存のデータは設定されません。</span><span class="sxs-lookup"><span data-stu-id="6ecb2-130">Bam Portal Aggregations Do Not Populate Existing Data When Using an IP Address as a URL in Internet Explorer</span></span>
 <span data-ttu-id="6ecb2-131">**問題**</span><span class="sxs-lookup"><span data-stu-id="6ecb2-131">**Problem**</span></span>  
  
 <span data-ttu-id="6ecb2-132">Internet Explorer を URL として、IP アドレスを使用して、BAM ポータルを表示する、集計、次のメッセージが表示されます。"詳細なし。</span><span class="sxs-lookup"><span data-stu-id="6ecb2-132">When using an IP address as a URL with Internet Explorer to view the BAM portal, aggregations display the following message: "No detail.</span></span> <span data-ttu-id="6ecb2-133">クエリ処理できませんでした。"</span><span class="sxs-lookup"><span data-stu-id="6ecb2-133">The query could not be processed."</span></span>  
  
 <span data-ttu-id="6ecb2-134">**原因**</span><span class="sxs-lookup"><span data-stu-id="6ecb2-134">**Cause**</span></span>  
  
 <span data-ttu-id="6ecb2-135">Internet Explorer で、既定のセキュリティ設定は、IPv4 と IPv6 アドレスを Url として使用してサイトにアクセスを禁止する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6ecb2-135">The default security settings in Internet Explorer may prevent access to sites using IPv4 and IPv6 addresses as URLs.</span></span>  
  
 <span data-ttu-id="6ecb2-136">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="6ecb2-136">**Resolution**</span></span>  
  
 <span data-ttu-id="6ecb2-137">信頼済みサイト一覧に、サイトのアドレスを追加し、ドメイン間でデータ ソースへのアクセスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="6ecb2-137">Add the site address to the trusted sites list and enable access to data sources across domains.</span></span>  
  
#### <a name="add-the-ip-address-to-the-trusted-sites-list"></a><span data-ttu-id="6ecb2-138">信頼済みサイト一覧に IP アドレスを追加します。</span><span class="sxs-lookup"><span data-stu-id="6ecb2-138">Add the IP address to the trusted sites list</span></span>  
  
1.  <span data-ttu-id="6ecb2-139">Internet Explorer で、次のようにクリックします。**ツール**、 をクリックし、**インターネット オプション**します。</span><span class="sxs-lookup"><span data-stu-id="6ecb2-139">In Internet Explorer, click **Tools**, and then click **Internet Options**.</span></span>  
  
2.  <span data-ttu-id="6ecb2-140">をクリックして、**セキュリティ**タブをクリックし、をクリックし、**信頼済みサイト**セキュリティ ゾーンです。</span><span class="sxs-lookup"><span data-stu-id="6ecb2-140">Click the **Security** tab, and then click the **Trusted sites** security zone.</span></span>  
  
3.  <span data-ttu-id="6ecb2-141">をクリックして、**サイト**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6ecb2-141">Click the **Sites** button.</span></span>  
  
4.  <span data-ttu-id="6ecb2-142">**この web サイトをゾーンに追加**、BAM ポータルの IP アドレスを入力して、クリックして、**追加**します。</span><span class="sxs-lookup"><span data-stu-id="6ecb2-142">In **Add this website to the zone**, type the IP address of the BAM portal, and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="6ecb2-143">**[閉じる]** をクリックし、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6ecb2-143">Click **Close**, and then click **OK**.</span></span>  
  
#### <a name="enable-access-to-data-sources-across-domains"></a><span data-ttu-id="6ecb2-144">ドメイン間でデータ ソースへのアクセスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="6ecb2-144">Enable access to data sources across domains</span></span>  
  
1.  <span data-ttu-id="6ecb2-145">Internet Explorer で、次のようにクリックします。**ツール**、 をクリックし、**インターネット オプション**します。</span><span class="sxs-lookup"><span data-stu-id="6ecb2-145">In Internet Explorer, click **Tools**, and then click **Internet Options**.</span></span>  
  
2.  <span data-ttu-id="6ecb2-146">をクリックして、**セキュリティ**タブをクリックし、をクリックし、**信頼済みサイト**セキュリティ ゾーンです。</span><span class="sxs-lookup"><span data-stu-id="6ecb2-146">Click the **Security** tab, and then click the **Trusted Sites** security zone.</span></span>  
  
3.  <span data-ttu-id="6ecb2-147">をクリックして、**レベルのカスタマイズ**ボタンの下にスクロールすると、 **[その他]** のノード、**設定**ツリー。</span><span class="sxs-lookup"><span data-stu-id="6ecb2-147">Click the **Custom Level** button as you scroll down to the **Miscellaneous** node of the **Settings** tree.</span></span>  
  
4.  <span data-ttu-id="6ecb2-148">**ドメイン間でデータ ソースにアクセス**ノード、をクリックして、**オプションを有効にする**ボタンをクリックし、をクリックし、 **[ok]** します。</span><span class="sxs-lookup"><span data-stu-id="6ecb2-148">In the **Access data sources across domains** node, click the **Enable radio** button, and then click **OK**.</span></span>  
  
## <a name="bmexe-does-not-run-in-powershell"></a><span data-ttu-id="6ecb2-149">BM.exe が PowerShell で実行されません。</span><span class="sxs-lookup"><span data-stu-id="6ecb2-149">BM.exe does not run in PowerShell</span></span>  
 <span data-ttu-id="6ecb2-150">**問題**</span><span class="sxs-lookup"><span data-stu-id="6ecb2-150">**Problem**</span></span>  
  
 <span data-ttu-id="6ecb2-151">次のコマンドは、PowerShell で実行するとエラーをスローします。</span><span class="sxs-lookup"><span data-stu-id="6ecb2-151">The following command throws an error when run in PowerShell.</span></span>  
  
```  
bm.exe get-config -FileName:config.xml  
```  
  
 <span data-ttu-id="6ecb2-152">**原因**</span><span class="sxs-lookup"><span data-stu-id="6ecb2-152">**Cause**</span></span>  
  
 <span data-ttu-id="6ecb2-153">PowerShell は、.exe および構成ファイルのパスを特定できませんでした。</span><span class="sxs-lookup"><span data-stu-id="6ecb2-153">PowerShell could not locate the path of .exe and config files.</span></span>  
  
 <span data-ttu-id="6ecb2-154">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="6ecb2-154">**Resolution**</span></span>  
  
 <span data-ttu-id="6ecb2-155">PowerShell で bm.exe を使用する場合は、.exe および構成ファイルの完全なパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="6ecb2-155">If you use bm.exe in PowerShell, specify the full path of .exe and config files.</span></span> <span data-ttu-id="6ecb2-156">例:`bm.exe get-config -FileName:config.xml`として指定する必要があります`“%BizTalkPathTracking%”\bm.exe get-config -FileName:”%InstallDir%”\Tracking\config.xml`します。</span><span class="sxs-lookup"><span data-stu-id="6ecb2-156">For example: `bm.exe get-config -FileName:config.xml` should be specified as `“%BizTalkPathTracking%”\bm.exe get-config -FileName:”%InstallDir%”\Tracking\config.xml`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ecb2-157">参照</span><span class="sxs-lookup"><span data-stu-id="6ecb2-157">See Also</span></span>  
 [<span data-ttu-id="6ecb2-158">BAM ポータルの計画</span><span class="sxs-lookup"><span data-stu-id="6ecb2-158">Planning for the BAM Portal</span></span>](../core/planning-for-the-bam-portal.md)