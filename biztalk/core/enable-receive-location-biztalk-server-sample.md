---
title: "有効にする受信場所 (BizTalk Server サンプル) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive locations, examples
- receive locations, enabling
- examples, receive locations
ms.assetid: dd04b38a-634d-4c9a-b31a-2f226fa91d19
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99923c3029b72dae660bee4b4089336e90e2e4e7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="enable-receive-location-biztalk-server-sample"></a><span data-ttu-id="b64e7-102">有効にする受信場所 (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="b64e7-102">Enable Receive Location (BizTalk Server Sample)</span></span>
<span data-ttu-id="b64e7-103">受信場所の有効化のサンプルでは、受信場所を有効にする方法を示します。オプションで、その受信場所の受信トランスポート URL を設定する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="b64e7-103">The Enable Receive Location sample demonstrates how to enable a receive location and optionally set the Inbound Transport URL for that receive location.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="b64e7-104">展開スクリプトは、展開後に不要になった場合は、削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b64e7-104">Deployment scripts should be removed after deployment if not needed.</span></span> <span data-ttu-id="b64e7-105">保持する必要のある管理スクリプトおよび他のスクリプトは、ACL によってセキュリティで保護し、厳重に監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b64e7-105">Administration scripts and other scripts that must remain should be secured by ACL’s and closely monitored.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="b64e7-106">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="b64e7-106">What This Sample Does</span></span>  
 <span data-ttu-id="b64e7-107">このサンプルを構成しているスクリプト ファイル内の Microsoft Visual Basic Scripting Edition (VBScript) スクリプトは、BizTalk Server WMI プロバイダを使用した次の操作の実行方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b64e7-107">The Microsoft Visual Basic Scripting Edition (VBScript) script in the script file that constitutes this sample shows how to perform the following operations using the BizTalk Server WMI provider:</span></span>  
  
-   <span data-ttu-id="b64e7-108">受信ポート名と受信場所が指定されていることを前提として、クエリを実行し、一致する受信場所の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="b64e7-108">Given a receive port name and receive location, query for a list of matching receive locations.</span></span>  
  
-   <span data-ttu-id="b64e7-109">受信場所の受信トランスポート URL を設定します (インストール パスの相対パスで指定)。</span><span class="sxs-lookup"><span data-stu-id="b64e7-109">Set the Inbound Transport URL for a receive location (relative to the installation path).</span></span>  
  
-   <span data-ttu-id="b64e7-110">受信場所を有効にします。</span><span class="sxs-lookup"><span data-stu-id="b64e7-110">Enable a receive location.</span></span>  
  
-   <span data-ttu-id="b64e7-111">意味のある情報がユーザーに返されるようにエラーを処理します。</span><span class="sxs-lookup"><span data-stu-id="b64e7-111">Handle any errors such that meaningful information is returned to the user.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="b64e7-112">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="b64e7-112">Where to Find This Sample</span></span>  
 <span data-ttu-id="b64e7-113">このサンプルは、SDK がある次の場所にあります。</span><span class="sxs-lookup"><span data-stu-id="b64e7-113">The sample is located in the following SDK location:</span></span>  
  
 <span data-ttu-id="b64e7-114">\<*パスのサンプル*> \Admin\WMI\Enable Location\ の受信</span><span class="sxs-lookup"><span data-stu-id="b64e7-114">\<*Samples Path*>\Admin\WMI\Enable Receive Location\\</span></span>  
  
 <span data-ttu-id="b64e7-115">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="b64e7-115">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="b64e7-116">ファイル</span><span class="sxs-lookup"><span data-stu-id="b64e7-116">File(s)</span></span>|<span data-ttu-id="b64e7-117">Description</span><span class="sxs-lookup"><span data-stu-id="b64e7-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b64e7-118">\VBScript フォルダー内のファイル : </span><span class="sxs-lookup"><span data-stu-id="b64e7-118">In the \VBScript folder:</span></span><br /><br /> <span data-ttu-id="b64e7-119">EnableRecLoc.vbs</span><span class="sxs-lookup"><span data-stu-id="b64e7-119">EnableRecLoc.vbs</span></span>|<span data-ttu-id="b64e7-120">有効にする受信場所を指定するパラメータを受け取り、必要に応じてその受信場所に関連付けられている受信トランスポート URL の新しい値を受け取る VBScript ファイル。</span><span class="sxs-lookup"><span data-stu-id="b64e7-120">VBScript file that takes parameters that specify a receive location to be enabled, and optionally, a new value for the Inbound Transport URL associated with that receive location.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="b64e7-121">このサンプルのビルドと初期化</span><span class="sxs-lookup"><span data-stu-id="b64e7-121">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="b64e7-122">受信場所の有効化のサンプルは、ビルドまたは初期化が不要な 1 つの VBScript ファイルで構成されます。</span><span class="sxs-lookup"><span data-stu-id="b64e7-122">The Enable Receive Location sample consists of a single VBScript file that you do not need to build or initialize.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="b64e7-123">このサンプルの実行</span><span class="sxs-lookup"><span data-stu-id="b64e7-123">Running This Sample</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="b64e7-124">このサンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="b64e7-124">To run this sample</span></span>  
  
1.  <span data-ttu-id="b64e7-125">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="b64e7-125">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="b64e7-126">\<*パスのサンプル*> \Admin\WMI\Enable Location\VBScript\ の受信</span><span class="sxs-lookup"><span data-stu-id="b64e7-126">\<*Samples Path*>\Admin\WMI\Enable Receive Location\VBScript\\</span></span>  
  
2.  <span data-ttu-id="b64e7-127">cscript プログラムを使用し、次のコマンド ライン引数 (3 番目はオプション) を渡して、ファイル EnableRecLoc.vbs を実行します。</span><span class="sxs-lookup"><span data-stu-id="b64e7-127">Run the file EnableRecLoc.vbs using the cscript program, passing the following command-line arguments, of which the third one is optional:</span></span>  
  
    -   **\<**   
         <span data-ttu-id="b64e7-128">***ReceivePortName* >。**</span><span class="sxs-lookup"><span data-stu-id="b64e7-128">***ReceivePortName* >.**</span></span> <span data-ttu-id="b64e7-129">有効にする受信場所を含む受信ポートの名前。</span><span class="sxs-lookup"><span data-stu-id="b64e7-129">The name of the receive port that contains the receive location to be enabled.</span></span> <span data-ttu-id="b64e7-130">受信ポート名に空白が含まれている場合は、名前を引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="b64e7-130">If the receive port name contains spaces, enclose the name in quotes.</span></span>  
  
    -   **\<**   
         <span data-ttu-id="b64e7-131">***ReceiveLocationName* >。**</span><span class="sxs-lookup"><span data-stu-id="b64e7-131">***ReceiveLocationName* >.**</span></span> <span data-ttu-id="b64e7-132">指定の受信ポート内にある、有効にする受信場所の名前。</span><span class="sxs-lookup"><span data-stu-id="b64e7-132">The name of the receive location within the specified receive port to be enabled.</span></span> <span data-ttu-id="b64e7-133">受信場所名に空白が含まれている場合は、名前を引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="b64e7-133">If the receive location name contains spaces, enclose the name in quotes.</span></span>  
  
    -   **\<**   
         <span data-ttu-id="b64e7-134">***InboundTransportURI* >。**</span><span class="sxs-lookup"><span data-stu-id="b64e7-134">***InboundTransportURI* >.**</span></span> <span data-ttu-id="b64e7-135">製品のインストール場所に相対的な受信アダプタ URI。この引数を指定することによって変更できます。</span><span class="sxs-lookup"><span data-stu-id="b64e7-135">A receive adapter URI, relative to the product installation location, that you can change by specifying this argument.</span></span> <span data-ttu-id="b64e7-136">受信アダプタ URI に空白が含まれている場合は、URI を引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="b64e7-136">If the inbound adapter URI contains spaces, enclose the URI in quotes.</span></span>  
  
         <span data-ttu-id="b64e7-137">例:</span><span class="sxs-lookup"><span data-stu-id="b64e7-137">For example:</span></span>  
  
        ```  
        cscript EnableRecLoc.vbs "My Business Receive Port" MyBusinessReceiveLocation  
        ```  
  
         <span data-ttu-id="b64e7-138">- または -</span><span class="sxs-lookup"><span data-stu-id="b64e7-138">-OR-</span></span>  
  
        ```  
        cscript EnableRecLoc.vbs MyBusinessReceivePort "My Business Receive Location" SDK\Samples\HelloWorld\In\*.xml  
        ```  
  
## <a name="comments"></a><span data-ttu-id="b64e7-139">コメント</span><span class="sxs-lookup"><span data-stu-id="b64e7-139">Comments</span></span>  
 <span data-ttu-id="b64e7-140">BizTalk Server 管理コンソールで実行できるすべてのタスクは、Windows WMI オブジェクト モデルにアクセスするスクリプトを使用しても実行できます。</span><span class="sxs-lookup"><span data-stu-id="b64e7-140">All tasks that you can perform in the BizTalk Server Administration console can also be performed by using script that accesses the Windows WMI object model.</span></span>  
  
 <span data-ttu-id="b64e7-141">スクリプト ファイル EnableRecLoc.vbs には、実行する操作についての説明が記された詳細なコメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b64e7-141">The script file EnableRecLoc.vbs contains detailed comments with further explanation about the operations that it performs.</span></span>  
  
 <span data-ttu-id="b64e7-142">詳細については、Windows Management Instrumentation」を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102)です。</span><span class="sxs-lookup"><span data-stu-id="b64e7-142">For more information, see Windows Management Instrumentation at [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b64e7-143">参照</span><span class="sxs-lookup"><span data-stu-id="b64e7-143">See Also</span></span>  
 [<span data-ttu-id="b64e7-144">管理 WMI (BizTalk Server Samples フォルダ)</span><span class="sxs-lookup"><span data-stu-id="b64e7-144">Admin-WMI (BizTalk Server Samples Folder)</span></span>](../core/admin-wmi-biztalk-server-samples-folder.md)