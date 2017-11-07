---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-tibco-enterprise-message-service/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: 93cb3a1420b60183ff42108c32224cf4707b9cd7
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="how-to-clean-the-target-computer"></a><span data-ttu-id="96254-101">対象となるコンピューターをクリーニングする方法</span><span class="sxs-lookup"><span data-stu-id="96254-101">How to Clean the Target Computer</span></span>
<span data-ttu-id="96254-102">展開には、受信場所の構成が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="96254-102">Deployment overwrites the receive location configuration.</span></span> <span data-ttu-id="96254-103">バインド ファイル (およびアセンブリ) を展開先のコンピューターに展開すると、送信ポートと受信場所が、インポートされた XML バインド ファイルの送信ポートと受信場所に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="96254-103">When you deploy a binding file (and assembly) on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are imported.</span></span>  
  
### <a name="to-clean-the-target-computer"></a><span data-ttu-id="96254-104">展開先のコンピューターをクリーニングするには</span><span class="sxs-lookup"><span data-stu-id="96254-104">To clean the target computer</span></span>  
  
-   <span data-ttu-id="96254-105">送信ポートを削除して、受信場所をオーケストレーションにバインドされています。</span><span class="sxs-lookup"><span data-stu-id="96254-105">Remove any send ports and receive locations bound to the orchestration.</span></span>  
  
     <span data-ttu-id="96254-106">Microsoft Visual Studio が展開先のコンピューターにインストールされていない場合は、次のスクリプトを実行してポートを削除できます。</span><span class="sxs-lookup"><span data-stu-id="96254-106">If you do not have Microsoft Visual Studio installed on the target computer, you can remove the ports by running these scripts:</span></span>  
  
     <span data-ttu-id="96254-107">\<Microsoft BizTalk Server > \SDK\Samples\Admin\WMI\Remove Port\VBScript\RemoveSendPort.vbs の送信</span><span class="sxs-lookup"><span data-stu-id="96254-107">\<Microsoft BizTalk Server>\SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs</span></span>  
  
     <span data-ttu-id="96254-108">\<Microsoft BizTalk Server > \SDK\Samples\Admin\WMI\Remove Port\VBScript\RemoveReceivePort.vbs の受信</span><span class="sxs-lookup"><span data-stu-id="96254-108">\<Microsoft BizTalk Server>\SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs</span></span>  
  
     <span data-ttu-id="96254-109">たとえば、コマンド プロンプトで次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="96254-109">For example, at a command prompt, run:</span></span>  
  
     <span data-ttu-id="96254-110">**cscript RemoveSendPort.vbs\<送信ポートの名前 >**</span><span class="sxs-lookup"><span data-stu-id="96254-110">**cscript RemoveSendPort.vbs \<Send port name>**</span></span>  
  
