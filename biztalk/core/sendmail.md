---
title: SendMail |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SMTP adapters, examples
- examples, SMTP adapters
- SMTP adapters
ms.assetid: a0258619-b195-4c8a-8326-77add6e6f04d
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6cf0243eccb6a38dc121cfe06a60e30fa0c26c7
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974840"
---
# <a name="sendmail"></a><span data-ttu-id="34ea0-102">SendMail</span><span class="sxs-lookup"><span data-stu-id="34ea0-102">SendMail</span></span>
<span data-ttu-id="34ea0-103">SendMail サンプルは、簡易メール転送プロトコル (SMTP) アダプターを使用して、Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] オーケストレーションから電子メール メッセージを送信する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="34ea0-103">The SendMail sample demonstrates how you can use the Simple Mail Transfer Protocol (SMTP) adapter to send e-mail messages from within a Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration.</span></span> <span data-ttu-id="34ea0-104">電子メール メッセージの送信に使用される動的な情報は、プロパティの昇格機能を使用して XML メッセージから取得します。</span><span class="sxs-lookup"><span data-stu-id="34ea0-104">Dynamic information used to send the e-mail messages is retrieved from an XML message using property promotion functionality.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="34ea0-105">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="34ea0-105">What This Sample Does</span></span>  
 <span data-ttu-id="34ea0-106">このサンプルは、受信 XML 発注書 (PO) メッセージから、次の一連の手順を使用して昇格させたプロパティから取得した情報を使用して電子メール メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="34ea0-106">This sample sends an e-mail message using information obtained from properties promoted out of an incoming XML purchase order (PO) message, using the following sequence of steps:</span></span>  
  
1.  <span data-ttu-id="34ea0-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] オーケストレーションが、受信 XML PO メッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="34ea0-107">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration retrieves an input XML PO message.</span></span>  
  
2.  <span data-ttu-id="34ea0-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]オーケストレーションの昇格、 **PONumber**と**電子メール**プロパティ アクセスを後で簡単にします。</span><span class="sxs-lookup"><span data-stu-id="34ea0-108">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration promotes the **PONumber** and **Email** properties for easier access in the future.</span></span>  
  
3.  <span data-ttu-id="34ea0-109">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] オーケストレーションは、昇格されたプロパティの値を使用して、動的送信ポートの送信先アドレス、および電子メール メッセージの件名を設定します。</span><span class="sxs-lookup"><span data-stu-id="34ea0-109">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration uses the values of the promoted properties to set the destination address of the dynamic send port and to set the subject of the e-mail message.</span></span>  
  
4.  <span data-ttu-id="34ea0-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] オーケストレーションは、SMTP アダプターを使用して、構築された電子メール メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="34ea0-110">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration sends the constructed e-mail message through the SMTP adapter.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="34ea0-111">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="34ea0-111">Where to Find This Sample</span></span>  
 <span data-ttu-id="34ea0-112">\<*パスのサンプル*\>\AdaptersUsage\SendMail\\</span><span class="sxs-lookup"><span data-stu-id="34ea0-112">\<*Samples Path*\>\AdaptersUsage\SendMail\\</span></span>  
  
 <span data-ttu-id="34ea0-113">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="34ea0-113">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="34ea0-114">ファイル</span><span class="sxs-lookup"><span data-stu-id="34ea0-114">File(s)</span></span>|<span data-ttu-id="34ea0-115">Description</span><span class="sxs-lookup"><span data-stu-id="34ea0-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="34ea0-116">AssemblyInfo.cs、SendMail.btproj、SendMail.sln</span><span class="sxs-lookup"><span data-stu-id="34ea0-116">AssemblyInfo.cs, SendMail.btproj, SendMail.sln</span></span>|<span data-ttu-id="34ea0-117">このサンプルのプロジェクト ファイル、ソリューション ファイル、およびアセンブリ情報ファイルを提供します。</span><span class="sxs-lookup"><span data-stu-id="34ea0-117">Provides project, solution, and assembly information files for this sample.</span></span>|  
