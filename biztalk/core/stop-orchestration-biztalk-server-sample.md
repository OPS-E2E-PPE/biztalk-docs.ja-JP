---
title: オーケストレーション (BizTalk Server サンプル) を停止 |Microsoft ドキュメント
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
ms.openlocfilehash: 8b0c88bdeb85b8ad493b85d2569061c35bd516e1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973896"
---
# <a name="stop-orchestration-biztalk-server-sample"></a><span data-ttu-id="493f0-102">オーケストレーション (BizTalk Server サンプル) を停止します。</span><span class="sxs-lookup"><span data-stu-id="493f0-102">Stop Orchestration (BizTalk Server Sample)</span></span>
<span data-ttu-id="493f0-103">オーケストレーションの停止のサンプルは、BizTalk Server オーケストレーションの停止方法および参加解除方法 (オプション) を示しています。</span><span class="sxs-lookup"><span data-stu-id="493f0-103">The Stop Orchestration sample demonstrates how to stop a BizTalk Server orchestration and, optionally, to unenlist it.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="493f0-104">展開スクリプトは、展開後に不要になった場合は、削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="493f0-104">Deployment scripts should be removed after deployment if not needed.</span></span> <span data-ttu-id="493f0-105">保持する必要のある管理スクリプトおよび他のスクリプトは、ACL によってセキュリティで保護し、厳重に監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="493f0-105">Administration scripts and other scripts that must remain should be secured by ACL’s and closely monitored.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="493f0-106">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="493f0-106">What This Sample Does</span></span>  
 <span data-ttu-id="493f0-107">このサンプルを構成するスクリプト ファイル内の Visual Basic Scripting Edition (VBScript) スクリプトは、BizTalk Server WMI プロバイダーを使用して、次の操作を実行する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="493f0-107">The Visual Basic Scripting Edition (VBScript) script in the script file that constitutes this sample shows how to perform the following operations using the BizTalk Server WMI provider:</span></span>  
  
-   <span data-ttu-id="493f0-108">オーケストレーション名とアセンブリ名を受け取ると、展開された特定の BizTalk Server オーケストレーションに対するクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="493f0-108">Given an orchestration name and an assembly name, query for a specific deployed BizTalk Server orchestration.</span></span>  
  
-   <span data-ttu-id="493f0-109">そのオーケストレーションを停止します。</span><span class="sxs-lookup"><span data-stu-id="493f0-109">Stop that orchestration.</span></span>  
  
-   <span data-ttu-id="493f0-110">オーケストレーションを参加解除します (オプション)。</span><span class="sxs-lookup"><span data-stu-id="493f0-110">Unenlist that orchestration (optionally).</span></span>  
  
-   <span data-ttu-id="493f0-111">意味のある情報がユーザーに返されるようにエラーを処理します。</span><span class="sxs-lookup"><span data-stu-id="493f0-111">Handle any errors such that meaningful information is returned to the user.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="493f0-112">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="493f0-112">Where to Find This Sample</span></span>  
 <span data-ttu-id="493f0-113">このサンプル ファイルは、次の SDK の場所にあります。</span><span class="sxs-lookup"><span data-stu-id="493f0-113">The sample files are located in the following SDK location:</span></span>  
  
 <span data-ttu-id="493f0-114">\<*パスのサンプル*\>\Admin\WMI\Stop Orchestration\\</span><span class="sxs-lookup"><span data-stu-id="493f0-114">\<*Samples Path*\>\Admin\WMI\Stop Orchestration\\</span></span>  
  
 <span data-ttu-id="493f0-115">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="493f0-115">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="493f0-116">ファイル</span><span class="sxs-lookup"><span data-stu-id="493f0-116">File(s)</span></span>|<span data-ttu-id="493f0-117">Description</span><span class="sxs-lookup"><span data-stu-id="493f0-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="493f0-118">\VBScript フォルダー内のファイル : </span><span class="sxs-lookup"><span data-stu-id="493f0-118">In the \VBScript folder:</span></span><br /><br /> <span data-ttu-id="493f0-119">StopOrch.vbs</span><span class="sxs-lookup"><span data-stu-id="493f0-119">StopOrch.vbs</span></span>|<span data-ttu-id="493f0-120">停止および参加解除 (オプション) の対象となるオーケストレーションを指定するパラメータを取る VBScript ファイル。</span><span class="sxs-lookup"><span data-stu-id="493f0-120">VBScript file that takes parameters to specify an orchestration to be stopped and, optionally, unenlisted.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="493f0-121">このサンプルのビルドと初期化</span><span class="sxs-lookup"><span data-stu-id="493f0-121">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="493f0-122">オーケストレーションの停止のサンプルは、構築または初期化が不要な 1 つの VBScript ファイルで構成されます。</span><span class="sxs-lookup"><span data-stu-id="493f0-122">The Stop Orchestration sample consists of a single VBScript file that you do not need to build or initialize.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="493f0-123">このサンプルの実行</span><span class="sxs-lookup"><span data-stu-id="493f0-123">Running This Sample</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="493f0-124">このサンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="493f0-124">To run this sample</span></span>  
  
