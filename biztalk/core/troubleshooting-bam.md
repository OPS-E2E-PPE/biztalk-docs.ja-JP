---
title: BAM のトラブルシューティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e63299a8-5c74-4337-ba20-3213e0c6ea1f
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d068b3f669400f2f7b55a3279aa40090adc8689f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243263"
---
# <a name="troubleshooting-bam"></a><span data-ttu-id="0a052-102">BAM のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="0a052-102">Troubleshooting BAM</span></span>
<span data-ttu-id="0a052-103">このトピックでは、ビジネス アクティビティ監視 (BAM) を使用する場合に発生する可能性が問題のトラブルシューティングに役立つ情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="0a052-103">This topic provides information to help you troubleshoot problems you might encounter when using Business Activity Monitoring (BAM).</span></span>  
  
## <a name="bam-deployment-failed"></a><span data-ttu-id="0a052-104">BAM を展開できませんでした。</span><span class="sxs-lookup"><span data-stu-id="0a052-104">BAM deployment failed</span></span>  
 <span data-ttu-id="0a052-105">SQL Server Analysis Services が利用できない場合は、リアルタイム集計 (RTA) を含む BAM 定義を展開しようとした場合、Bm.exe コマンドには、次のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0a052-105">If you attempt to deploy a BAM definition that includes a real-time aggregation (RTA) when SQL Server Analysis Services is not available, the Bm.exe command will display the following message:</span></span>  
  
 <span data-ttu-id="0a052-106">ERROR:BAM の展開に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="0a052-106">ERROR: BAM deployment failed.</span></span> <span data-ttu-id="0a052-107">接続できません。</span><span class="sxs-lookup"><span data-stu-id="0a052-107">A connection cannot be made.</span></span> <span data-ttu-id="0a052-108">サーバーが実行中であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0a052-108">Ensure that the server is running.</span></span> <span data-ttu-id="0a052-109">ターゲット コンピューターによって拒否されたため、接続は行われません *\<IP アドレス\>* します。</span><span class="sxs-lookup"><span data-stu-id="0a052-109">No connection could be made because the target machine actively refused it *\<IP address\>*.</span></span>  
  
 <span data-ttu-id="0a052-110">これには、SQL Server Analysis Services が既にインストールされている必要があります、構成されているし、RTA を含む BAM 定義を展開するために実行されている必要がありますが発生します。</span><span class="sxs-lookup"><span data-stu-id="0a052-110">This occurs because SQL Server Analysis Services must have been installed and configured, and must be running in order to deploy a BAM definition that includes an RTA.</span></span>  
  
## <a name="cannot-refresh-the-live-data-workbook"></a><span data-ttu-id="0a052-111">ライブ データ ブックを更新することはできません。</span><span class="sxs-lookup"><span data-stu-id="0a052-111">Cannot refresh the live data workbook</span></span>  
 <span data-ttu-id="0a052-112">ライブ データ ブックのデータを更新しようとすると、Microsoft Office Excel には、次のエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0a052-112">When you try to refresh the data in a live data workbook, Microsoft Office Excel might display the following error:</span></span>  
  
 `XML for Analysis parser: The CurrentCatalog XML/A property was not specified.`  
  
 <span data-ttu-id="0a052-113">これには、BAM アドインが追加されていない Excel にために発生します。</span><span class="sxs-lookup"><span data-stu-id="0a052-113">This occurs because the BAM add-in has not been added to Excel.</span></span>  
  
#### <a name="add-the-bam-add-in-to-excel"></a><span data-ttu-id="0a052-114">Excel に BAM アドインを追加します。</span><span class="sxs-lookup"><span data-stu-id="0a052-114">Add the BAM add-in to Excel</span></span>  
  
1.  <span data-ttu-id="0a052-115">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office**、順にクリックします**Microsoft Office Excel**します。</span><span class="sxs-lookup"><span data-stu-id="0a052-115">Click **Start**, point to **All Programs**, point to **Microsoft Office**, and then click **Microsoft Office Excel**.</span></span>  
  
2.  <span data-ttu-id="0a052-116">をクリックして、 **Microsoft Office ボタン**、順にクリックします**Excel オプション**します。</span><span class="sxs-lookup"><span data-stu-id="0a052-116">Click the **Microsoft Office Button**, and then click **Excel Options**.</span></span>  
  
