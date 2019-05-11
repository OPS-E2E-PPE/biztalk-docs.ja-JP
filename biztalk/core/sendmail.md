---
title: SendMail |Microsoft Docs
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
ms.openlocfilehash: 94e05df6001a8f34909c60292050bb784b59112a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399011"
---
# <a name="sendmail"></a><span data-ttu-id="5983b-102">SendMail</span><span class="sxs-lookup"><span data-stu-id="5983b-102">SendMail</span></span>
<span data-ttu-id="5983b-103">SendMail サンプルは、簡易メール転送プロトコル (SMTP) アダプターを使用して、microsoft から電子メール メッセージを送信する方法を示します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]オーケストレーションします。</span><span class="sxs-lookup"><span data-stu-id="5983b-103">The SendMail sample demonstrates how you can use the Simple Mail Transfer Protocol (SMTP) adapter to send e-mail messages from within a Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration.</span></span> <span data-ttu-id="5983b-104">電子メール メッセージの送信に使用される動的な情報は、プロパティの昇格機能を使用して XML メッセージから取得されます。</span><span class="sxs-lookup"><span data-stu-id="5983b-104">Dynamic information used to send the e-mail messages is retrieved from an XML message using property promotion functionality.</span></span>  

## <a name="what-this-sample-does"></a><span data-ttu-id="5983b-105">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="5983b-105">What This Sample Does</span></span>  
 <span data-ttu-id="5983b-106">このサンプルは、受信 XML 注文書 (PO) メッセージ、次の一連の手順を使用して外部から昇格させたプロパティから取得した情報を使用して電子メール メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="5983b-106">This sample sends an e-mail message using information obtained from properties promoted out of an incoming XML purchase order (PO) message, using the following sequence of steps:</span></span>  

1. <span data-ttu-id="5983b-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]オーケストレーションは、XML PO メッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="5983b-107">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration retrieves an input XML PO message.</span></span>  

2. <span data-ttu-id="5983b-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]オーケストレーションの昇格、 **PONumber**と**電子メール**プロパティは、将来簡単にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="5983b-108">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration promotes the **PONumber** and **Email** properties for easier access in the future.</span></span>  

3. <span data-ttu-id="5983b-109">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]動的送信ポートの送信先アドレスを設定して、電子メール メッセージの件名を設定するオーケストレーションは昇格されたプロパティの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="5983b-109">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration uses the values of the promoted properties to set the destination address of the dynamic send port and to set the subject of the e-mail message.</span></span>  

4. <span data-ttu-id="5983b-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]オーケストレーションは、SMTP アダプターで構築された電子メール メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="5983b-110">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration sends the constructed e-mail message through the SMTP adapter.</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="5983b-111">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="5983b-111">Where to Find This Sample</span></span>  
 <span data-ttu-id="5983b-112">\<*パスのサンプル*\>\AdaptersUsage\SendMail\\</span><span class="sxs-lookup"><span data-stu-id="5983b-112">\<*Samples Path*\>\AdaptersUsage\SendMail\\</span></span>  

 <span data-ttu-id="5983b-113">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="5983b-113">The following table shows the files in this sample and describes their purpose.</span></span>  


|                    <span data-ttu-id="5983b-114">ファイル</span><span class="sxs-lookup"><span data-stu-id="5983b-114">File(s)</span></span>                     |                                                                                                         <span data-ttu-id="5983b-115">説明</span><span class="sxs-lookup"><span data-stu-id="5983b-115">Description</span></span>                                                                                                         |
|------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="5983b-116">AssemblyInfo.cs, SendMail.btproj, SendMail.sln</span><span class="sxs-lookup"><span data-stu-id="5983b-116">AssemblyInfo.cs, SendMail.btproj, SendMail.sln</span></span> |                                                                         <span data-ttu-id="5983b-117">このサンプルのプロジェクト、ソリューション、およびアセンブリ情報ファイルを提供します。</span><span class="sxs-lookup"><span data-stu-id="5983b-117">Provides project, solution, and assembly information files for this sample.</span></span>                                                                         |
|                  <span data-ttu-id="5983b-118">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="5983b-118">Cleanup.bat</span></span>                   |              <span data-ttu-id="5983b-119">必要に応じて、アセンブリの展開の解除とグローバル アセンブリ キャッシュ (GAC) からのアセンブリの削除、送信および受信ポートの削除、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリの削除などを行います。</span><span class="sxs-lookup"><span data-stu-id="5983b-119">Undeploys assemblies and removes them from the global assembly cache (GAC); removes send and receive ports; removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>               |
|     <span data-ttu-id="5983b-120">PropertySchema.xsd、PurchaseOrder.xsd</span><span class="sxs-lookup"><span data-stu-id="5983b-120">PropertySchema.xsd, PurchaseOrder.xsd</span></span>      |                                                           <span data-ttu-id="5983b-121">スキーマの昇格するプロパティと提供 XML PO メッセージは、それぞれします。</span><span class="sxs-lookup"><span data-stu-id="5983b-121">Provides schemas for the properties that you want to promote, and for the XML PO message, respectively.</span></span>                                                           |
|                <span data-ttu-id="5983b-122">」の ReceiveSend.odx</span><span class="sxs-lookup"><span data-stu-id="5983b-122">ReceiveSend.odx</span></span>                 |   <span data-ttu-id="5983b-123">提供、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージ内の情報に基づいて、受信 XML PO メッセージを処理し、電子メール メッセージを送信するオーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="5983b-123">Provides a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration that processes the incoming XML PO message and sends an e-mail message based on information in the message.</span></span>   |
|               <span data-ttu-id="5983b-124">SendMailInput.xml</span><span class="sxs-lookup"><span data-stu-id="5983b-124">SendMailInput.xml</span></span>                |                                                                                 <span data-ttu-id="5983b-125">XML を使用して指定の PO では、サンプル入力ファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5983b-125">Contains a sample input file with a PO specified using XML.</span></span>                                                                                 |
|                   <span data-ttu-id="5983b-126">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="5983b-126">Setup.bat</span></span>                    | <span data-ttu-id="5983b-127">このサンプルを作成および初期化します。</span><span class="sxs-lookup"><span data-stu-id="5983b-127">Builds and initializes this sample.</span></span> <span data-ttu-id="5983b-128">**注:** このセットアップ ファイルが作成し、ポート、およびように、ほとんどの SDK サンプルのセットアップ ファイルよりも、別のメカニズムを使用してバインドします。</span><span class="sxs-lookup"><span data-stu-id="5983b-128">**Note:**  This setup file creates and binds ports, and so on, using a different mechanism than most of the setup files for the SDK samples.</span></span> <span data-ttu-id="5983b-129">Companion .xml ファイルは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="5983b-129">It does not require a companion .xml file.</span></span> |

### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="5983b-130">このサンプルを作成および初期化するには</span><span class="sxs-lookup"><span data-stu-id="5983b-130">To build and initialize this sample</span></span>  

1. <span data-ttu-id="5983b-131">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="5983b-131">In a command window, navigate to the following folder:</span></span>  

    <span data-ttu-id="5983b-132">\<*パスのサンプル*\>\AdaptersUsage\SendMail</span><span class="sxs-lookup"><span data-stu-id="5983b-132">\<*Samples Path*\>\AdaptersUsage\SendMail</span></span>  

2. <span data-ttu-id="5983b-133">ファイルは、次の操作を実行します。 Setup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="5983b-133">Run the file Setup.bat, which performs the following actions:</span></span>  

   - <span data-ttu-id="5983b-134">このサンプルの次の入力フォルダを作成します。</span><span class="sxs-lookup"><span data-stu-id="5983b-134">Creates the following input folder for this sample:</span></span>  

      <span data-ttu-id="5983b-135">\<*パスのサンプル*\>\AdaptersUsage\SendMail\In</span><span class="sxs-lookup"><span data-stu-id="5983b-135">\<*Samples Path*\>\AdaptersUsage\SendMail\In</span></span>  

   - <span data-ttu-id="5983b-136">コンパイル、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]このサンプルのプロジェクト。</span><span class="sxs-lookup"><span data-stu-id="5983b-136">Compiles the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] project for this sample.</span></span>  

   - <span data-ttu-id="5983b-137">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] オーケストレーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="5983b-137">Starts the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration.</span></span>  

     > [!NOTE]
     >  <span data-ttu-id="5983b-138">このサンプルを実行する前に、BizTalk がビルド プロセス中および初期化プロセス中にエラーを報告していないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="5983b-138">You should confirm that BizTalk did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  

     > [!NOTE]
     >  <span data-ttu-id="5983b-139">Setup.bat ファイルを実行せずに、このサンプルのプロジェクトを開いてビルドする場合は、最初に .NET Framework の厳密名ユーティリティ (sn.exe) を使用して、厳密な名前のキー ペアを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5983b-139">If you choose to open and build the project in this sample without running the file Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name Utility (sn.exe).</span></span> <span data-ttu-id="5983b-140">結果として得られるアセンブリに署名するのにには、このキー ペアを使用します。</span><span class="sxs-lookup"><span data-stu-id="5983b-140">Use this key pair to sign the resulting assembly.</span></span>  

     > [!NOTE]
     >  <span data-ttu-id="5983b-141">Setup.bat による変更を元に戻すには、Cleanup.bat とすべての受信し、送信ポート SendMail_1.0.0.0_Microsoft.Samples.BizTalk.SendMail で始まる削除を実行します。</span><span class="sxs-lookup"><span data-stu-id="5983b-141">To undo changes made by Setup.bat, run Cleanup.bat and delete all receive and send ports prefixed with SendMail_1.0.0.0_Microsoft.Samples.BizTalk.SendMail.</span></span> <span data-ttu-id="5983b-142">Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。</span><span class="sxs-lookup"><span data-stu-id="5983b-142">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  