1.  <span data-ttu-id="493f0-125">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="493f0-125">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="493f0-126">\<*パスのサンプル*\>\Admin\WMI\Stop Orchestration\VBScript\\</span><span class="sxs-lookup"><span data-stu-id="493f0-126">\<*Samples Path*\>\Admin\WMI\Stop Orchestration\VBScript\\</span></span>  
  
2.  <span data-ttu-id="493f0-127">cscript プログラムを使用し、次のコマンド ライン引数 (3 番目はオプション) を渡して、ファイル StopOrch.vbs を実行します。</span><span class="sxs-lookup"><span data-stu-id="493f0-127">Run the file StopOrch.vbs using the cscript program, passing the following command-line arguments, of which the third one is optional:</span></span>  
  
    -   <span data-ttu-id="493f0-128">**\<** ***OrchestrationName* \>です。**</span><span class="sxs-lookup"><span data-stu-id="493f0-128">**\<** ***OrchestrationName* \>.**</span></span> <span data-ttu-id="493f0-129">停止および参加解除 (オプション) の対象となる BizTalk Server オーケストレーションの名前。</span><span class="sxs-lookup"><span data-stu-id="493f0-129">The name of the BizTalk Server orchestration to be stopped and, optionally, unenlisted.</span></span>  
  
    -   <span data-ttu-id="493f0-130">**\<** ***AssemblyName* \>です。**</span><span class="sxs-lookup"><span data-stu-id="493f0-130">**\<** ***AssemblyName* \>.**</span></span> <span data-ttu-id="493f0-131">特定のオーケストレーションが展開された BizTalk アセンブリの名前。</span><span class="sxs-lookup"><span data-stu-id="493f0-131">The name of the BizTalk assembly in which the specified orchestration was deployed.</span></span> <span data-ttu-id="493f0-132">アセンブリ名に空白が含まれている場合は、名前を引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="493f0-132">If the assembly name contains spaces, enclose the name in quotes.</span></span>  
  
    -   <span data-ttu-id="493f0-133">**参加を解除します。**</span><span class="sxs-lookup"><span data-stu-id="493f0-133">**Unenlist.**</span></span> <span data-ttu-id="493f0-134">オプションの文字列で、特定のオーケストレーションを停止および参加解除する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="493f0-134">An optional, literal string used to indicate that the specified orchestration should be unenlisted in addition to being stopped.</span></span>  
  
         <span data-ttu-id="493f0-135">例:</span><span class="sxs-lookup"><span data-stu-id="493f0-135">For example:</span></span>  
  
        ```  
        cscript StopOrch.vbs MyBusinessOrchestration "My Business Assembly"  
        ```  
  
         <span data-ttu-id="493f0-136">- または -</span><span class="sxs-lookup"><span data-stu-id="493f0-136">-OR-</span></span>  
  
        ```  
        cscript StopOrch.vbs MyBusinessOrchestration MyBusinessAssembly Unenlist  
        ```  
  
## <a name="comments"></a><span data-ttu-id="493f0-137">コメント</span><span class="sxs-lookup"><span data-stu-id="493f0-137">Comments</span></span>  
 <span data-ttu-id="493f0-138">BizTalk Server 管理コンソールで実行できるすべてのタスクは、Windows WMI オブジェクト モデルにアクセスするスクリプトを使用して実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="493f0-138">All tasks that you can perform in the BizTalk Server Administration console can also be performed by using scripts that access the Windows WMI object model.</span></span>  
  
 <span data-ttu-id="493f0-139">スクリプト ファイル StopOrch.vbs には、実行する操作について説明する詳細なコメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="493f0-139">The script file StopOrch.vbs contains detailed comments with further explanation about the operations that it performs.</span></span> <span data-ttu-id="493f0-140">詳細については、Windows Management Instrumentation」を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102)です。</span><span class="sxs-lookup"><span data-stu-id="493f0-140">For more information, see Windows Management Instrumentation at [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="493f0-141">参照</span><span class="sxs-lookup"><span data-stu-id="493f0-141">See Also</span></span>  
 [<span data-ttu-id="493f0-142">Admin-WMI (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="493f0-142">Admin-WMI (BizTalk Server Samples Folder)</span></span>](../core/admin-wmi-biztalk-server-samples-folder.md)