---
title: "BAM のトラブルシューティング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e63299a8-5c74-4337-ba20-3213e0c6ea1f
caps.latest.revision: 
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12cd08ae9bee686946c8db14039504411506035f
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2018
---
# <a name="troubleshooting-bam"></a><span data-ttu-id="2d16b-102">BAM のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="2d16b-102">Troubleshooting BAM</span></span>
<span data-ttu-id="2d16b-103">このトピックでは、ビジネス アクティビティ監視 (BAM) の使用時に生じる問題のトラブルシューティングに役立つ情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="2d16b-103">This topic provides information to help you troubleshoot problems you might encounter when using Business Activity Monitoring (BAM).</span></span>  
  
## <a name="bam-deployment-failed"></a><span data-ttu-id="2d16b-104">BAM を展開できない</span><span class="sxs-lookup"><span data-stu-id="2d16b-104">BAM deployment failed</span></span>  
 <span data-ttu-id="2d16b-105">SQL Server Analysis Services が使用できないときにリアルタイム集計 (RTA) を含む BAM 定義を展開しようとすると、Bm.exe コマンドで次のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2d16b-105">If you attempt to deploy a BAM definition that includes a real-time aggregation (RTA) when SQL Server Analysis Services is not available, the Bm.exe command will display the following message:</span></span>  
  
 <span data-ttu-id="2d16b-106">エラー: BAM の展開に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="2d16b-106">ERROR: BAM deployment failed.</span></span> <span data-ttu-id="2d16b-107">接続できません。</span><span class="sxs-lookup"><span data-stu-id="2d16b-107">A connection cannot be made.</span></span> <span data-ttu-id="2d16b-108">サーバーが実行中であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="2d16b-108">Ensure that the server is running.</span></span> <span data-ttu-id="2d16b-109">対象のコンピューターによって拒否されたため接続は行われません *\<IP アドレス\>*です。</span><span class="sxs-lookup"><span data-stu-id="2d16b-109">No connection could be made because the target machine actively refused it *\<IP address\>*.</span></span>  
  
 <span data-ttu-id="2d16b-110">このエラーは、SQL Server Analysis Services がインストールされ構成済みであり、RTA を含む BAM 定義を展開するために実行されている必要があるために発生します。</span><span class="sxs-lookup"><span data-stu-id="2d16b-110">This occurs because SQL Server Analysis Services must have been installed and configured, and must be running in order to deploy a BAM definition that includes an RTA.</span></span>  
  
## <a name="cannot-refresh-the-live-data-workbook"></a><span data-ttu-id="2d16b-111">ライブ データ ブックを更新できない</span><span class="sxs-lookup"><span data-stu-id="2d16b-111">Cannot refresh the live data workbook</span></span>  
 <span data-ttu-id="2d16b-112">ライブ データ ブックのデータを更新しようとすると、Microsoft Office Excel で次のエラーが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="2d16b-112">When you try to refresh the data in a live data workbook, Microsoft Office Excel might display the following error:</span></span>  
  
 `XML for Analysis parser: The CurrentCatalog XML/A property was not specified.`  
  
 <span data-ttu-id="2d16b-113">このエラーは、BAM アドインが Excel に追加されていないために発生します。</span><span class="sxs-lookup"><span data-stu-id="2d16b-113">This occurs because the BAM add-in has not been added to Excel.</span></span>  
  
#### <a name="add-the-bam-add-in-to-excel"></a><span data-ttu-id="2d16b-114">Excel に BAM アドインを追加します。</span><span class="sxs-lookup"><span data-stu-id="2d16b-114">Add the BAM add-in to Excel</span></span>  
  
1.  <span data-ttu-id="2d16b-115">をクリックして **開始**, 、 をポイント **すべてのプログラム**, 、 をポイント **Microsoft Office**, 、 をクリックし、 **Microsoft Office Excel**します。</span><span class="sxs-lookup"><span data-stu-id="2d16b-115">Click **Start**, point to **All Programs**, point to **Microsoft Office**, and then click **Microsoft Office Excel**.</span></span>  
  
2.  <span data-ttu-id="2d16b-116">クリックして、 **Microsoft Office ボタン**, 、 をクリックし、 **Excel のオプション**します。</span><span class="sxs-lookup"><span data-stu-id="2d16b-116">Click the **Microsoft Office Button**, and then click **Excel Options**.</span></span>  
  