|<span data-ttu-id="34ea0-118">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="34ea0-118">Cleanup.bat</span></span>|<span data-ttu-id="34ea0-119">必要に応じて、アセンブリの展開の解除とグローバル アセンブリ キャッシュ (GAC) からのアセンブリの削除、送信および受信ポートの削除、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリの削除などを行います。</span><span class="sxs-lookup"><span data-stu-id="34ea0-119">Undeploys assemblies and removes them from the global assembly cache (GAC); removes send and receive ports; removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="34ea0-120">PropertySchema.xsd、PurchaseOrder.xsd</span><span class="sxs-lookup"><span data-stu-id="34ea0-120">PropertySchema.xsd, PurchaseOrder.xsd</span></span>|<span data-ttu-id="34ea0-121">昇格するプロパティのスキーマ、および XML PO メッセージのスキーマを提供します。</span><span class="sxs-lookup"><span data-stu-id="34ea0-121">Provides schemas for the properties that you want to promote, and for the XML PO message, respectively.</span></span>|  
|<span data-ttu-id="34ea0-122">ReceiveSend.odx</span><span class="sxs-lookup"><span data-stu-id="34ea0-122">ReceiveSend.odx</span></span>|<span data-ttu-id="34ea0-123">受信 XML PO メッセージを処理し、メッセージの情報に基づいて電子メール メッセージを送信する [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] オーケストレーションを提供します。</span><span class="sxs-lookup"><span data-stu-id="34ea0-123">Provides a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration that processes the incoming XML PO message and sends an e-mail message based on information in the message.</span></span>|  
|<span data-ttu-id="34ea0-124">SendMailInput.xml</span><span class="sxs-lookup"><span data-stu-id="34ea0-124">SendMailInput.xml</span></span>|<span data-ttu-id="34ea0-125">XML を使用して PO を指定したサンプル入力ファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="34ea0-125">Contains a sample input file with a PO specified using XML.</span></span>|  
|<span data-ttu-id="34ea0-126">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="34ea0-126">Setup.bat</span></span>|<span data-ttu-id="34ea0-127">このサンプルを作成および初期化します。</span><span class="sxs-lookup"><span data-stu-id="34ea0-127">Builds and initializes this sample.</span></span> <span data-ttu-id="34ea0-128">**注:** SDK サンプルについては、ファイルのほとんどのセットアップとは異なる機構を使用して、このセットアップ ファイルを作成し、ポートをバインドします。</span><span class="sxs-lookup"><span data-stu-id="34ea0-128">**Note:**  This setup file creates and binds ports, and so on, using a different mechanism than most of the setup files for the SDK samples.</span></span> <span data-ttu-id="34ea0-129">companion .xml ファイルは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="34ea0-129">It does not require a companion .xml file.</span></span>|  
  
### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="34ea0-130">このサンプルを作成および初期化するには</span><span class="sxs-lookup"><span data-stu-id="34ea0-130">To build and initialize this sample</span></span>  
  
1.  <span data-ttu-id="34ea0-131">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="34ea0-131">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="34ea0-132">\<*パスのサンプル*\>\AdaptersUsage\SendMail</span><span class="sxs-lookup"><span data-stu-id="34ea0-132">\<*Samples Path*\>\AdaptersUsage\SendMail</span></span>  
  
2.  <span data-ttu-id="34ea0-133">次の操作を実行する Setup.bat ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="34ea0-133">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="34ea0-134">このサンプルの次の入力フォルダを作成します。</span><span class="sxs-lookup"><span data-stu-id="34ea0-134">Creates the following input folder for this sample:</span></span>  
  
         <span data-ttu-id="34ea0-135">\<*パスのサンプル*\>\AdaptersUsage\SendMail\In</span><span class="sxs-lookup"><span data-stu-id="34ea0-135">\<*Samples Path*\>\AdaptersUsage\SendMail\In</span></span>  
  
    -   <span data-ttu-id="34ea0-136">コンパイル、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]このサンプルのプロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="34ea0-136">Compiles the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] project for this sample.</span></span>  
  
    -   <span data-ttu-id="34ea0-137">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] オーケストレーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="34ea0-137">Starts the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="34ea0-138">このサンプルを実行する前に、BizTalk がビルド プロセス中および初期化プロセス中にエラーを報告していないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="34ea0-138">You should confirm that BizTalk did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="34ea0-139">Setup.bat ファイルを実行せずに、このサンプルのプロジェクトを開いてビルドする場合は、最初に .NET Framework の厳密名ユーティリティ (sn.exe) を使用して、厳密な名前のキー ペアを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34ea0-139">If you choose to open and build the project in this sample without running the file Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name Utility (sn.exe).</span></span> <span data-ttu-id="34ea0-140">結果として得られるアセンブリに署名するのにには、このキー ペアを使用します。</span><span class="sxs-lookup"><span data-stu-id="34ea0-140">Use this key pair to sign the resulting assembly.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="34ea0-141">Setup.bat による変更を元に戻すには、Cleanup.bat を実行し、SendMail_1.0.0.0_Microsoft.Samples.BizTalk.SendMail で始まるすべての受信ポートと送信ポートを削除します。</span><span class="sxs-lookup"><span data-stu-id="34ea0-141">To undo changes made by Setup.bat, run Cleanup.bat and delete all receive and send ports prefixed with SendMail_1.0.0.0_Microsoft.Samples.BizTalk.SendMail.</span></span> <span data-ttu-id="34ea0-142">Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。</span><span class="sxs-lookup"><span data-stu-id="34ea0-142">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  
  
