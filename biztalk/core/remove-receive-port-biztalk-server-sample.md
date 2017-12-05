---
title: "受信ポート (BizTalk Server サンプル) の削除 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive ports, examples
- deleting, receive ports
- examples, receive ports
- receive ports, deleting
ms.assetid: de97d914-b8e8-4365-8041-3b455c351f86
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d15442da8afd4829245b742bdd45af8f7d1f832
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="remove-receive-port-biztalk-server-sample"></a><span data-ttu-id="855d6-102">受信ポート (BizTalk Server サンプル) の削除</span><span class="sxs-lookup"><span data-stu-id="855d6-102">Remove Receive Port (BizTalk Server Sample)</span></span>
<span data-ttu-id="855d6-103">受信ポートの削除のサンプルでは、1 つ以上の受信ポートを削除する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="855d6-103">The Remove Receive Port sample demonstrates how to remove one or more receive ports.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="855d6-104">展開スクリプトは、展開後に不要になった場合は、削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="855d6-104">Deployment scripts should be removed after deployment if not needed.</span></span> <span data-ttu-id="855d6-105">保持する必要のある管理スクリプトおよび他のスクリプトは、ACL によってセキュリティで保護し、厳重に監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="855d6-105">Administration scripts and other scripts that must remain should be secured by ACL’s and closely monitored.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="855d6-106">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="855d6-106">What This Sample Does</span></span>  
 <span data-ttu-id="855d6-107">このサンプルを構成するスクリプト ファイル内の Visual Basic Scripting Edition (VBScript) スクリプトは、BizTalk Server WMI プロバイダーを使用して、次の操作を実行する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="855d6-107">The Visual Basic Scripting Edition (VBScript) script in the script file that constitutes this sample shows how to perform the following operations using the BizTalk Server WMI provider:</span></span>  
  
-   <span data-ttu-id="855d6-108">受信ポート名が指定されていることを前提として、クエリを実行し、一致する受信ポートの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="855d6-108">Given a receive port name, query for a list of matching receive ports.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="855d6-109">通常、指定された名前に一致する受信ポートは 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="855d6-109">Generally, there will only be one receive port that matches a given name.</span></span>  
  
-   <span data-ttu-id="855d6-110">取得した受信ポートを削除します。</span><span class="sxs-lookup"><span data-stu-id="855d6-110">Remove those receive ports.</span></span>  
  
-   <span data-ttu-id="855d6-111">意味のある情報がユーザーに返されるようにエラーを処理します。</span><span class="sxs-lookup"><span data-stu-id="855d6-111">Handle any errors such that meaningful information is returned to the user.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="855d6-112">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="855d6-112">Where to Find This Sample</span></span>  
 <span data-ttu-id="855d6-113">サンプルは、次の SDK の場所に配置されます。</span><span class="sxs-lookup"><span data-stu-id="855d6-113">The samples are located in the following SDK location:</span></span>  
  
 <span data-ttu-id="855d6-114">\<*パスのサンプル*\>\Admin\WMI\Remove 受信 Port\\</span><span class="sxs-lookup"><span data-stu-id="855d6-114">\<*Samples Path*\>\Admin\WMI\Remove Receive Port\\</span></span>  
  
 <span data-ttu-id="855d6-115">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="855d6-115">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="855d6-116">ファイル</span><span class="sxs-lookup"><span data-stu-id="855d6-116">File(s)</span></span>|<span data-ttu-id="855d6-117">Description</span><span class="sxs-lookup"><span data-stu-id="855d6-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="855d6-118">\VBScript フォルダー内のファイル : </span><span class="sxs-lookup"><span data-stu-id="855d6-118">In the \VBScript folder:</span></span><br /><br /> <span data-ttu-id="855d6-119">RemoveReceivePort.vbs</span><span class="sxs-lookup"><span data-stu-id="855d6-119">RemoveReceivePort.vbs</span></span>|<span data-ttu-id="855d6-120">削除する 1 つ以上の受信ポートを指定するパラメータを取る VBScript ファイル。</span><span class="sxs-lookup"><span data-stu-id="855d6-120">VBScript file that takes a parameter that specifies one or more receive ports to remove.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="855d6-121">このサンプルのビルドと初期化</span><span class="sxs-lookup"><span data-stu-id="855d6-121">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="855d6-122">受信ポートの削除のサンプルは、ビルドまたは初期化が不要な 1 つの VBScript ファイルで構成されています。</span><span class="sxs-lookup"><span data-stu-id="855d6-122">The Remove Receive Port sample consists of a single VBScript file that you do not need to build or initialize.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="855d6-123">このサンプルの実行</span><span class="sxs-lookup"><span data-stu-id="855d6-123">Running This Sample</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="855d6-124">このサンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="855d6-124">To run this sample</span></span>  
  