3. <span data-ttu-id="5983b-143">**BizTalk Server 管理**コンソールで、SendMail_1.0.0.0_Microsoft.Samples.BizTalk.SendMail で始まる受信ポートを探します。</span><span class="sxs-lookup"><span data-stu-id="5983b-143">In the **BizTalk Server Administration** console, locate the receive port prefixed by SendMail_1.0.0.0_Microsoft.Samples.BizTalk.SendMail.</span></span> <span data-ttu-id="5983b-144">入力の場所として使用するファイル システム上のディレクトリをポイントするには、この受信ポートの受信場所を更新します。</span><span class="sxs-lookup"><span data-stu-id="5983b-144">Update the receive location for this receive port to point to a directory on your file system to use as the input location.</span></span>  

4. <span data-ttu-id="5983b-145">メモ帳などのプログラムを使用して変更した SendMailInput.xml ファイルを変更できるように、**電子メール**要素は、このサンプルで生成された電子メール メッセージを受信する正当な電子メール アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="5983b-145">Using a program such as Notepad, modify the file SendMailInput.xml so that the **Email** element specifies a legitimate e-mail address at which you want to receive the e-mail message generated by this sample.</span></span>  

5. <span data-ttu-id="5983b-146">クリックして**開始**、 をポイント**プログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="5983b-146">Click **Start**, point to **Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  

6. <span data-ttu-id="5983b-147">**BizTalk Server 管理**コンソールで、BizTalk グループのツリーを展開します。</span><span class="sxs-lookup"><span data-stu-id="5983b-147">In the **BizTalk Server Administration** console, expand the BizTalk Group tree.</span></span>  

7. <span data-ttu-id="5983b-148">展開、**プラットフォームの設定**左側のウィンドウのツリーです。</span><span class="sxs-lookup"><span data-stu-id="5983b-148">Expand the **Platform Settings** tree in the left pane.</span></span>  

8. <span data-ttu-id="5983b-149">展開、**アダプター**フォルダー、をクリックして、 **SMTP**ノード、および SMTP アダプターの右側のウィンドウで行をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5983b-149">Expand the **Adapters** folder, click the **SMTP** node, and then double-click the SMTP adapter row in the right pane.</span></span>  

9. <span data-ttu-id="5983b-150">**SMTP - アダプター ハンドラーのプロパティ**ダイアログ ボックスで、をクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="5983b-150">In the **SMTP - Adapter Handler Properties** dialog box, click **Properties**.</span></span>  

10. <span data-ttu-id="5983b-151">**SMTP トランスポートのプロパティ** ダイアログ ボックスで、**プロパティ** タブで、適切な値を指定、 **SMTP サーバー名**と **(電子メールからアドレス)** プロパティ、およびクリック**OK**します。</span><span class="sxs-lookup"><span data-stu-id="5983b-151">In the **SMTP Transport Properties** dialog box, on the **Properties** tab, provide appropriate values for the **SMTP server name** and **From (e-mail address)** properties, and then click **OK**.</span></span>  

     <span data-ttu-id="5983b-152">この SMTP アダプタから送信された電子メール メッセージの差出人の電子メール アドレスを作成するこれらの値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="5983b-152">These values will be used to construct the From e-mail address for any e-mail messages sent through this SMTP adapter.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="5983b-153">SMTP サーバーで認証する必要がある場合は、差出人の電子メール アドレスは、認証に使用するのと同じアカウントに属していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5983b-153">If you need to authenticate with your SMTP server, you must ensure that the From e-mail address belongs to the same account that you use for authentication.</span></span>  

11. <span data-ttu-id="5983b-154">停止し、オーケストレーションがこれらの変更を採用できるように、BizTalk サービス (BizTalkServerApplication) を再起動します。</span><span class="sxs-lookup"><span data-stu-id="5983b-154">Stop and then restart the BizTalk service (BizTalkServerApplication) so that the orchestration will adopt these changes.</span></span>  

### <a name="to-run-this-sample"></a><span data-ttu-id="5983b-155">このサンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="5983b-155">To run this sample</span></span>  

1.  <span data-ttu-id="5983b-156">入力フォルダーに変更した SendMailInput.xml ファイルのコピーを格納します。</span><span class="sxs-lookup"><span data-stu-id="5983b-156">Put a copy of the modified file SendMailInput.xml into the input folder.</span></span>  

2.  <span data-ttu-id="5983b-157">前の手順で指定した電子メール アドレスに電子メール メッセージの到着を確認します。</span><span class="sxs-lookup"><span data-stu-id="5983b-157">Observe the arrival of an e-mail message to the e-mail address you specified in the previous procedure.</span></span>  

## <a name="see-also"></a><span data-ttu-id="5983b-158">参照</span><span class="sxs-lookup"><span data-stu-id="5983b-158">See Also</span></span>  
 [<span data-ttu-id="5983b-159">アダプタ サンプル – 使用法</span><span class="sxs-lookup"><span data-stu-id="5983b-159">Adapter Samples - Usage</span></span>](../core/adapter-samples-usage.md)