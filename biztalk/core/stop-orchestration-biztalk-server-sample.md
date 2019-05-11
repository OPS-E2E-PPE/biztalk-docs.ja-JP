---
title: オーケストレーションの停止 (BizTalk Server サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- examples, orchestrations
- orchestrations, stopping
ms.assetid: 83be44e9-819d-4ac5-8b75-84c23e6b5ba2
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5f6294442311f2644f6f0bc7efd2261af7712c1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244162"
---
# <a name="stop-orchestration-biztalk-server-sample"></a><span data-ttu-id="1ebd0-102">オーケストレーションの停止 (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="1ebd0-102">Stop Orchestration (BizTalk Server Sample)</span></span>
<span data-ttu-id="1ebd0-103">オーケストレーションの停止サンプルでは、BizTalk Server オーケストレーションを停止し、必要に応じて参加を解除します。</span><span class="sxs-lookup"><span data-stu-id="1ebd0-103">The Stop Orchestration sample demonstrates how to stop a BizTalk Server orchestration and, optionally, to unenlist it.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="1ebd0-104">展開スクリプトは、展開後に不要になった場合は、削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ebd0-104">Deployment scripts should be removed after deployment if not needed.</span></span> <span data-ttu-id="1ebd0-105">保持する必要のある管理スクリプトおよび他のスクリプトは、ACL によってセキュリティで保護し、厳重に監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ebd0-105">Administration scripts and other scripts that must remain should be secured by ACL’s and closely monitored.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="1ebd0-106">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="1ebd0-106">What This Sample Does</span></span>  
 <span data-ttu-id="1ebd0-107">このサンプルを構成するスクリプト ファイル内の Visual Basic Scripting Edition (VBScript) スクリプトは、BizTalk Server WMI プロバイダーを使用して、次の操作を実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1ebd0-107">The Visual Basic Scripting Edition (VBScript) script in the script file that constitutes this sample shows how to perform the following operations using the BizTalk Server WMI provider:</span></span>  
  
-   <span data-ttu-id="1ebd0-108">オーケストレーション名とアセンブリ名を指定するには、特定のクエリには、BizTalk Server オーケストレーションが展開されています。</span><span class="sxs-lookup"><span data-stu-id="1ebd0-108">Given an orchestration name and an assembly name, query for a specific deployed BizTalk Server orchestration.</span></span>  
  
-   <span data-ttu-id="1ebd0-109">そのオーケストレーションを停止します。</span><span class="sxs-lookup"><span data-stu-id="1ebd0-109">Stop that orchestration.</span></span>  
  
-   <span data-ttu-id="1ebd0-110">(省略可能)、そのオーケストレーションを参加解除します。</span><span class="sxs-lookup"><span data-stu-id="1ebd0-110">Unenlist that orchestration (optionally).</span></span>  
  
-   <span data-ttu-id="1ebd0-111">意味のある情報がユーザーに返されるようにエラーを処理します。</span><span class="sxs-lookup"><span data-stu-id="1ebd0-111">Handle any errors such that meaningful information is returned to the user.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="1ebd0-112">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="1ebd0-112">Where to Find This Sample</span></span>  
 <span data-ttu-id="1ebd0-113">サンプル ファイルは、次の SDK の場所に配置されます。</span><span class="sxs-lookup"><span data-stu-id="1ebd0-113">The sample files are located in the following SDK location:</span></span>  
  
 <span data-ttu-id="1ebd0-114">\<*パスのサンプル*\>\Admin\WMI\Stop Orchestration\\</span><span class="sxs-lookup"><span data-stu-id="1ebd0-114">\<*Samples Path*\>\Admin\WMI\Stop Orchestration\\</span></span>  
  
 <span data-ttu-id="1ebd0-115">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="1ebd0-115">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="1ebd0-116">ファイル</span><span class="sxs-lookup"><span data-stu-id="1ebd0-116">File(s)</span></span>|<span data-ttu-id="1ebd0-117">説明</span><span class="sxs-lookup"><span data-stu-id="1ebd0-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1ebd0-118">\VBScript フォルダー。</span><span class="sxs-lookup"><span data-stu-id="1ebd0-118">In the \VBScript folder:</span></span><br /><br /> <span data-ttu-id="1ebd0-119">StopOrch.vbs</span><span class="sxs-lookup"><span data-stu-id="1ebd0-119">StopOrch.vbs</span></span>|<span data-ttu-id="1ebd0-120">オーケストレーションが停止し、必要に応じて、参加解除の対象を指定するパラメータを受け取る VBScript ファイル。</span><span class="sxs-lookup"><span data-stu-id="1ebd0-120">VBScript file that takes parameters to specify an orchestration to be stopped and, optionally, unenlisted.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="1ebd0-121">このサンプルのビルドと初期化</span><span class="sxs-lookup"><span data-stu-id="1ebd0-121">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="1ebd0-122">オーケストレーションの停止のサンプルは、ビルドまたは初期化する必要はありませんが、1 つの VBScript ファイルで構成されます。</span><span class="sxs-lookup"><span data-stu-id="1ebd0-122">The Stop Orchestration sample consists of a single VBScript file that you do not need to build or initialize.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="1ebd0-123">このサンプルの実行</span><span class="sxs-lookup"><span data-stu-id="1ebd0-123">Running This Sample</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="1ebd0-124">このサンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="1ebd0-124">To run this sample</span></span>  
  
1.  <span data-ttu-id="1ebd0-125">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="1ebd0-125">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="1ebd0-126">\<*パスのサンプル*\>\Admin\WMI\Stop Orchestration\VBScript\\</span><span class="sxs-lookup"><span data-stu-id="1ebd0-126">\<*Samples Path*\>\Admin\WMI\Stop Orchestration\VBScript\\</span></span>  
  
2.  <span data-ttu-id="1ebd0-127">ファイル StopOrch.vbs cscript プログラムを使用して、3 つ目は省略可能ですが、次のコマンドライン引数を渡すことを実行します。</span><span class="sxs-lookup"><span data-stu-id="1ebd0-127">Run the file StopOrch.vbs using the cscript program, passing the following command-line arguments, of which the third one is optional:</span></span>  
  
    -   <span data-ttu-id="1ebd0-128">**\<** ***OrchestrationName* \>.**</span><span class="sxs-lookup"><span data-stu-id="1ebd0-128">**\<** ***OrchestrationName* \>.**</span></span> <span data-ttu-id="1ebd0-129">BizTalk Server オーケストレーションを停止して、必要に応じて、参加解除の対象の名前。</span><span class="sxs-lookup"><span data-stu-id="1ebd0-129">The name of the BizTalk Server orchestration to be stopped and, optionally, unenlisted.</span></span>  
  
    -   <span data-ttu-id="1ebd0-130">**\<** ***AssemblyName* \>.**</span><span class="sxs-lookup"><span data-stu-id="1ebd0-130">**\<** ***AssemblyName* \>.**</span></span> <span data-ttu-id="1ebd0-131">特定のオーケストレーションが展開されている BizTalk アセンブリの名前。</span><span class="sxs-lookup"><span data-stu-id="1ebd0-131">The name of the BizTalk assembly in which the specified orchestration was deployed.</span></span> <span data-ttu-id="1ebd0-132">アセンブリ名に空白が含まれている場合は、名前を引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="1ebd0-132">If the assembly name contains spaces, enclose the name in quotes.</span></span>  
  
    -   <span data-ttu-id="1ebd0-133">**参加を解除します。**</span><span class="sxs-lookup"><span data-stu-id="1ebd0-133">**Unenlist.**</span></span> <span data-ttu-id="1ebd0-134">省略可能なリテラル文字列、特定のオーケストレーションを停止および参加する必要があるように指定するために使用します。</span><span class="sxs-lookup"><span data-stu-id="1ebd0-134">An optional, literal string used to indicate that the specified orchestration should be unenlisted in addition to being stopped.</span></span>  
  
         <span data-ttu-id="1ebd0-135">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="1ebd0-135">For example:</span></span>  
  
        ```  
        cscript StopOrch.vbs MyBusinessOrchestration "My Business Assembly"  
        ```  
  
         <span data-ttu-id="1ebd0-136">-または-</span><span class="sxs-lookup"><span data-stu-id="1ebd0-136">-OR-</span></span>  
  
        ```  
        cscript StopOrch.vbs MyBusinessOrchestration MyBusinessAssembly Unenlist  
        ```  
  
## <a name="comments"></a><span data-ttu-id="1ebd0-137">コメント</span><span class="sxs-lookup"><span data-stu-id="1ebd0-137">Comments</span></span>  
 <span data-ttu-id="1ebd0-138">BizTalk Server 管理コンソールで実行できるすべてのタスクは、Windows WMI オブジェクト モデルにアクセスするスクリプトを使用しても実行できます。</span><span class="sxs-lookup"><span data-stu-id="1ebd0-138">All tasks that you can perform in the BizTalk Server Administration console can also be performed by using scripts that access the Windows WMI object model.</span></span>  
  
 <span data-ttu-id="1ebd0-139">スクリプト ファイル StopOrch.vbs には、詳細なコメントが、実行する操作についての説明が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1ebd0-139">The script file StopOrch.vbs contains detailed comments with further explanation about the operations that it performs.</span></span> <span data-ttu-id="1ebd0-140">詳細については、Windows Management Instrumentation を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102)します。</span><span class="sxs-lookup"><span data-stu-id="1ebd0-140">For more information, see Windows Management Instrumentation at [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ebd0-141">参照</span><span class="sxs-lookup"><span data-stu-id="1ebd0-141">See Also</span></span>  
 [<span data-ttu-id="1ebd0-142">Admin-WMI (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="1ebd0-142">Admin-WMI (BizTalk Server Samples Folder)</span></span>](../core/admin-wmi-biztalk-server-samples-folder.md)