---
title: HTTPRequestResponse |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP adapters, examples
- examples, HTTP adapters
ms.assetid: 81c66f61-d86c-49cf-8d24-21c67c68bc5a
caps.latest.revision: 35
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ecea06f7637d7fee46593d412f1570d26b7eaeb1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019527"
---
# <a name="httprequestresponse"></a><span data-ttu-id="3b0df-102">HTTPRequestResponse</span><span class="sxs-lookup"><span data-stu-id="3b0df-102">HTTPRequestResponse</span></span>
<span data-ttu-id="3b0df-103">HTTPRequestResponse サンプルは、Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Internet Server API (ISAPI) フィルターを使用して ASP.NET アプリケーションと [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] オーケストレーションの通信を行う方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3b0df-103">The HTTPRequestResponse sample demonstrates how to use the Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Internet Server Application Programming Interface (ISAPI) filter to allow an ASP.NET application to communicate with a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration.</span></span>  

## <a name="what-this-sample-does"></a><span data-ttu-id="3b0df-104">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="3b0df-104">What This Sample Does</span></span>  
 <span data-ttu-id="3b0df-105">このサンプルでは、ASP.NET アプリケーションは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ISAPI フィルターに要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="3b0df-105">In this sample, the ASP.NET application submits a request to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ISAPI filter.</span></span> <span data-ttu-id="3b0df-106">オーケストレーションは、このメッセージを受信し、同期応答を使用して ASP.NET アプリケーションにメッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="3b0df-106">The orchestration then consumes this message and returns it to the ASP.NET application using a synchronous response.</span></span> <span data-ttu-id="3b0df-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ISAPI フィルターを使用することにより、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] オーケストレーションと ASP.NET アプリケーションの統合を実現できます。</span><span class="sxs-lookup"><span data-stu-id="3b0df-107">You achieve the integration between the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration and the ASP.NET application by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ISAPI filter.</span></span>  

 <span data-ttu-id="3b0df-108">このサンプルでは、以下の手順を使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] と ASP.NET アプリケーションの間で、注文書 (PO) および PO の受信確認メッセージを交換します。</span><span class="sxs-lookup"><span data-stu-id="3b0df-108">In this sample, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and an ASP.NET application exchange purchase order (PO) and PO acknowledgement messages using the following sequence of steps:</span></span>  

1. <span data-ttu-id="3b0df-109">ASP.NET アプリケーションが HTTP 要求を使用して、XML PO メッセージを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に送信します。</span><span class="sxs-lookup"><span data-stu-id="3b0df-109">An ASP.NET application, using an HTTP request, submits an XML PO message to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  

2. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="3b0df-110"> は XML PO メッセージを受け取り、XML PO 受信確認メッセージを構築します。その後、そのメッセージを HTTP 応答で ASP.NET アプリケーションに返します。</span><span class="sxs-lookup"><span data-stu-id="3b0df-110"> receives the XML PO message and constructs an XML PO acknowledgement message, and then sends that message back to the ASP.NET application in the HTTP response.</span></span>  

   <span data-ttu-id="3b0df-111">ASP.NET アプリケーションは XML PO 受信確認応答を受け取り、応答から抽出されたステータス情報で Web フォームを更新します。</span><span class="sxs-lookup"><span data-stu-id="3b0df-111">The ASP.NET application receives the XML PO acknowledgement response and refreshes the Web form with status information extracted from the response.</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="3b0df-112">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="3b0df-112">Where to Find This Sample</span></span>  
 <span data-ttu-id="3b0df-113">*\<パスのサンプル\>* \AdaptersUsage\HTTPRequestResponse\\</span><span class="sxs-lookup"><span data-stu-id="3b0df-113">*\<Samples Path\>* \AdaptersUsage\HTTPRequestResponse\\</span></span>  

 <span data-ttu-id="3b0df-114">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="3b0df-114">The following table shows the files in this sample and describes their purpose.</span></span>  


