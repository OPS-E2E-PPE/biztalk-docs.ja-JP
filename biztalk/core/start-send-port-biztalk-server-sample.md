---
title: 送信ポートの開始 (BizTalk Server サンプル) |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send ports, examples
- examples, send ports
- send ports, starting
ms.assetid: 84e54c9e-e9e8-4bb2-a191-20c29e127dae
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f293d00848c32f6b519349543c8a39824d9bca8c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973880"
---
# <a name="start-send-port-biztalk-server-sample"></a><span data-ttu-id="9751b-102">送信ポートの開始 (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="9751b-102">Start Send Port (BizTalk Server Sample)</span></span>
<span data-ttu-id="9751b-103">送信ポート開始のサンプルは、ファイル アダプタの使用時に、送信ポートを開始し、オプションでプライマリ トランスポート アドレスを設定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="9751b-103">The Start Send Port sample demonstrates how to start a send port and optionally set the Primary Transport Address when using the FILE adapter.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="9751b-104">展開スクリプトは、展開後に不要になった場合は、削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9751b-104">Deployment scripts should be removed after deployment if not needed.</span></span> <span data-ttu-id="9751b-105">保持する必要のある管理スクリプトおよび他のスクリプトは、ACL によってセキュリティで保護し、厳重に監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9751b-105">Administration scripts and other scripts that must remain should be secured by ACL’s and closely monitored.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="9751b-106">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="9751b-106">What This Sample Does</span></span>  
 <span data-ttu-id="9751b-107">このサンプルを構成するスクリプト ファイル内の Visual Basic Scripting Edition (VBScript) スクリプトは、BizTalk Server WMI プロバイダーを使用して、次の操作を実行する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="9751b-107">The Visual Basic Scripting Edition (VBScript) script in the script file that constitutes this sample shows how to perform the following operations using the BizTalk Server WMI provider:</span></span>  
  
-   <span data-ttu-id="9751b-108">送信ポート名が指定されていることを前提として、クエリを実行し、一致する送信ポートの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="9751b-108">Given a send port name, query for a list of matching send ports.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9751b-109">通常、指定された名前に一致する送信ポートは 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="9751b-109">Generally, there will only be one send port that matches a given name.</span></span>  
  
-   <span data-ttu-id="9751b-110">これらの送信ポートのプライマリ トランスポート アドレスを設定します (インストール パスの相対パスで指定)。</span><span class="sxs-lookup"><span data-stu-id="9751b-110">Set the Primary Transport Address for those send ports (relative to the installation path).</span></span>  
  
-   <span data-ttu-id="9751b-111">開始される送信ポート。</span><span class="sxs-lookup"><span data-stu-id="9751b-111">Start those send ports.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="9751b-112">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="9751b-112">Where to Find This Sample</span></span>  
 <span data-ttu-id="9751b-113">このサンプル ファイルは、次の SDK の場所にあります。</span><span class="sxs-lookup"><span data-stu-id="9751b-113">The sample files are located in the following SDK location:</span></span>  
  
 <span data-ttu-id="9751b-114">\<*パスのサンプル*\>\Admin\WMI\Start Port\ の送信</span><span class="sxs-lookup"><span data-stu-id="9751b-114">\<*Samples Path*\>\Admin\WMI\Start Send Port\\</span></span>  
  
 <span data-ttu-id="9751b-115">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="9751b-115">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="9751b-116">ファイル</span><span class="sxs-lookup"><span data-stu-id="9751b-116">File(s)</span></span>|<span data-ttu-id="9751b-117">Description</span><span class="sxs-lookup"><span data-stu-id="9751b-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9751b-118">\VBScript フォルダー内のファイル : </span><span class="sxs-lookup"><span data-stu-id="9751b-118">In the \VBScript folder:</span></span><br /><br /> <span data-ttu-id="9751b-119">StartSendPort.vbs</span><span class="sxs-lookup"><span data-stu-id="9751b-119">StartSendPort.vbs</span></span>|<span data-ttu-id="9751b-120">開始する送信ポートを指定するパラメータを取得すると共に、そのポートに関連付けられているプライマリ トランスポート アドレスの新しい値を必要に応じて取得する VBScript ファイル。</span><span class="sxs-lookup"><span data-stu-id="9751b-120">VBScript file that takes parameters that specify a send port to start, and optionally, a new value for the Primary Transport Address associated with that port.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="9751b-121">このサンプルのビルドと初期化</span><span class="sxs-lookup"><span data-stu-id="9751b-121">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="9751b-122">送信ポート開始のサンプルは、ビルドまたは初期化が不要な 1 つの VBScript ファイルで構成されています。</span><span class="sxs-lookup"><span data-stu-id="9751b-122">The Start Send Port sample consists of a single VBScript file that you do not need to build or initialize.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="9751b-123">このサンプルの実行</span><span class="sxs-lookup"><span data-stu-id="9751b-123">Running This Sample</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="9751b-124">このサンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="9751b-124">To run this sample</span></span>  
  
