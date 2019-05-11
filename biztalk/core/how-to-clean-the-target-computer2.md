---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-tibco-enterprise-message-service/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 936f25f9dda62cf881b4539a0eee475118294f95
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342386"
---
# <a name="how-to-clean-the-target-computer"></a><span data-ttu-id="f0388-101">対象のコンピューターをクリーニングする方法</span><span class="sxs-lookup"><span data-stu-id="f0388-101">How to Clean the Target Computer</span></span>
<span data-ttu-id="f0388-102">展開には、受信場所の構成が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="f0388-102">Deployment overwrites the receive location configuration.</span></span> <span data-ttu-id="f0388-103">バインド ファイル (およびアセンブリ) をターゲット コンピューターに展開すると、送信ポートと受信場所が、インポートされた XML バインド ファイルの送信ポートと受信場所に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="f0388-103">When you deploy a binding file (and assembly) on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are imported.</span></span>  
  
### <a name="to-clean-the-target-computer"></a><span data-ttu-id="f0388-104">ターゲット コンピューターをクリーニングするには</span><span class="sxs-lookup"><span data-stu-id="f0388-104">To clean the target computer</span></span>  
  
-   <span data-ttu-id="f0388-105">送信ポートを削除して、受信場所がオーケストレーションにバインドされています。</span><span class="sxs-lookup"><span data-stu-id="f0388-105">Remove any send ports and receive locations bound to the orchestration.</span></span>  
  
     <span data-ttu-id="f0388-106">Microsoft Visual Studio がターゲット コンピューターにインストールされていない場合は、次のスクリプトを実行してポートを削除できます。</span><span class="sxs-lookup"><span data-stu-id="f0388-106">If you do not have Microsoft Visual Studio installed on the target computer, you can remove the ports by running these scripts:</span></span>  
  
     <span data-ttu-id="f0388-107">\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove Port\VBScript\RemoveSendPort.vbs を送信します。</span><span class="sxs-lookup"><span data-stu-id="f0388-107">\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs</span></span>  
  
     <span data-ttu-id="f0388-108">\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove Port\VBScript\RemoveReceivePort.vbs の受信</span><span class="sxs-lookup"><span data-stu-id="f0388-108">\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs</span></span>  
  
     <span data-ttu-id="f0388-109">たとえば、コマンド プロンプトで次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="f0388-109">For example, at a command prompt, run:</span></span>  
  
     <span data-ttu-id="f0388-110">**cscript RemoveSendPort.vbs\<送信ポートの名前\>**</span><span class="sxs-lookup"><span data-stu-id="f0388-110">**cscript RemoveSendPort.vbs \<Send port name\>**</span></span>  
  