1.  <span data-ttu-id="855d6-125">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="855d6-125">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="855d6-126">\<*パスのサンプル*\>\Admin\WMI\Remove 受信 Port\VBScript\\</span><span class="sxs-lookup"><span data-stu-id="855d6-126">\<*Samples Path*\>\Admin\WMI\Remove Receive Port\VBScript\\</span></span>  
  
2.  <span data-ttu-id="855d6-127">cscript プログラムを使用し、次のコマンド ライン引数を渡して、ファイル RemoveReceivePort.vbs を実行します。</span><span class="sxs-lookup"><span data-stu-id="855d6-127">Run the file RemoveReceivePort.vbs using the cscript program, passing the following command-line argument:</span></span>  
  
     <span data-ttu-id="855d6-128">**\<** ***ReceivePortName* \>**です。</span><span class="sxs-lookup"><span data-stu-id="855d6-128">**\<** ***ReceivePortName* \>**.</span></span> <span data-ttu-id="855d6-129">削除する受信ポートの名前。</span><span class="sxs-lookup"><span data-stu-id="855d6-129">The name of the receive port(s) to remove.</span></span> <span data-ttu-id="855d6-130">受信ポート名に空白が含まれている場合は、名前を引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="855d6-130">If the receive port name contains spaces, enclose the name in quotes.</span></span>  
  
     <span data-ttu-id="855d6-131">例:</span><span class="sxs-lookup"><span data-stu-id="855d6-131">For example:</span></span>  
  
    ```  
    cscript RemoveReceivePort.vbs "My Business Receive Port"  
    ```  
  
## <a name="comments"></a><span data-ttu-id="855d6-132">コメント</span><span class="sxs-lookup"><span data-stu-id="855d6-132">Comments</span></span>  
 <span data-ttu-id="855d6-133">BizTalk Server 管理コンソールで実行できるすべてのタスクは、Windows WMI オブジェクト モデルにアクセスするスクリプトを使用しても実行できます。</span><span class="sxs-lookup"><span data-stu-id="855d6-133">All tasks that you can perform in the BizTalk Server Administration console can also be performed by using script that accesses the Windows WMI object model.</span></span>  
  
 <span data-ttu-id="855d6-134">スクリプト ファイル RemoveReceivePort.vbs には、実行する操作についての説明が記された詳細なコメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="855d6-134">The script file RemoveReceivePort.vbs contains detailed comments with further explanation about the operations that it performs.</span></span> <span data-ttu-id="855d6-135">詳細については、Windows Management Instrumentation」を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102)です。</span><span class="sxs-lookup"><span data-stu-id="855d6-135">For more information, see Windows Management Instrumentation at [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="855d6-136">参照</span><span class="sxs-lookup"><span data-stu-id="855d6-136">See Also</span></span>  
 [<span data-ttu-id="855d6-137">Admin-WMI (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="855d6-137">Admin-WMI (BizTalk Server Samples Folder)</span></span>](../core/admin-wmi-biztalk-server-samples-folder.md)