1.  <span data-ttu-id="9751b-125">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="9751b-125">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="9751b-126">\<*パスのサンプル*\>\Admin\WMI\Start Port\VBScript\ の送信</span><span class="sxs-lookup"><span data-stu-id="9751b-126">\<*Samples Path*\>\Admin\WMI\Start Send Port\VBScript\\</span></span>  
  
2.  <span data-ttu-id="9751b-127">cscript プログラムを使用し、次のコマンド ライン引数 (2 番目はオプション) を渡して、ファイル StartSendPort.vbs を実行します。</span><span class="sxs-lookup"><span data-stu-id="9751b-127">Run the file StartSendPort.vbs using the cscript program, passing the following command-line arguments, the second of which is optional:</span></span>  
  
    -   <span data-ttu-id="9751b-128">**\<** ***SendPortName* \>です。**</span><span class="sxs-lookup"><span data-stu-id="9751b-128">**\<** ***SendPortName* \>.**</span></span> <span data-ttu-id="9751b-129">開始する送信ポートの名前。</span><span class="sxs-lookup"><span data-stu-id="9751b-129">The name of the send port to start.</span></span> <span data-ttu-id="9751b-130">送信ポートの名前にスペースが含まれる場合は、名前を引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="9751b-130">If the send port name contains spaces, enclose the name in quotes.</span></span>  
  
    -   <span data-ttu-id="9751b-131">**\<** ***PrimaryTransportAddress* \>です。**</span><span class="sxs-lookup"><span data-stu-id="9751b-131">**\<** ***PrimaryTransportAddress* \>.**</span></span> <span data-ttu-id="9751b-132">製品のインストール場所を基準としたプライマリ トランスポート アドレス。この引数を指定することによって変更できます。</span><span class="sxs-lookup"><span data-stu-id="9751b-132">The Primary Transport Address, relative to the product installation location, that you can change by specifying this argument.</span></span> <span data-ttu-id="9751b-133">プライマリ アダプタ アドレスに空白が含まれている場合は、名前を引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="9751b-133">If the primary adapter address contains spaces, enclose the name in quotes.</span></span>  
  
         <span data-ttu-id="9751b-134">例:</span><span class="sxs-lookup"><span data-stu-id="9751b-134">For example:</span></span>  
  
        ```  
        cscript StartSendPort.vbs "My Business Send Port" SDK\Samples\HelloWorld\Out\%MessageID%.xml  
        ```  
  
## <a name="comments"></a><span data-ttu-id="9751b-135">コメント</span><span class="sxs-lookup"><span data-stu-id="9751b-135">Comments</span></span>  
 <span data-ttu-id="9751b-136">BizTalk Server 管理コンソールで実行できるすべてのタスクは、Windows WMI オブジェクト モデルにアクセスするスクリプトを使用しても実行できます。</span><span class="sxs-lookup"><span data-stu-id="9751b-136">All tasks that you can perform in the BizTalk Server Administration console can also be performed by using script that accesses the Windows WMI object model.</span></span>  
  
 <span data-ttu-id="9751b-137">スクリプト ファイル StartSendPort.vbs には、実行する操作についての説明のある詳細なコメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9751b-137">The script file StartSendPort.vbs contains detailed comments with further explanation about the operations that it performs.</span></span> <span data-ttu-id="9751b-138">詳細については、Windows Management Instrumentation」を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102)です。</span><span class="sxs-lookup"><span data-stu-id="9751b-138">For more information, see Windows Management Instrumentation at [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9751b-139">参照</span><span class="sxs-lookup"><span data-stu-id="9751b-139">See Also</span></span>  
 [<span data-ttu-id="9751b-140">Admin-WMI (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="9751b-140">Admin-WMI (BizTalk Server Samples Folder)</span></span>](../core/admin-wmi-biztalk-server-samples-folder.md)