---
title: 受信ポート (BizTalk Server サンプル) の削除 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive ports, examples
- deleting, receive ports
- examples, receive ports
- receive ports, deleting
ms.assetid: de97d914-b8e8-4365-8041-3b455c351f86
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f39d8264e00b239eaffbb24fb53e3a0f99998720
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397943"
---
# <a name="remove-receive-port-biztalk-server-sample"></a><span data-ttu-id="7842f-102">受信ポート (BizTalk Server サンプル) の削除</span><span class="sxs-lookup"><span data-stu-id="7842f-102">Remove Receive Port (BizTalk Server Sample)</span></span>
<span data-ttu-id="7842f-103">以上の受信ポートや受信ポートの削除のサンプルが 1 つを削除する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7842f-103">The Remove Receive Port sample demonstrates how to remove one or more receive ports.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="7842f-104">展開スクリプトは、展開後に不要になった場合は、削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7842f-104">Deployment scripts should be removed after deployment if not needed.</span></span> <span data-ttu-id="7842f-105">保持する必要のある管理スクリプトおよび他のスクリプトは、ACL によってセキュリティで保護し、厳重に監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7842f-105">Administration scripts and other scripts that must remain should be secured by ACL’s and closely monitored.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="7842f-106">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="7842f-106">What This Sample Does</span></span>  
 <span data-ttu-id="7842f-107">このサンプルを構成するスクリプト ファイル内の Visual Basic Scripting Edition (VBScript) スクリプトは、BizTalk Server WMI プロバイダーを使用して、次の操作を実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7842f-107">The Visual Basic Scripting Edition (VBScript) script in the script file that constitutes this sample shows how to perform the following operations using the BizTalk Server WMI provider:</span></span>  
  
-   <span data-ttu-id="7842f-108">受信ポート名、一致する受信ポートの一覧については、クエリを指定します。</span><span class="sxs-lookup"><span data-stu-id="7842f-108">Given a receive port name, query for a list of matching receive ports.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7842f-109">一般に、あるは 1 つだけ指定した名前に一致するポートを受信します。</span><span class="sxs-lookup"><span data-stu-id="7842f-109">Generally, there will only be one receive port that matches a given name.</span></span>  
  
-   <span data-ttu-id="7842f-110">削除された受信ポート。</span><span class="sxs-lookup"><span data-stu-id="7842f-110">Remove those receive ports.</span></span>  
  
-   <span data-ttu-id="7842f-111">意味のある情報がユーザーに返されるようにエラーを処理します。</span><span class="sxs-lookup"><span data-stu-id="7842f-111">Handle any errors such that meaningful information is returned to the user.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="7842f-112">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="7842f-112">Where to Find This Sample</span></span>  
 <span data-ttu-id="7842f-113">サンプルは、次の SDK の場所に配置されます。</span><span class="sxs-lookup"><span data-stu-id="7842f-113">The samples are located in the following SDK location:</span></span>  
  
 <span data-ttu-id="7842f-114">\<*パスのサンプル*\>\Admin\WMI\Remove Port\ の受信</span><span class="sxs-lookup"><span data-stu-id="7842f-114">\<*Samples Path*\>\Admin\WMI\Remove Receive Port\\</span></span>  
  
 <span data-ttu-id="7842f-115">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="7842f-115">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="7842f-116">ファイル</span><span class="sxs-lookup"><span data-stu-id="7842f-116">File(s)</span></span>|<span data-ttu-id="7842f-117">説明</span><span class="sxs-lookup"><span data-stu-id="7842f-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7842f-118">\VBScript フォルダー。</span><span class="sxs-lookup"><span data-stu-id="7842f-118">In the \VBScript folder:</span></span><br /><br /> <span data-ttu-id="7842f-119">RemoveReceivePort.vbs</span><span class="sxs-lookup"><span data-stu-id="7842f-119">RemoveReceivePort.vbs</span></span>|<span data-ttu-id="7842f-120">1 つまたは複数を指定するパラメーターを取る VBScript ファイルの受信ポートを削除します。</span><span class="sxs-lookup"><span data-stu-id="7842f-120">VBScript file that takes a parameter that specifies one or more receive ports to remove.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="7842f-121">このサンプルのビルドと初期化</span><span class="sxs-lookup"><span data-stu-id="7842f-121">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="7842f-122">受信ポートの削除のサンプルは、ビルドまたは初期化する必要はありませんが、1 つの VBScript ファイルで構成されます。</span><span class="sxs-lookup"><span data-stu-id="7842f-122">The Remove Receive Port sample consists of a single VBScript file that you do not need to build or initialize.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="7842f-123">このサンプルの実行</span><span class="sxs-lookup"><span data-stu-id="7842f-123">Running This Sample</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="7842f-124">このサンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="7842f-124">To run this sample</span></span>  
  