|                                                                                                     <span data-ttu-id="3b0df-115">ファイル</span><span class="sxs-lookup"><span data-stu-id="3b0df-115">File(s)</span></span>                                                                                                      |                                                                                             <span data-ttu-id="3b0df-116">説明</span><span class="sxs-lookup"><span data-stu-id="3b0df-116">Description</span></span>                                                                                             |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                                                                   <span data-ttu-id="3b0df-117">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="3b0df-117">Cleanup.bat</span></span>                                                                                                    |  <span data-ttu-id="3b0df-118">必要に応じて、アセンブリの展開の解除とグローバル アセンブリ キャッシュ (GAC) からのアセンブリの削除、送信および受信ポートの削除、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリの削除などを行います。</span><span class="sxs-lookup"><span data-stu-id="3b0df-118">Undeploys assemblies and removes them from the global assembly cache (GAC); removes send and receive ports; removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>   |
|                                                                               <span data-ttu-id="3b0df-119">HTTPRequestResponse.btproj、HTTPRequestResponse.sln</span><span class="sxs-lookup"><span data-stu-id="3b0df-119">HTTPRequestResponse.btproj, HTTPRequestResponse.sln</span></span>                                                                                |                            <span data-ttu-id="3b0df-120">HTTP 要求の受信、PO メッセージの処理、および応答の発行を行う BizTalk プロジェクトのプロジェクト ファイルおよびソース ファイルを提供します。</span><span class="sxs-lookup"><span data-stu-id="3b0df-120">Provides project and source files for the BizTalk project that receives the HTTP request, processes the PO message, and issues the response.</span></span>                             |
|                                                                                          <span data-ttu-id="3b0df-121">HTTPRequestResponseBinding.xml</span><span class="sxs-lookup"><span data-stu-id="3b0df-121">HTTPRequestResponseBinding.xml</span></span>                                                                                          |                                                                           <span data-ttu-id="3b0df-122">ポートのバインドなど、自動化されたセットアップを提供します。</span><span class="sxs-lookup"><span data-stu-id="3b0df-122">Provides automated setup such as port binding.</span></span>                                                                            |
|                                                                                             <span data-ttu-id="3b0df-123">POAck.xsd、POSchema.xsd</span><span class="sxs-lookup"><span data-stu-id="3b0df-123">POAck.xsd, POSchema.xsd</span></span>                                                                                              |                                                            <span data-ttu-id="3b0df-124">PO 受信確認および PO .xml ファイルのスキーマをそれぞれ提供します。</span><span class="sxs-lookup"><span data-stu-id="3b0df-124">Provides schemas for the PO acknowledgement and PO .xml files, respectively.</span></span>                                                             |
|                                                                                            <span data-ttu-id="3b0df-125">POReceiveOrchestration.odx</span><span class="sxs-lookup"><span data-stu-id="3b0df-125">POReceiveOrchestration.odx</span></span>                                                                                            |         <span data-ttu-id="3b0df-126">PO の受信、PO の処理、および PO 受信確認を行う [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] オーケストレーションを提供します。</span><span class="sxs-lookup"><span data-stu-id="3b0df-126">Provides a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration that receives the PO, processes it, and issues the PO acknowledgement.</span></span>          |
|                                                                                                    <span data-ttu-id="3b0df-127">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="3b0df-127">Setup.bat</span></span>                                                                                                     |                                                                                 <span data-ttu-id="3b0df-128">このサンプルを作成および初期化します。</span><span class="sxs-lookup"><span data-stu-id="3b0df-128">Builds and initializes this sample.</span></span>                                                                                 |
| <span data-ttu-id="3b0df-129">\RequestResponse フォルダー内</span><span class="sxs-lookup"><span data-stu-id="3b0df-129">In the \RequestResponse folder:</span></span><br /><br /> <span data-ttu-id="3b0df-130">AssemblyInfo.cs、default.aspx、default.aspx.cs、Global.asax、Global.asax.cs、RequestResponse.csproj、RequestResponse.csproj.webinfo、RequestResponse.sln、Web.config</span><span class="sxs-lookup"><span data-stu-id="3b0df-130">AssemblyInfo.cs, default.aspx, default.aspx.cs, Global.asax, Global.asax.cs, RequestResponse.csproj, RequestResponse.csproj.webinfo, RequestResponse.sln, Web.config</span></span> | <span data-ttu-id="3b0df-131">このサンプルのドライバーとして機能する ASP.NET アプリケーションを構成するファイル (プロジェクト ファイルとソリューション ファイル、ASPX ファイル、Microsoft Visual C# .NET ソース ファイルなど) を含みます。</span><span class="sxs-lookup"><span data-stu-id="3b0df-131">Contains files that constitute the ASP.NET application that serves as a driver for this sample, including project and solution files, ASPX files, Microsoft Visual C# .NET source files, and so on.</span></span> |

## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="3b0df-132">このサンプルのビルドと初期化</span><span class="sxs-lookup"><span data-stu-id="3b0df-132">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="3b0df-133">次の手順を使用して、HTTPRequestResponse サンプルをビルドおよび初期化します。</span><span class="sxs-lookup"><span data-stu-id="3b0df-133">Use the following procedure to build and initialize the HTTPRequestResponse sample.</span></span>  

#### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="3b0df-134">このサンプルを作成および初期化するには</span><span class="sxs-lookup"><span data-stu-id="3b0df-134">To build and initialize this sample</span></span>  

1. <span data-ttu-id="3b0df-135">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="3b0df-135">In a command window, navigate to the following folder:</span></span>  

    <span data-ttu-id="3b0df-136">\<*パスのサンプル*\>\AdaptersUsage\HTTPRequestResponse</span><span class="sxs-lookup"><span data-stu-id="3b0df-136">\<*Samples Path*\>\AdaptersUsage\HTTPRequestResponse</span></span>  

2. <span data-ttu-id="3b0df-137">ファイルは、次の操作を実行します。 Setup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="3b0df-137">Run the file Setup.bat, which performs the following actions:</span></span>  

   - <span data-ttu-id="3b0df-138">このサンプルを実行する ASP.NET アプリケーションをコンパイルし構成します。</span><span class="sxs-lookup"><span data-stu-id="3b0df-138">Compiles and configures the ASP.NET application used to drive this sample.</span></span>  

     > [!NOTE]
     >  <span data-ttu-id="3b0df-139">IIS マネージャーでアプリケーション プールを作成、設定、 **DefaultAppPool** .NET Framework バージョンを **.Net Framework v4.0**します。</span><span class="sxs-lookup"><span data-stu-id="3b0df-139">While creating application pool in IIS Manager, set the **DefaultAppPool** .NET Framework version to **.Net Framework v4.0**.</span></span>  

   - <span data-ttu-id="3b0df-140">このサンプルで使用する [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] オーケストレーションをコンパイルし、展開します。</span><span class="sxs-lookup"><span data-stu-id="3b0df-140">Compiles and deploys the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration used in this sample.</span></span>  

   - <span data-ttu-id="3b0df-141">コンパイルし、Microsoft の展開[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]このサンプルのプロジェクト。</span><span class="sxs-lookup"><span data-stu-id="3b0df-141">Compiles and deploys the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] projects for this sample.</span></span>  

   - <span data-ttu-id="3b0df-142">必要な [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ポートを作成しバインドします。</span><span class="sxs-lookup"><span data-stu-id="3b0df-142">Creates and binds the necessary [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ports.</span></span>  

   - <span data-ttu-id="3b0df-143">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] オーケストレーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="3b0df-143">Starts the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration.</span></span>  

     > [!IMPORTANT]
     >  <span data-ttu-id="3b0df-144">Web アプリケーションを実装するサンプル コード (Default.aspx.cs) を変更して環境を反映する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b0df-144">You must change the sample code that implements the Web application (Default.aspx.cs) to reflect your environment:</span></span>  
     >   
     >  <span data-ttu-id="3b0df-145">http://\<*サーバー名*\>/\<*仮想 dir*\>>/btshttpreceive.dll 場所`<servername>`Web の名前を指定しますサーバーに、投稿して`<`*仮想ディレクトリ*`>`はこのファイルが存在する仮想ディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="3b0df-145">http://\<*server name*\>/\<*virtual dir*\>/BTSHTTPReceive.dll where `<servername>` is the name of the Web server you are posting to, and `<`*virtual dir*`>` is the virtual directory where this file resides.</span></span>  

     > [!NOTE]
     >  <span data-ttu-id="3b0df-146">このサンプルを実行する前に、BizTalk がビルド プロセス中および初期化プロセス中にエラーを報告していないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3b0df-146">You should confirm that BizTalk did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  

     > [!NOTE]
     >  <span data-ttu-id="3b0df-147">開き、Setup.bat ファイルを実行することがなくこのサンプルでは、プロジェクトをビルドする場合は、まず、.NET Framework の厳密名ユーティリティ (sn.exe) を使用して厳密な名前キーのペアを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b0df-147">If you choose to open and build the projects in this sample without running the file Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name Utility (sn.exe).</span></span> <span data-ttu-id="3b0df-148">このキー ペアは、生成されたアセンブリの署名に使用します。</span><span class="sxs-lookup"><span data-stu-id="3b0df-148">Use this key pair to sign the resulting assemblies.</span></span> <span data-ttu-id="3b0df-149">プロジェクトをビルドする前に、default.aspx.resx および Global.asax.resx への参照を RequestResponse.csproj ファイルから手動で削除する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="3b0df-149">You must also manually remove the references to default.aspx.resx and Global.asax.resx from the file RequestResponse.csproj before attempting to build that project.</span></span>  

     > [!NOTE]
     >  <span data-ttu-id="3b0df-150">Setup.bat によって行われた変更を元に戻すには、Cleanup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="3b0df-150">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="3b0df-151">Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。</span><span class="sxs-lookup"><span data-stu-id="3b0df-151">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  

     > [!NOTE]
     >  <span data-ttu-id="3b0df-152">構成する必要があり、受信アダプターを有効に HTTP を使用する IIS。</span><span class="sxs-lookup"><span data-stu-id="3b0df-152">You must configure and enable IIS to use the HTTP receive adapter.</span></span> <span data-ttu-id="3b0df-153">詳細については、次を参照してください。 [IIS の HTTP 受信場所を構成する方法](../core/how-to-configure-iis-for-an-http-receive-location.md)します。</span><span class="sxs-lookup"><span data-stu-id="3b0df-153">For more information, see [How to Configure IIS for an HTTP Receive Location](../core/how-to-configure-iis-for-an-http-receive-location.md).</span></span>  

3. <span data-ttu-id="3b0df-154">Setup.bat ファイルを実行すると、このサンプルの仮想ディレクトリが構成され、既定の Web サイトに関連付けられた IIS アプリケーション プールで実行されるよう設定されます。</span><span class="sxs-lookup"><span data-stu-id="3b0df-154">The setup.bat file configures the virtual directory for this sample to run in the IIS application pool associated with the default web site.</span></span>  <span data-ttu-id="3b0df-155">内のユーザーのコンテキストで実行するには、このサンプル用の仮想ディレクトリを構成する、 **BizTalk 分離ホスト ユーザー**と**IIS_IURS**ユーザー グループの場合は、新しいで実行する仮想ディレクトリを構成する必要がありますIIS アプリケーション プール。</span><span class="sxs-lookup"><span data-stu-id="3b0df-155">To configure the virtual directory for this sample to run under the context of a user in the **BizTalk Isolated Host Users** and **IIS_IURS** user groups, you should configure the virtual directory to run in a new IIS application pool.</span></span> <span data-ttu-id="3b0df-156">仮想ディレクトリを新しい IIS アプリケーション プールで実行するよう構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3b0df-156">Configure the virtual directory to run in a new IIS application pool by completing the following steps:</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="3b0df-157">別の SDK サンプル用に新しいアプリケーション プールを作成済みの場合は、次の最後の手順に進むことができます。</span><span class="sxs-lookup"><span data-stu-id="3b0df-157">If you have already created a new application pool for another SDK sample then you can proceed to the last step below.</span></span>  

   1.  <span data-ttu-id="3b0df-158">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリックします**インターネット インフォメーション サービス (IIS) マネージャー**.</span><span class="sxs-lookup"><span data-stu-id="3b0df-158">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  

   2.  <span data-ttu-id="3b0df-159">**インターネット インフォメーション サービス (IIS) マネージャー**に移動し、**アプリケーション プール**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="3b0df-159">In the **Internet Information Services (IIS) Manager**, navigate to the **Application Pools** folder.</span></span>  

   3.  <span data-ttu-id="3b0df-160">右クリックし、**アプリケーション プール**フォルダーとクリック**新規**、**アプリケーション プールしています.**</span><span class="sxs-lookup"><span data-stu-id="3b0df-160">Right-click the **Application Pools** folder and click **New**, **Application Pool...**</span></span>  

   4.  <span data-ttu-id="3b0df-161">名前を入力、**アプリケーション プール ID:** 、BizTalkSDKSamples などことを確認します、**新しいアプリケーション プールの既定の設定を使用して**オプションが選択されているし、をクリックして**OK**に新しいアプリケーション プールを作成します。</span><span class="sxs-lookup"><span data-stu-id="3b0df-161">Enter a name for the **Application Pool ID:** such as BizTalkSDKSamples, verify that the **Use default settings for new application pool** option is selected and click **OK** to create the new application pool.</span></span>  

   5.  <span data-ttu-id="3b0df-162">新しいアプリケーション プールを右クリックし、をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="3b0df-162">Right-click the new application pool and then click **Properties**.</span></span>  

   6.  <span data-ttu-id="3b0df-163">をクリックして、 **Identity**  タブのプロパティ ダイアログ ボックスし、このアプリケーション プールのメンバーであるユーザーに実行する id を変更、 **BizTalk 分離ホスト ユーザー**ユーザー グループ。</span><span class="sxs-lookup"><span data-stu-id="3b0df-163">Click the **Identity** tab of the properties dialog box and change the identity under which this application pool runs to a user that is a member of the **BizTalk Isolated Host Users** user group.</span></span>  <span data-ttu-id="3b0df-164">このユーザーは、ローカルのメンバーでもある必要があります**IIS_IURS**ユーザー グループ。</span><span class="sxs-lookup"><span data-stu-id="3b0df-164">This user should also be a member of the local **IIS_IURS** user group.</span></span>  

   7.  <span data-ttu-id="3b0df-165">この SDK サンプルの仮想ディレクトリを、新しいアプリケーション プールで実行するよう構成します。</span><span class="sxs-lookup"><span data-stu-id="3b0df-165">Configure the virtual directory for this SDK sample to run under the new application pool.</span></span> <span data-ttu-id="3b0df-166">**アプリケーション プール**設定は、**仮想ディレクトリ**仮想ディレクトリのプロパティ ダイアログ ボックスのタブ。</span><span class="sxs-lookup"><span data-stu-id="3b0df-166">The **Application pool** setting is available on the **Virtual Directory** tab of the Virtual Directory properties dialog box.</span></span> <span data-ttu-id="3b0df-167">このサンプルで作成される仮想ディレクトリは、HttpRequestResponseSample という名前になります。</span><span class="sxs-lookup"><span data-stu-id="3b0df-167">The virtual directory created for this sample is HttpRequestResponseSample.</span></span>  

## <a name="running-this-sample"></a><span data-ttu-id="3b0df-168">このサンプルの実行</span><span class="sxs-lookup"><span data-stu-id="3b0df-168">Running This Sample</span></span>  
 <span data-ttu-id="3b0df-169">次の手順を使用して、HTTPRequestResponse サンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="3b0df-169">Use the following procedure to run the HTTPRequestResponse sample.</span></span>  

#### <a name="to-run-this-sample"></a><span data-ttu-id="3b0df-170">このサンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="3b0df-170">To run this sample</span></span>  

1.  <span data-ttu-id="3b0df-171">Internet Explorer に移動します。 http://localhost/RequestResponse/ します。</span><span class="sxs-lookup"><span data-stu-id="3b0df-171">In Internet Explorer, navigate to http://localhost/RequestResponse/.</span></span>  

2.  <span data-ttu-id="3b0df-172">Web フォームで、必要なフィールドに入力し、クリックして**Place Order**して注文を送信します。</span><span class="sxs-lookup"><span data-stu-id="3b0df-172">Complete the necessary fields in the Web form, and then click **Place Order** to submit your order.</span></span>  

3.  <span data-ttu-id="3b0df-173">応答を受信した後、Web フォームが更新される際に注文のステータスを確認します。</span><span class="sxs-lookup"><span data-stu-id="3b0df-173">Observe the status of your order when the Web form refreshes after receiving a response.</span></span>  

## <a name="comments"></a><span data-ttu-id="3b0df-174">コメント</span><span class="sxs-lookup"><span data-stu-id="3b0df-174">Comments</span></span>  
 <span data-ttu-id="3b0df-175">**BTSHTTPReceiveISAPI**このサンプルで使用される拡張機能が 1 台のコンピューターの既定のインストールで動作するよう構成します。</span><span class="sxs-lookup"><span data-stu-id="3b0df-175">The **BTSHTTPReceiveISAPI** extension used in this sample is configured to work on a single computer default installation.</span></span> <span data-ttu-id="3b0df-176">このサンプルに追加の構成を拡張するを参照してください。 [HTTP アダプター](../core/http-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="3b0df-176">To extend this sample for additional configurations, see [HTTP Adapter](../core/http-adapter.md).</span></span>  

 <span data-ttu-id="3b0df-177">このサンプルは、Web フォームまたは一般的な HTTP を介して [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] にデータを送信するために必要なアプリケーションに拡張できます。</span><span class="sxs-lookup"><span data-stu-id="3b0df-177">You can extend this sample to applications that are required to submit data to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] through a Web form, or through HTTP in general.</span></span> <span data-ttu-id="3b0df-178">このサンプルの ASP.NET アプリケーションの部分を拡張すると、さらに多くの情報をクエリして、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] にデータを送信する前にその他の処理を実行できます。</span><span class="sxs-lookup"><span data-stu-id="3b0df-178">By extending the ASP.NET application portion of this sample, you can query for more information and perform other preprocessing before submitting the data to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  

## <a name="see-also"></a><span data-ttu-id="3b0df-179">参照</span><span class="sxs-lookup"><span data-stu-id="3b0df-179">See Also</span></span>  
 [<span data-ttu-id="3b0df-180">HTTP アダプター サンプル</span><span class="sxs-lookup"><span data-stu-id="3b0df-180">HTTP Adapter Samples</span></span>](../core/http-adapter-samples.md)