3.  <span data-ttu-id="34ea0-143">**BizTalk Server 管理コンソール**コンソールで、SendMail_1.0.0.0_Microsoft.Samples.BizTalk.SendMail で始まる受信ポートを検索します。</span><span class="sxs-lookup"><span data-stu-id="34ea0-143">In the **BizTalk Server Administration** console, locate the receive port prefixed by SendMail_1.0.0.0_Microsoft.Samples.BizTalk.SendMail.</span></span> <span data-ttu-id="34ea0-144">この受信ポートの受信場所を更新して、ファイル システムのディレクトリをポイントし、入力場所に使用します。</span><span class="sxs-lookup"><span data-stu-id="34ea0-144">Update the receive location for this receive port to point to a directory on your file system to use as the input location.</span></span>  
  
4.  <span data-ttu-id="34ea0-145">メモ帳などのプログラムを使用して SendMailInput.xml ファイルを変更できるように、**電子メール**要素は、このサンプルで生成された電子メール メッセージを受信する正当な電子メール アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="34ea0-145">Using a program such as Notepad, modify the file SendMailInput.xml so that the **Email** element specifies a legitimate e-mail address at which you want to receive the e-mail message generated by this sample.</span></span>  
  
5.  <span data-ttu-id="34ea0-146">をクリックして**開始**、 をポイント**プログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="34ea0-146">Click **Start**, point to **Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
6.  <span data-ttu-id="34ea0-147">**BizTalk Server 管理コンソール**コンソールで、BizTalk グループ ツリーを展開します。</span><span class="sxs-lookup"><span data-stu-id="34ea0-147">In the **BizTalk Server Administration** console, expand the BizTalk Group tree.</span></span>  
  
7.  <span data-ttu-id="34ea0-148">展開して、**プラットフォームの設定**左ペインのツリーです。</span><span class="sxs-lookup"><span data-stu-id="34ea0-148">Expand the **Platform Settings** tree in the left pane.</span></span>  
  
8.  <span data-ttu-id="34ea0-149">展開、**アダプター**フォルダーで、をクリックして、 **SMTP**ノード、および SMTP アダプターの右側のペインで行をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="34ea0-149">Expand the **Adapters** folder, click the **SMTP** node, and then double-click the SMTP adapter row in the right pane.</span></span>  
  
9. <span data-ttu-id="34ea0-150">**SMTP - アダプター ハンドラーのプロパティ**ダイアログ ボックスで、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="34ea0-150">In the **SMTP - Adapter Handler Properties** dialog box, click **Properties**.</span></span>  
  
10. <span data-ttu-id="34ea0-151">**SMTP トランスポートのプロパティ** ダイアログ ボックスで、**プロパティ** タブで、適切な値を指定して、 **SMTP サーバー名**と **(電子メールからアドレス)** プロパティ、およびクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="34ea0-151">In the **SMTP Transport Properties** dialog box, on the **Properties** tab, provide appropriate values for the **SMTP server name** and **From (e-mail address)** properties, and then click **OK**.</span></span>  
  
     <span data-ttu-id="34ea0-152">これらの値を使用して、この SMTP アダプタから送信するすべての電子メール メッセージの差出人の電子メール アドレスを構築します。</span><span class="sxs-lookup"><span data-stu-id="34ea0-152">These values will be used to construct the From e-mail address for any e-mail messages sent through this SMTP adapter.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="34ea0-153">SMTP サーバーで認証する必要がある場合は、差出人の電子メール アドレスが、認証に使用するアカウントと同じアカウントに所属していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34ea0-153">If you need to authenticate with your SMTP server, you must ensure that the From e-mail address belongs to the same account that you use for authentication.</span></span>  
  
11. <span data-ttu-id="34ea0-154">BizTalk サービス (BizTalkServerApplication) を停止してから再起動し、オーケストレーションがこれらの変更を採用するようにします。</span><span class="sxs-lookup"><span data-stu-id="34ea0-154">Stop and then restart the BizTalk service (BizTalkServerApplication) so that the orchestration will adopt these changes.</span></span>  
  
### <a name="to-run-this-sample"></a><span data-ttu-id="34ea0-155">このサンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="34ea0-155">To run this sample</span></span>  
  
1.  <span data-ttu-id="34ea0-156">変更した SendMailInput.xml ファイルを入力フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="34ea0-156">Put a copy of the modified file SendMailInput.xml into the input folder.</span></span>  
  
2.  <span data-ttu-id="34ea0-157">電子メール メッセージが、前の手順で指定した電子メール メッセージに届くことを確認します。</span><span class="sxs-lookup"><span data-stu-id="34ea0-157">Observe the arrival of an e-mail message to the e-mail address you specified in the previous procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34ea0-158">参照</span><span class="sxs-lookup"><span data-stu-id="34ea0-158">See Also</span></span>  
 [<span data-ttu-id="34ea0-159">アダプタ サンプル – 使用法</span><span class="sxs-lookup"><span data-stu-id="34ea0-159">Adapter Samples - Usage</span></span>](../core/adapter-samples-usage.md)