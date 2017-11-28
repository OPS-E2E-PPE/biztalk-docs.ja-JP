---
title: "Files2 のバインドのインポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- binding files, importing
- assemblies, removing from database
- importing binding files
- target computers, cleaning
- BizTalk assemblies, removing from database
ms.assetid: 9e552a4b-06ec-4887-b17b-a625c137699f
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3783b21385c210c454bcd3d4c951f2200a6ec866
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="importing-binding-files"></a><span data-ttu-id="f8603-102">バインド ファイルのインポート</span><span class="sxs-lookup"><span data-stu-id="f8603-102">Importing Binding Files</span></span>
<span data-ttu-id="f8603-103">このトピックでは、BizTalk Adapter for JD Edwards EnterpriseOne の展開時のインポート プロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f8603-103">This topic provides some information concerning the import process when you deploy BizTalk Adapter for JD Edwards EnterpriseOne.</span></span> <span data-ttu-id="f8603-104">バインド ファイルとアセンブリを展開先のコンピューターに再展開すると、送信ポートと受信場所が、再インポートされた XML バインド ファイルの送信ポートと受信場所に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="f8603-104">When you redeploy a binding file (and assembly) on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are reimported.</span></span>  
  
### <a name="to-clean-the-target-computer"></a><span data-ttu-id="f8603-105">展開先のコンピューターをクリーニングするには</span><span class="sxs-lookup"><span data-stu-id="f8603-105">To clean the target computer</span></span>  
  
-   <span data-ttu-id="f8603-106">送信ポートを削除して、受信場所、オーケストレーションにバインドします。</span><span class="sxs-lookup"><span data-stu-id="f8603-106">Remove Send ports and Receive locations bound to the orchestration.</span></span>  
  
     <span data-ttu-id="f8603-107">Visual Studio が展開先のコンピューターにインストールされていない場合は、次のスクリプトを実行してポートを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="f8603-107">If you do not have Visual Studio installed on the target computer, you can remove the ports by running the scripts:</span></span>  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="f8603-108">SDK\Samples\Admin\WMI\\</span><span class="sxs-lookup"><span data-stu-id="f8603-108">SDK\Samples\Admin\WMI\\</span></span>  
  
     <span data-ttu-id="f8603-109">Remove Send Port\VBScript\RemoveSendPort.vbs</span><span class="sxs-lookup"><span data-stu-id="f8603-109">Remove Send Port\VBScript\RemoveSendPort.vbs</span></span>  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="f8603-110">SDK\Samples\Admin\WMI\\</span><span class="sxs-lookup"><span data-stu-id="f8603-110">SDK\Samples\Admin\WMI\\</span></span>  
  
     <span data-ttu-id="f8603-111">Remove Receive Port\VBScript\RemoveReceivePort.vbs</span><span class="sxs-lookup"><span data-stu-id="f8603-111">Remove Receive Port\VBScript\RemoveReceivePort.vbs</span></span>  
  
     <span data-ttu-id="f8603-112">たとえば、コマンド プロンプトで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f8603-112">For example, from a command prompt run:</span></span>  
  
     <span data-ttu-id="f8603-113">**cscript RemoveSendPort.vbs\<送信ポートの名前 >**</span><span class="sxs-lookup"><span data-stu-id="f8603-113">**cscript RemoveSendPort.vbs \<Send port name>**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8603-114">参照</span><span class="sxs-lookup"><span data-stu-id="f8603-114">See Also</span></span>  
 [<span data-ttu-id="f8603-115">ポートとアセンブリの展開</span><span class="sxs-lookup"><span data-stu-id="f8603-115">Deploying Ports and Assemblies</span></span>](../core/deploying-ports-and-assemblies3.md)