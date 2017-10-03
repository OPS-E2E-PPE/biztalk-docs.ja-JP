---
title: "送信ポートの削除 (BizTalk Server サンプル) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send ports, examples
- examples, send ports
- send ports, deleting
- deleting, send ports
ms.assetid: e6643525-fa9f-4d39-880f-314749a68471
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2bb37ae93b45ac1721da582cc0092bda5d67999
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="remove-send-port-biztalk-server-sample"></a><span data-ttu-id="501c9-102">送信ポートの削除 (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="501c9-102">Remove Send Port (BizTalk Server Sample)</span></span>
<span data-ttu-id="501c9-103">送信ポートの削除のサンプルでは、1 つ以上の送信ポートの参加を解除し、削除する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="501c9-103">The Remove Send Port sample demonstrates how to unenlist and remove one or more send ports.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="501c9-104">展開スクリプトは、展開後に不要になった場合は、削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="501c9-104">Deployment scripts should be removed after deployment if not needed.</span></span> <span data-ttu-id="501c9-105">保持する必要のある管理スクリプトおよび他のスクリプトは、ACL によってセキュリティで保護し、厳重に監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="501c9-105">Administration scripts and other scripts that must remain should be secured by ACL’s and closely monitored.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="501c9-106">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="501c9-106">What This Sample Does</span></span>  
 <span data-ttu-id="501c9-107">このサンプルを構成するスクリプト ファイル内の Visual Basic Scripting Edition (VBScript) スクリプトは、BizTalk Server WMI プロバイダーを使用して、次の操作を実行する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="501c9-107">The Visual Basic Scripting Edition (VBScript) script in the script file that constitutes this sample shows how to perform the following operations using the BizTalk Server WMI provider:</span></span>  
  
-   <span data-ttu-id="501c9-108">送信ポート名が指定されていることを前提として、クエリを実行し、一致する送信ポートの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="501c9-108">Given a send port name, query for a list of matching send ports.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="501c9-109">通常、指定された名前に一致する送信ポートは 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="501c9-109">Generally, there will only be one send port that matches a given name.</span></span>  
  
-   <span data-ttu-id="501c9-110">送信ポートの参加を解除します。</span><span class="sxs-lookup"><span data-stu-id="501c9-110">Unenlist those send ports.</span></span>  
  
-   <span data-ttu-id="501c9-111">削除された送信ポート。</span><span class="sxs-lookup"><span data-stu-id="501c9-111">Delete those send ports.</span></span>  
  
-   <span data-ttu-id="501c9-112">意味のある情報がユーザーに返されるようにエラーを処理します。</span><span class="sxs-lookup"><span data-stu-id="501c9-112">Handle any errors such that meaningful information is returned to the user.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="501c9-113">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="501c9-113">Where to Find This Sample</span></span>  
 <span data-ttu-id="501c9-114">このサンプルは、SDK がある次の場所にあります。</span><span class="sxs-lookup"><span data-stu-id="501c9-114">The sample is located in the following SDK location:</span></span>  
  
 <span data-ttu-id="501c9-115">\<*パスのサンプル*> \Admin\WMI\Remove Port\ の送信</span><span class="sxs-lookup"><span data-stu-id="501c9-115">\<*Samples Path*>\Admin\WMI\Remove Send Port\\</span></span>  
  
 <span data-ttu-id="501c9-116">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="501c9-116">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="501c9-117">ファイル</span><span class="sxs-lookup"><span data-stu-id="501c9-117">File(s)</span></span>|<span data-ttu-id="501c9-118">Description</span><span class="sxs-lookup"><span data-stu-id="501c9-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="501c9-119">\VBScript フォルダー内のファイル : </span><span class="sxs-lookup"><span data-stu-id="501c9-119">In the \VBScript folder:</span></span><br /><br /> <span data-ttu-id="501c9-120">RemoveSendPort.vbs</span><span class="sxs-lookup"><span data-stu-id="501c9-120">RemoveSendPort.vbs</span></span>|<span data-ttu-id="501c9-121">参加を解除し、削除する 1 つ以上の送信ポートを指定するパラメータを取る VBScript ファイル。</span><span class="sxs-lookup"><span data-stu-id="501c9-121">VBScript file that takes a parameter that specifies one or more send ports to unenlist and remove.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="501c9-122">このサンプルのビルドと初期化</span><span class="sxs-lookup"><span data-stu-id="501c9-122">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="501c9-123">送信ポートの削除のサンプルは、ビルドまたは初期化が不要な 1 つの VBScript ファイルで構成されています。</span><span class="sxs-lookup"><span data-stu-id="501c9-123">The Remove Send Port sample consists of a single VBScript file that you not need to build or initialize.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="501c9-124">このサンプルの実行</span><span class="sxs-lookup"><span data-stu-id="501c9-124">Running This Sample</span></span>  
  
#### <a name="to-run-the-remove-send-port-sample"></a><span data-ttu-id="501c9-125">送信ポートの削除のサンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="501c9-125">To run the Remove Send Port sample</span></span>  
  
1.  <span data-ttu-id="501c9-126">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="501c9-126">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="501c9-127">\<*パスのサンプル*> \Admin\WMI\Remove Port\VBScript\ の受信</span><span class="sxs-lookup"><span data-stu-id="501c9-127">\<*Samples Path*>\Admin\WMI\Remove Receive Port\VBScript\\</span></span>  
  
2.  <span data-ttu-id="501c9-128">cscript プログラムを使用し、次のコマンド ライン引数を渡して、ファイル RemoveSendPort.vbs を実行します。</span><span class="sxs-lookup"><span data-stu-id="501c9-128">Run the file RemoveSendPort.vbs using the cscript program, passing the following command-line argument:</span></span>  
  
     **\<**   
     <span data-ttu-id="501c9-129">***SendPortName* >。**</span><span class="sxs-lookup"><span data-stu-id="501c9-129">***SendPortName* >.**</span></span> <span data-ttu-id="501c9-130">削除する送信ポートの名前。</span><span class="sxs-lookup"><span data-stu-id="501c9-130">The name of the send port(s) to remove.</span></span> <span data-ttu-id="501c9-131">送信ポートの名前にスペースが含まれる場合は、名前を引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="501c9-131">If the send port name contains spaces, enclose the name in quotes.</span></span>  
  
     <span data-ttu-id="501c9-132">例:</span><span class="sxs-lookup"><span data-stu-id="501c9-132">For example:</span></span>  
  
    ```  
    cscript RemoveSendPort.vbs "My Business Send Port"  
    ```  
  
## <a name="comments"></a><span data-ttu-id="501c9-133">コメント</span><span class="sxs-lookup"><span data-stu-id="501c9-133">Comments</span></span>  
 <span data-ttu-id="501c9-134">BizTalk Server 管理コンソールで実行できるすべてのタスクは、Windows WMI オブジェクト モデルにアクセスするスクリプトを使用しても実行できます。</span><span class="sxs-lookup"><span data-stu-id="501c9-134">All tasks that you can perform in the BizTalk Server Administration console can also be performed by using script that accesses the Windows WMI object model.</span></span>  
  
 <span data-ttu-id="501c9-135">スクリプト ファイル RemoveSendPort.vbs には、実行する操作についての説明のある詳細なコメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="501c9-135">The script file RemoveSendPort.vbs contains detailed comments with further explanation about the operations that it performs.</span></span> <span data-ttu-id="501c9-136">詳細については、Windows Management Instrumentation」を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102)です。</span><span class="sxs-lookup"><span data-stu-id="501c9-136">For more information, see Windows Management Instrumentation at [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="501c9-137">参照</span><span class="sxs-lookup"><span data-stu-id="501c9-137">See Also</span></span>  
 [<span data-ttu-id="501c9-138">管理 WMI (BizTalk Server Samples フォルダ)</span><span class="sxs-lookup"><span data-stu-id="501c9-138">Admin-WMI (BizTalk Server Samples Folder)</span></span>](../core/admin-wmi-biztalk-server-samples-folder.md)