3.  <span data-ttu-id="0a052-117">**Excel オプション**ダイアログ ボックスで、をクリックして**アドイン**。</span><span class="sxs-lookup"><span data-stu-id="0a052-117">In the **Excel Options** dialog box, click **Add-Ins**.</span></span>  
  
4.  <span data-ttu-id="0a052-118">**アドイン**ウィンドウで、をクリックして**移動**します。</span><span class="sxs-lookup"><span data-stu-id="0a052-118">In the **Add-Ins** pane, click **Go**.</span></span>  
  
5.  <span data-ttu-id="0a052-119">**アドイン**ダイアログ ボックスで、**ビジネス アクティビティ監視**チェック ボックスをオンにし**OK**。</span><span class="sxs-lookup"><span data-stu-id="0a052-119">In the **Add-Ins** dialog box, select the **Business Activity Monitoring** check box, and then click **OK**.</span></span>  
  
     <span data-ttu-id="0a052-120">![追加&#45;アドイン ダイアログ ボックス](../core/media/addins.gif "AddIns")</span><span class="sxs-lookup"><span data-stu-id="0a052-120">![Add&#45;Ins dialog box](../core/media/addins.gif "AddIns")</span></span>  
  
## <a name="errorobject-library-invalid-or-contains-references-to-object-definitions-that-could-not-be-found-with-bam-excel-add-in-in-office"></a><span data-ttu-id="0a052-121">エラー:「オブジェクト ライブラリが無効または見つかりませんでしたオブジェクト定義への参照が含まれています」と BAM Excel アドインで Office</span><span class="sxs-lookup"><span data-stu-id="0a052-121">Error:"Object library invalid or contains references to object definitions that could not be found" with BAM Excel Add-In in Office</span></span>  
 <span data-ttu-id="0a052-122">Microsoft Excel をアップグレードした後に BAM Excel アドイン使用しようとすると、このエラーが表示される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0a052-122">You may receive this error, when you try use the BAM Excel Add-In after you upgrade Microsoft Excel.</span></span>  
  
 <span data-ttu-id="0a052-123">**解決方法:** BAM アドインには、ActiveX コントロールを使用するため、次のディレクトリからキャッシュされている .exd ファイルを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a052-123">**Resolution:** Since the BAM Add-In uses ActiveX controls, you have to delete any cached .exd files from the following directories:</span></span>  
  
-   <span data-ttu-id="0a052-124">C:\Documents and Settings\\< ユーザー名\>\Application Data\Microsoft\Forms</span><span class="sxs-lookup"><span data-stu-id="0a052-124">C:\Documents and Settings\\<username\>\Application Data\Microsoft\Forms</span></span>  
  
-   <span data-ttu-id="0a052-125">C:\Documents and Settings\\< ユーザー名\>\AppData\Local\Temp\VBE</span><span class="sxs-lookup"><span data-stu-id="0a052-125">C:\Documents and Settings\\<username\>\AppData\Local\Temp\VBE</span></span>  
  
## <a name="bam-portal-cannot-connect"></a><span data-ttu-id="0a052-126">BAM ポータルが接続できません。</span><span class="sxs-lookup"><span data-stu-id="0a052-126">BAM portal cannot connect</span></span>  
<span data-ttu-id="0a052-127">BAM ポータルを管理者として実行します。</span><span class="sxs-lookup"><span data-stu-id="0a052-127">Run the BAM portal as an administrator.</span></span>  
  
#### <a name="run-the-bam-portal"></a><span data-ttu-id="0a052-128">BAM ポータルを実行します。</span><span class="sxs-lookup"><span data-stu-id="0a052-128">Run the BAM portal</span></span>
  
1.  <span data-ttu-id="0a052-129">をクリックして**開始**、 をポイント**すべてのプログラム**を右クリックして**Internet Explorer**、順にクリックします**管理者として実行**します。</span><span class="sxs-lookup"><span data-stu-id="0a052-129">Click **Start**, point to **All Programs**, right-click **Internet Explorer**, and then click **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="0a052-130">**ユーザー アカウント制御**ダイアログ ボックスで、をクリックして**続行**します。</span><span class="sxs-lookup"><span data-stu-id="0a052-130">In the **User Account Control** dialog box, click **Continue**.</span></span>  
  
3.  <span data-ttu-id="0a052-131">Internet Explorer アドレス バーに「`http://<server>/BAM`ここで、 *\<server\>* BAM ポータルを実行しているコンピューター名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="0a052-131">In the Internet Explorer address bar, type `http://<server>/BAM`, where *\<server\>* is the name of the computer that is running the BAM portal.</span></span>  
  
## <a name="bam-portal-does-not-work-if-invalid-users-are-granted-permissions"></a><span data-ttu-id="0a052-132">BAM ポータルでは、無効なユーザーのアクセス許可が与えられる場合は機能しません</span><span class="sxs-lookup"><span data-stu-id="0a052-132">BAM portal does not work if invalid users are granted permissions</span></span>  
 <span data-ttu-id="0a052-133">BAM ビューのアクセス許可を持つ AD ユーザーは、AD から削除する場合、BAM ポータル正しく読み込まれません (DBO) を除くすべてのユーザー。</span><span class="sxs-lookup"><span data-stu-id="0a052-133">If an AD user who has the BAM view permissions is removed from the AD, then the BAM portal does not load properly for any user (except DBO).</span></span>  
  
 <span data-ttu-id="0a052-134">この問題を解決するには、対応する bam _ {ビュー名} view セキュリティ ロールから無効なユーザーを削除します。</span><span class="sxs-lookup"><span data-stu-id="0a052-134">To resolve this issue, remove the invalid user from the corresponding bam_{viewname}view security role.</span></span>  
  
## <a name="cannot-export-or-import-a-bam-definition-to-localhost"></a><span data-ttu-id="0a052-135">エクスポートまたは localhost に BAM 定義をインポートできません。</span><span class="sxs-lookup"><span data-stu-id="0a052-135">Cannot export or import a BAM definition to localhost</span></span>  
 <span data-ttu-id="0a052-136">BAM 定義を XML としてエクスポートするときに localhost にエクスポートしようとする場合は、次のエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0a052-136">When you export a BAM definition as XML, you will see the following error message if you try to export to localhost:</span></span>  
  
 `The system cannot find the path specified.`  
  
 <span data-ttu-id="0a052-137">Localhost に BAM 定義のエクスポートはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="0a052-137">Exporting a BAM definition to localhost is not supported.</span></span> <span data-ttu-id="0a052-138">同様に、localhost から BAM 定義をインポートすることはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="0a052-138">Similarly, importing a BAM definition from localhost is not supported.</span></span>  
  
## <a name="alerts-do-not-work-after-upgrading-sql-server-editions"></a><span data-ttu-id="0a052-139">SQL Server のエディションのアップグレード後にアラートが機能しません。</span><span class="sxs-lookup"><span data-stu-id="0a052-139">Alerts do not work after upgrading SQL Server editions</span></span>  
 <span data-ttu-id="0a052-140">(たとえば、Enterprise Edition を Standard Edition) から別のエディションに 1 つのエディションの SQL Server からアップグレードした場合、BAM 警告は再起動されません。</span><span class="sxs-lookup"><span data-stu-id="0a052-140">If you have upgraded from one edition of SQL Server to another edition (for example, from Standard Edition to Enterprise Edition), BAM alerts will not restart.</span></span> <span data-ttu-id="0a052-141">この問題を解決するには、BAM 警告を削除および再作成するには、または、SQL Server Notification Service をアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="0a052-141">To fix this problem, either delete the BAM alerts and re-create them, or upgrade the SQL Server Notification Service.</span></span>  
  
#### <a name="upgrade-the-sql-server-notification-service"></a><span data-ttu-id="0a052-142">SQL Server の通知サービスをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="0a052-142">Upgrade the SQL Server Notification Service</span></span>  
  
1.  <span data-ttu-id="0a052-143">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2005**、順にクリックします**Notification Service のコマンド プロンプト**します。</span><span class="sxs-lookup"><span data-stu-id="0a052-143">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2005**, and then click **Notification Service Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="0a052-144">コマンド プロンプトで次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="0a052-144">Type the following command at the command prompt:</span></span>  
  
     `nscontrol.exe upgrade -name <instanceName>`  
  
## <a name="objectdisposedexception-exception"></a><span data-ttu-id="0a052-145">ObjectDisposedException 例外</span><span class="sxs-lookup"><span data-stu-id="0a052-145">ObjectDisposedException Exception</span></span>  
 <span data-ttu-id="0a052-146">アプリケーションが BAM WF 3.5 インターセプターを使用している場合、次のエラー メッセージが表示される可能性があります。**System.ObjectDisposedException:破棄されたオブジェクトにアクセスできません**します。</span><span class="sxs-lookup"><span data-stu-id="0a052-146">If your application is using BAM WF 3.5 interceptor, you may receive the following error message: **System.ObjectDisposedException: Cannot access a disposed object**.</span></span> <span data-ttu-id="0a052-147">このエラー メッセージの詳細については、次を参照してください。 [ObjectDisposedException 例外](https://support.microsoft.com/help/960754)します。</span><span class="sxs-lookup"><span data-stu-id="0a052-147">For more information about this error message, see [ObjectDisposedException Exception](https://support.microsoft.com/help/960754).</span></span> 

<span data-ttu-id="0a052-148">この問題を解決するには、インストール、[修正プログラム 960754](https://support.microsoft.com/help/960754)します。</span><span class="sxs-lookup"><span data-stu-id="0a052-148">To resolve this issue, install the [hotfix 960754](https://support.microsoft.com/help/960754).</span></span> 
  
## <a name="workbook-has-lost-its-vba-project-activex-controls-and-other-programmability-related-features"></a><span data-ttu-id="0a052-149">ブックは、VBA プロジェクト、ActiveX コントロールおよびその他のプログラミング関連の機能に失われています</span><span class="sxs-lookup"><span data-stu-id="0a052-149">Workbook has lost its VBA project, ActiveX controls and other programmability-related features</span></span>  
 <span data-ttu-id="0a052-150">BAM.xla を Excel で使用しようとすると、次のエラーが発生した可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0a052-150">When attempting to use BAM.xla in Microsoft Excel, you may get the following error:</span></span>  
  
 `This workbook has lost its VBA project, ActiveX controls and any other programmability-related features.`  
  
 <span data-ttu-id="0a052-151">この問題を解決するには、インストール、**アプリケーション用の Visual Basic**オプションで  **Office 共有機能**Microsoft Office とします。</span><span class="sxs-lookup"><span data-stu-id="0a052-151">To resolve this issue, install the **Visual Basic for Applications** option under **Office Shared Features** with Microsoft Office.</span></span>  
  
## <a name="pivot-table-fails-to-get-the-data"></a><span data-ttu-id="0a052-152">ピボット テーブルがデータの取得に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="0a052-152">Pivot table fails to get the data</span></span>  
 <span data-ttu-id="0a052-153">デプロイされているビューに、BAM データベースともロールへのアクセス許可とアクセス許可があります。</span><span class="sxs-lookup"><span data-stu-id="0a052-153">You have permissions to access BAM databases, and also role and permissions on the views which are deployed.</span></span> <span data-ttu-id="0a052-154">アクティビティの検索ページが期待どおりに動作し、データを確認できます。</span><span class="sxs-lookup"><span data-stu-id="0a052-154">The Activity Search page works as expected and you can see the data.</span></span> <span data-ttu-id="0a052-155">ただし、ピボット テーブルで、次のエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0a052-155">But, in the Pivot table, the following error is displayed:</span></span>  
  
```  
Failed to get data.  If available, errors returned from the provider are listed below.  
* The following system error occurred:  No connection could be made because the target machine actively refused it.  
```  
  
 <span data-ttu-id="0a052-156">この問題を解決するには、対応する DNS を追加するには、設定として次に示します。</span><span class="sxs-lookup"><span data-stu-id="0a052-156">To resolve this issue, add the respective DNS settings as follows:</span></span>  
  
1.  <span data-ttu-id="0a052-157">クリックして**開始**に移動し、\*\*コントロール パネルの \*\*します。</span><span class="sxs-lookup"><span data-stu-id="0a052-157">Click **Start** and go to **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="0a052-158">クリックして**ネットワークとインターネット** をクリックし、**ネットワーク接続**します。</span><span class="sxs-lookup"><span data-stu-id="0a052-158">Click **Network and Internet** and then click **Network Connections**.</span></span>  
  
3.  <span data-ttu-id="0a052-159">(ローカル エリア接続) のようなネットワーク接続を右クリックし、選択**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="0a052-159">Right-click on the network connection (like Local Area Connection), and select **Properties**.</span></span>  
  
4.  <span data-ttu-id="0a052-160">**Local Area Connection**  ページで、**インターネット プロトコル バージョン 4 (Tcp/ipv4)**、 をクリック**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="0a052-160">On the **Local Area Connection** page, select **Internet Protocol Version 4 (TCP/IPv4)**, and click **Properties**.</span></span>  
  
5.  <span data-ttu-id="0a052-161">**[詳細設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0a052-161">Click **Advanced**.</span></span> <span data-ttu-id="0a052-162">**TCP/IP 詳細設定** ページで、をクリックして、 **DNS**タブ。</span><span class="sxs-lookup"><span data-stu-id="0a052-162">On the **Advance TCP/IP Settings** page, click the **DNS** tab.</span></span>  
  
6.  <span data-ttu-id="0a052-163">選択**これらの DNS サフィックスを追加する**し、必要な DNS サフィックスを追加します。</span><span class="sxs-lookup"><span data-stu-id="0a052-163">Select **Append these DNS suffixes** and then add the required DNS suffixes.</span></span>  
  
7.  <span data-ttu-id="0a052-164">クリックして**OK**し、すべての開いているウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="0a052-164">Click **OK** and close all the open windows.</span></span>  
  
## <a name="pivot-table-view-shows-all-values-as-0"></a><span data-ttu-id="0a052-165">ピボット テーブル ビューは、「0」としてすべての値を示しています</span><span class="sxs-lookup"><span data-stu-id="0a052-165">Pivot table view shows all values as “0”</span></span>  
 <span data-ttu-id="0a052-166">BAM ポータルを展開するときに、アクティビティの検索ページには、期待どおりの結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0a052-166">When you deploy the BAM portal, the Activity Search page displays expected results.</span></span> <span data-ttu-id="0a052-167">ただし、ピボット テーブルのビューには、すべての値が「0」として表示されます。</span><span class="sxs-lookup"><span data-stu-id="0a052-167">But, the Pivot table view displays all values as “0”.</span></span> <span data-ttu-id="0a052-168">次のエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0a052-168">The following error is displayed:</span></span>  
  
```  
Failed to get data.  If available, errors returned from the provider are listed below.  
* Safety settings on this machine prohibit accessing a data source on another domain.  
```  
  
 <span data-ttu-id="0a052-169">この問題を解決するには、ようゾーンにサイトを追加します。</span><span class="sxs-lookup"><span data-stu-id="0a052-169">To resolve this issue, add the site to the zone as follows:</span></span>  
  
1.  <span data-ttu-id="0a052-170">Internet Explorer のウィンドウで次のようにクリックします。**ツール**、 をクリックし、**インターネット オプション**します。</span><span class="sxs-lookup"><span data-stu-id="0a052-170">In the Internet Explorer window, click **Tools**, then click **Internet Options**.</span></span> <span data-ttu-id="0a052-171">をクリックして、**セキュリティ**、タブを選び、**信頼済みサイト**ゾーン。</span><span class="sxs-lookup"><span data-stu-id="0a052-171">Click the **Security** tab, and then select the **Trusted sites** zone.</span></span>  
  
2.  <span data-ttu-id="0a052-172">クリックして**レベルのカスタマイズ**ゾーンのセキュリティ レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="0a052-172">Click **Custom level** to set the security level for the zone.</span></span>  
  
3.  <span data-ttu-id="0a052-173">**設定**ページの**ドメイン間でデータ ソースにアクセス**オプションで、**プロンプト**。</span><span class="sxs-lookup"><span data-stu-id="0a052-173">On the **Settings** page, under the **Access data sources across domains** option, click **Prompt**.</span></span> <span data-ttu-id="0a052-174">コンポーネントは、このアクセス許可を必要とする場合を求められます。</span><span class="sxs-lookup"><span data-stu-id="0a052-174">You will be prompted when a component requires this permission.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a052-175">参照</span><span class="sxs-lookup"><span data-stu-id="0a052-175">See Also</span></span>  
 [<span data-ttu-id="0a052-176">ビジネス アクティビティの使用の監視</span><span class="sxs-lookup"><span data-stu-id="0a052-176">Using Business Activity Monitoring</span></span>](../core/using-business-activity-monitoring.md)