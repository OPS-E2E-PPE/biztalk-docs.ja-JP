---
title: "ターゲット Computer2 をクリーニングする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: cleaning target computer
ms.assetid: 0d25930e-0bee-4658-80e7-4a1ab4a8131d
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b15614af9a42489693d535896245254208379d76
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-clean-the-target-computer"></a><span data-ttu-id="73fd9-102">対象となるコンピューターをクリーニングする方法</span><span class="sxs-lookup"><span data-stu-id="73fd9-102">How to Clean the Target Computer</span></span>
<span data-ttu-id="73fd9-103">展開には、受信場所の構成が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="73fd9-103">Deployment overwrites the receive location configuration.</span></span> <span data-ttu-id="73fd9-104">バインド ファイル (およびアセンブリ) を展開先のコンピューターに展開すると、送信ポートと受信場所が、インポートされた XML バインド ファイルの送信ポートと受信場所に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="73fd9-104">When you deploy a binding file (and assembly) on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are imported.</span></span>  
  
### <a name="to-clean-the-target-computer"></a><span data-ttu-id="73fd9-105">展開先のコンピューターをクリーニングするには</span><span class="sxs-lookup"><span data-stu-id="73fd9-105">To clean the target computer</span></span>  
  
-   <span data-ttu-id="73fd9-106">送信ポートを削除して、受信場所をオーケストレーションにバインドされています。</span><span class="sxs-lookup"><span data-stu-id="73fd9-106">Remove any send ports and receive locations bound to the orchestration.</span></span>  
  
     <span data-ttu-id="73fd9-107">Microsoft Visual Studio が展開先のコンピューターにインストールされていない場合は、次のスクリプトを実行してポートを削除できます。</span><span class="sxs-lookup"><span data-stu-id="73fd9-107">If you do not have Microsoft Visual Studio installed on the target computer, you can remove the ports by running these scripts:</span></span>  
  
     <span data-ttu-id="73fd9-108">\<Microsoft BizTalk Server > \SDK\Samples\Admin\WMI\Remove Port\VBScript\RemoveSendPort.vbs の送信</span><span class="sxs-lookup"><span data-stu-id="73fd9-108">\<Microsoft BizTalk Server>\SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs</span></span>  
  
     <span data-ttu-id="73fd9-109">\<Microsoft BizTalk Server > \SDK\Samples\Admin\WMI\Remove Port\VBScript\RemoveReceivePort.vbs の受信</span><span class="sxs-lookup"><span data-stu-id="73fd9-109">\<Microsoft BizTalk Server>\SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs</span></span>  
  
     <span data-ttu-id="73fd9-110">たとえば、コマンド プロンプトで次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="73fd9-110">For example, at a command prompt, run:</span></span>  
  
     <span data-ttu-id="73fd9-111">**cscript RemoveSendPort.vbs\<送信ポートの名前 >**</span><span class="sxs-lookup"><span data-stu-id="73fd9-111">**cscript RemoveSendPort.vbs \<Send port name>**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73fd9-112">参照</span><span class="sxs-lookup"><span data-stu-id="73fd9-112">See Also</span></span>  
 [<span data-ttu-id="73fd9-113">ポートとアセンブリの展開</span><span class="sxs-lookup"><span data-stu-id="73fd9-113">Deploying Ports and Assemblies</span></span>](../core/deploying-ports-and-assemblies2.md)