3.  <span data-ttu-id="2d16b-117">**Excel のオプション** ダイアログ ボックスで、をクリックして **アドイン**します。</span><span class="sxs-lookup"><span data-stu-id="2d16b-117">In the **Excel Options** dialog box, click **Add-Ins**.</span></span>  
  
4.  <span data-ttu-id="2d16b-118">**アドイン**  ウィンドウで、をクリックして **移動**します。</span><span class="sxs-lookup"><span data-stu-id="2d16b-118">In the **Add-Ins** pane, click **Go**.</span></span>  
  
5.  <span data-ttu-id="2d16b-119">**アドイン** ダイアログ ボックスで、 **ビジネス アクティビティ監視** チェック ボックスをオンにし **[ok]**します。</span><span class="sxs-lookup"><span data-stu-id="2d16b-119">In the **Add-Ins** dialog box, select the **Business Activity Monitoring** check box, and then click **OK**.</span></span>  
  
     <span data-ttu-id="2d16b-120">![追加 (& a) #45; アドイン ダイアログ ボックス](../core/media/addins.gif "AddIns")</span><span class="sxs-lookup"><span data-stu-id="2d16b-120">![Add&#45;Ins dialog box](../core/media/addins.gif "AddIns")</span></span>  
  
## <a name="errorobject-library-invalid-or-contains-references-to-object-definitions-that-could-not-be-found-with-bam-excel-add-in-in-office"></a><span data-ttu-id="2d16b-121">Office の BAM Excel アドインで「オブジェクト ライブラリが無効、または見つからないオブジェクト定義への参照が含まれています」というエラーが表示される</span><span class="sxs-lookup"><span data-stu-id="2d16b-121">Error:"Object library invalid or contains references to object definitions that could not be found" with BAM Excel Add-In in Office</span></span>  
 <span data-ttu-id="2d16b-122">Microsoft Excel をアップグレードした後に BAM Excel アドインを使用しようとすると、このエラーが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="2d16b-122">You may receive this error, when you try use the BAM Excel Add-In after you upgrade Microsoft Excel.</span></span>  
  
 <span data-ttu-id="2d16b-123">**解決方法:** キャッシュされている .exd ファイルを次のディレクトリから削除する必要がある BAM アドインには、ActiveX コントロールを使用するため。</span><span class="sxs-lookup"><span data-stu-id="2d16b-123">**Resolution:** Since the BAM Add-In uses ActiveX controls, you have to delete any cached .exd files from the following directories:</span></span>  
  
-   <span data-ttu-id="2d16b-124">C:\Documents and Settings\\< ユーザー名\>\Application Data\Microsoft\Forms</span><span class="sxs-lookup"><span data-stu-id="2d16b-124">C:\Documents and Settings\\<username\>\Application Data\Microsoft\Forms</span></span>  
  
-   <span data-ttu-id="2d16b-125">C:\Documents and Settings\\< ユーザー名\>\AppData\Local\Temp\VBE</span><span class="sxs-lookup"><span data-stu-id="2d16b-125">C:\Documents and Settings\\<username\>\AppData\Local\Temp\VBE</span></span>  
  
## <a name="bam-portal-cannot-connect"></a><span data-ttu-id="2d16b-126">BAM ポータルに接続できない</span><span class="sxs-lookup"><span data-stu-id="2d16b-126">BAM portal cannot connect</span></span>  
<span data-ttu-id="2d16b-127">BAM ポータルを管理者として実行します。</span><span class="sxs-lookup"><span data-stu-id="2d16b-127">Run the BAM portal as an administrator.</span></span>  
  
#### <a name="run-the-bam-portal"></a><span data-ttu-id="2d16b-128">BAM ポータルを実行します。</span><span class="sxs-lookup"><span data-stu-id="2d16b-128">Run the BAM portal</span></span>
  
1.  <span data-ttu-id="2d16b-129">をクリックして **開始**, 、 をポイント **すべてのプログラム**, を右クリックして **Internet Explorer**, 、 をクリックし、 **管理者として実行**します。</span><span class="sxs-lookup"><span data-stu-id="2d16b-129">Click **Start**, point to **All Programs**, right-click **Internet Explorer**, and then click **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="2d16b-130">**ユーザー アカウント制御** ダイアログ ボックスで、をクリックして **続行**します。</span><span class="sxs-lookup"><span data-stu-id="2d16b-130">In the **User Account Control** dialog box, click **Continue**.</span></span>  
  
3.  <span data-ttu-id="2d16b-131">Internet Explorer のアドレス バーで、次のように入力します。`http://<server>/BAM`ここで、 *\<サーバー\>*  、BAM ポータルを実行しているコンピューターの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="2d16b-131">In the Internet Explorer address bar, type `http://<server>/BAM`, where *\<server\>* is the name of the computer that is running the BAM portal.</span></span>  
  
## <a name="bam-portal-does-not-work-if-invalid-users-are-granted-permissions"></a><span data-ttu-id="2d16b-132">無効なユーザーにアクセス許可が付与されていると BAM ポータルは機能しない</span><span class="sxs-lookup"><span data-stu-id="2d16b-132">BAM portal does not work if invalid users are granted permissions</span></span>  
 <span data-ttu-id="2d16b-133">BAM の表示アクセスが許可されている AD ユーザーの 1 人が AD から削除されると、BAM ポータルは、DBO を除き、どのユーザーに対しても正しく読み込まれなくなります。</span><span class="sxs-lookup"><span data-stu-id="2d16b-133">If an AD user who has the BAM view permissions is removed from the AD, then the BAM portal does not load properly for any user (except DBO).</span></span>  
  
 <span data-ttu-id="2d16b-134">この問題を解決するには、無効なユーザーを、対応する bam_{ビュー名}view セキュリティ ロールから削除してください。</span><span class="sxs-lookup"><span data-stu-id="2d16b-134">To resolve this issue, remove the invalid user from the corresponding bam_{viewname}view security role.</span></span>  
  
## <a name="cannot-export-or-import-a-bam-definition-to-localhost"></a><span data-ttu-id="2d16b-135">BAM 定義をローカルホストにエクスポートまたはインポートできない</span><span class="sxs-lookup"><span data-stu-id="2d16b-135">Cannot export or import a BAM definition to localhost</span></span>  
 <span data-ttu-id="2d16b-136">BAM 定義を XML としてエクスポートする際に、ローカルホストにエクスポートしようとすると、次のエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2d16b-136">When you export a BAM definition as XML, you will see the following error message if you try to export to localhost:</span></span>  
  
 `The system cannot find the path specified.`  
  
 <span data-ttu-id="2d16b-137">BAM 定義のローカルホストへのエクスポートはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="2d16b-137">Exporting a BAM definition to localhost is not supported.</span></span> <span data-ttu-id="2d16b-138">同様に、BAM 定義のローカルホストからのインポートもサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="2d16b-138">Similarly, importing a BAM definition from localhost is not supported.</span></span>  
  
## <a name="alerts-do-not-work-after-upgrading-sql-server-editions"></a><span data-ttu-id="2d16b-139">SQL Server エディションのアップグレード後に警告が実行されない</span><span class="sxs-lookup"><span data-stu-id="2d16b-139">Alerts do not work after upgrading SQL Server editions</span></span>  
 <span data-ttu-id="2d16b-140">(たとえば、Enterprise Edition を Standard Edition) から別のエディションへの 1 つのエディションの SQL Server からアップグレードした後は、BAM 警告は再起動されません。</span><span class="sxs-lookup"><span data-stu-id="2d16b-140">If you have upgraded from one edition of SQL Server to another edition (for example, from Standard Edition to Enterprise Edition), BAM alerts will not restart.</span></span> <span data-ttu-id="2d16b-141">この問題を解決するには、BAM 警告を削除し、それらを再作成または SQL Server Notification Service をアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="2d16b-141">To fix this problem, either delete the BAM alerts and re-create them, or upgrade the SQL Server Notification Service.</span></span>  
  
#### <a name="upgrade-the-sql-server-notification-service"></a><span data-ttu-id="2d16b-142">SQL Server Notification Service をアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="2d16b-142">Upgrade the SQL Server Notification Service</span></span>  
  
1.  <span data-ttu-id="2d16b-143">をクリックして **開始**, 、 をクリックして **すべてのプログラム**, 、 をクリックして **Microsoft SQL Server 2005**, 、 をクリックし、 **通知サービスのコマンド プロンプト**します。</span><span class="sxs-lookup"><span data-stu-id="2d16b-143">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2005**, and then click **Notification Service Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="2d16b-144">コマンド プロンプトで次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="2d16b-144">Type the following command at the command prompt:</span></span>  
  
     `nscontrol.exe upgrade -name <instanceName>`  
  
## <a name="objectdisposedexception-exception"></a><span data-ttu-id="2d16b-145">ObjectDisposedException 例外</span><span class="sxs-lookup"><span data-stu-id="2d16b-145">ObjectDisposedException Exception</span></span>  
 <span data-ttu-id="2d16b-146">アプリケーションが BAM WF 3.5 インターセプターを使用している場合、次のエラー メッセージが表示される場合があります: **System.ObjectDisposedException: 破棄されたオブジェクトにアクセスできません**します。</span><span class="sxs-lookup"><span data-stu-id="2d16b-146">If your application is using BAM WF 3.5 interceptor, you may receive the following error message: **System.ObjectDisposedException: Cannot access a disposed object**.</span></span> <span data-ttu-id="2d16b-147">このエラー メッセージの詳細については、次を参照してください。 [ObjectDisposedException 例外](https://support.microsoft.com/help/960754)です。</span><span class="sxs-lookup"><span data-stu-id="2d16b-147">For more information about this error message, see [ObjectDisposedException Exception](https://support.microsoft.com/help/960754).</span></span> 

<span data-ttu-id="2d16b-148">この問題を解決するには、インストール、[修正プログラム 960754](https://support.microsoft.com/help/960754)です。</span><span class="sxs-lookup"><span data-stu-id="2d16b-148">To resolve this issue, install the [hotfix 960754](https://support.microsoft.com/help/960754).</span></span> 
  
## <a name="workbook-has-lost-its-vba-project-activex-controls-and-other-programmability-related-features"></a><span data-ttu-id="2d16b-149">ブックにある VBA プロジェクト、ActiveX コントロール、およびその他のプログラミング関連の機能が失われている</span><span class="sxs-lookup"><span data-stu-id="2d16b-149">Workbook has lost its VBA project, ActiveX controls and other programmability-related features</span></span>  
 <span data-ttu-id="2d16b-150">Microsoft Excel で BAM.xla を使用しようとすると、次のエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2d16b-150">When attempting to use BAM.xla in Microsoft Excel, you may get the following error:</span></span>  
  
 `This workbook has lost its VBA project, ActiveX controls and any other programmability-related features.`  
  
 <span data-ttu-id="2d16b-151">この問題を解決するには、インストール、 **アプリケーション用の Visual Basic** オプションで  **Office 共有機能** Microsoft Office とします。</span><span class="sxs-lookup"><span data-stu-id="2d16b-151">To resolve this issue, install the **Visual Basic for Applications** option under **Office Shared Features** with Microsoft Office.</span></span>  
  
## <a name="pivot-table-fails-to-get-the-data"></a><span data-ttu-id="2d16b-152">ピボットテーブルのデータ取得に失敗する</span><span class="sxs-lookup"><span data-stu-id="2d16b-152">Pivot table fails to get the data</span></span>  
 <span data-ttu-id="2d16b-153">BAM データベースへのアクセス権がユーザーに付与されており、展開されるビューに対するロールとアクセス許可もこのユーザーに付与されているとします。</span><span class="sxs-lookup"><span data-stu-id="2d16b-153">You have permissions to access BAM databases, and also role and permissions on the views which are deployed.</span></span> <span data-ttu-id="2d16b-154">[アクティビティの検索] ページの動作は期待どおりであり、ユーザーはデータを見ることができます。</span><span class="sxs-lookup"><span data-stu-id="2d16b-154">The Activity Search page works as expected and you can see the data.</span></span> <span data-ttu-id="2d16b-155">ただし、ピボットテーブルには次のエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2d16b-155">But, in the Pivot table, the following error is displayed:</span></span>  
  
```  
Failed to get data.  If available, errors returned from the provider are listed below.  
* The following system error occurred:  No connection could be made because the target machine actively refused it.  
```  
  
 <span data-ttu-id="2d16b-156">この問題を解決するには、次の手順に従って対応する DNS 設定を追加してください。</span><span class="sxs-lookup"><span data-stu-id="2d16b-156">To resolve this issue, add the respective DNS settings as follows:</span></span>  
  
1.  <span data-ttu-id="2d16b-157">をクリックして **開始** にして **コントロール パネルの** します。</span><span class="sxs-lookup"><span data-stu-id="2d16b-157">Click **Start** and go to **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="2d16b-158">クリックして **ネットワークとインターネット**  をクリックし、 **ネットワーク接続**します。</span><span class="sxs-lookup"><span data-stu-id="2d16b-158">Click **Network and Internet** and then click **Network Connections**.</span></span>  
  
3.  <span data-ttu-id="2d16b-159">(ローカル エリア接続) のようなネットワーク接続を右クリックし、選択 **プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="2d16b-159">Right-click on the network connection (like Local Area Connection), and select **Properties**.</span></span>  
  
4.  <span data-ttu-id="2d16b-160">**Local Area Connection**  ページで、 **インターネット プロトコル バージョン 4 (Tcp/ipv4)**, 、 をクリック **プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="2d16b-160">On the **Local Area Connection** page, select **Internet Protocol Version 4 (TCP/IPv4)**, and click **Properties**.</span></span>  
  
5.  <span data-ttu-id="2d16b-161">**[詳細設定]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2d16b-161">Click **Advanced**.</span></span> <span data-ttu-id="2d16b-162">**TCP/IP 詳細設定** ページで、クリックして、 **DNS**  タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2d16b-162">On the **Advance TCP/IP Settings** page, click the **DNS** tab.</span></span>  
  
6.  <span data-ttu-id="2d16b-163">選択 **これらの DNS サフィックスを追加する** し、必要な DNS サフィックスを追加します。</span><span class="sxs-lookup"><span data-stu-id="2d16b-163">Select **Append these DNS suffixes** and then add the required DNS suffixes.</span></span>  
  
7.  <span data-ttu-id="2d16b-164">をクリックして **OK** し、すべての開いているウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="2d16b-164">Click **OK** and close all the open windows.</span></span>  
  
## <a name="pivot-table-view-shows-all-values-as-0"></a><span data-ttu-id="2d16b-165">ピボットテーブルのすべての値が "0" と表示される</span><span class="sxs-lookup"><span data-stu-id="2d16b-165">Pivot table view shows all values as “0”</span></span>  
 <span data-ttu-id="2d16b-166">BAM ポータルを展開したときに、[アクティビティの検索] ページには期待したとおりの結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2d16b-166">When you deploy the BAM portal, the Activity Search page displays expected results.</span></span> <span data-ttu-id="2d16b-167">ただし、ピボットテーブル ビューの値はすべて "0" と表示されます。</span><span class="sxs-lookup"><span data-stu-id="2d16b-167">But, the Pivot table view displays all values as “0”.</span></span> <span data-ttu-id="2d16b-168">次のエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2d16b-168">The following error is displayed:</span></span>  
  
```  
Failed to get data.  If available, errors returned from the provider are listed below.  
* Safety settings on this machine prohibit accessing a data source on another domain.  
```  
  
 <span data-ttu-id="2d16b-169">この問題を解決するには、次の手順に従ってサイトをゾーンに追加してください。</span><span class="sxs-lookup"><span data-stu-id="2d16b-169">To resolve this issue, add the site to the zone as follows:</span></span>  
  
1.  <span data-ttu-id="2d16b-170">Internet Explorer ウィンドウで  **ツール**, 、クリックして **インターネット オプション**します。</span><span class="sxs-lookup"><span data-stu-id="2d16b-170">In the Internet Explorer window, click **Tools**, then click **Internet Options**.</span></span> <span data-ttu-id="2d16b-171">クリックして、 **セキュリティ** タブをクリックし、選択、 **信頼済みサイト** ゾーンです。</span><span class="sxs-lookup"><span data-stu-id="2d16b-171">Click the **Security** tab, and then select the **Trusted sites** zone.</span></span>  
  
2.  <span data-ttu-id="2d16b-172">クリックして **レベルのカスタマイズ** 、ゾーンのセキュリティ レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="2d16b-172">Click **Custom level** to set the security level for the zone.</span></span>  
  
3.  <span data-ttu-id="2d16b-173">**設定**  ページで、、 **ドメイン間でデータ ソースにアクセス** オプションで、 **プロンプト**します。</span><span class="sxs-lookup"><span data-stu-id="2d16b-173">On the **Settings** page, under the **Access data sources across domains** option, click **Prompt**.</span></span> <span data-ttu-id="2d16b-174">コンポーネントは、このアクセス許可を必要とする場合を求められます。</span><span class="sxs-lookup"><span data-stu-id="2d16b-174">You will be prompted when a component requires this permission.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d16b-175">参照</span><span class="sxs-lookup"><span data-stu-id="2d16b-175">See Also</span></span>  
 [<span data-ttu-id="2d16b-176">ビジネス アクティビティの使用の監視</span><span class="sxs-lookup"><span data-stu-id="2d16b-176">Using Business Activity Monitoring</span></span>](../core/using-business-activity-monitoring.md)