1.  <span data-ttu-id="7842f-125">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="7842f-125">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="7842f-126">\<*パスのサンプル*\>\Admin\WMI\Remove Port\VBScript\ の受信</span><span class="sxs-lookup"><span data-stu-id="7842f-126">\<*Samples Path*\>\Admin\WMI\Remove Receive Port\VBScript\\</span></span>  
  
2.  <span data-ttu-id="7842f-127">ファイル RemoveReceivePort.vbs cscript プログラムを使用して、次のコマンドライン引数を渡して実行します。</span><span class="sxs-lookup"><span data-stu-id="7842f-127">Run the file RemoveReceivePort.vbs using the cscript program, passing the following command-line argument:</span></span>  
  
     <span data-ttu-id="7842f-128">**\<** ***ReceivePortName* \>** します。</span><span class="sxs-lookup"><span data-stu-id="7842f-128">**\<** ***ReceivePortName* \>**.</span></span> <span data-ttu-id="7842f-129">削除する受信ポートの名前。</span><span class="sxs-lookup"><span data-stu-id="7842f-129">The name of the receive port(s) to remove.</span></span> <span data-ttu-id="7842f-130">受信ポート名にスペースが含まれている場合は、名前を引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="7842f-130">If the receive port name contains spaces, enclose the name in quotes.</span></span>  
  
     <span data-ttu-id="7842f-131">例 :</span><span class="sxs-lookup"><span data-stu-id="7842f-131">For example:</span></span>  
  
    ```  
    cscript RemoveReceivePort.vbs "My Business Receive Port"  
    ```  
  
## <a name="comments"></a><span data-ttu-id="7842f-132">コメント</span><span class="sxs-lookup"><span data-stu-id="7842f-132">Comments</span></span>  
 <span data-ttu-id="7842f-133">BizTalk Server 管理コンソールで実行できるすべてのタスクは、Windows WMI オブジェクト モデルにアクセスするスクリプトを使用しても実行できます。</span><span class="sxs-lookup"><span data-stu-id="7842f-133">All tasks that you can perform in the BizTalk Server Administration console can also be performed by using script that accesses the Windows WMI object model.</span></span>  
  
 <span data-ttu-id="7842f-134">スクリプト ファイル RemoveReceivePort.vbs には、詳細なコメントが、実行する操作についての説明が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7842f-134">The script file RemoveReceivePort.vbs contains detailed comments with further explanation about the operations that it performs.</span></span> <span data-ttu-id="7842f-135">詳細については、Windows Management Instrumentation を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102)します。</span><span class="sxs-lookup"><span data-stu-id="7842f-135">For more information, see Windows Management Instrumentation at [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7842f-136">参照</span><span class="sxs-lookup"><span data-stu-id="7842f-136">See Also</span></span>  
 [<span data-ttu-id="7842f-137">Admin-WMI (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="7842f-137">Admin-WMI (BizTalk Server Samples Folder)</span></span>](../core/admin-wmi-biztalk-server-samples-folder.md)