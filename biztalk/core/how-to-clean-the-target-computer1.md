---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-tibco-rendezvous/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: f4f0645e5bb6c497a35771c18c9635fcaf2cff78
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386998"
---
# <a name="how-to-clean-the-target-computer"></a><span data-ttu-id="437d0-101">対象のコンピューターをクリーニングする方法</span><span class="sxs-lookup"><span data-stu-id="437d0-101">How to Clean the Target Computer</span></span>
<span data-ttu-id="437d0-102">展開には、受信場所の構成が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="437d0-102">Deployment overwrites the receive location configuration.</span></span> <span data-ttu-id="437d0-103">バインド ファイル (およびアセンブリ) をターゲット コンピューターに展開すると、送信ポートと受信場所が、インポートされた XML バインド ファイルの送信ポートと受信場所に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="437d0-103">When you deploy a binding file (and assembly) on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are imported.</span></span>  
  
### <a name="to-clean-the-target-computer"></a><span data-ttu-id="437d0-104">ターゲット コンピューターをクリーニングするには</span><span class="sxs-lookup"><span data-stu-id="437d0-104">To clean the target computer</span></span>  
  
- <span data-ttu-id="437d0-105">送信ポートを削除して、受信、オーケストレーションにバインドされている場所。</span><span class="sxs-lookup"><span data-stu-id="437d0-105">Remove send ports and receive locations bound to the orchestration.</span></span>  
  
   <span data-ttu-id="437d0-106">Microsoft Visual Studio がターゲット コンピューターにインストールされていない場合は、次のスクリプトを実行してポートを削除できます。</span><span class="sxs-lookup"><span data-stu-id="437d0-106">If you do not have Microsoft Visual Studio installed on the target computer, you can remove the ports by running these scripts:</span></span>  
  
  - [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="437d0-107">SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs</span><span class="sxs-lookup"><span data-stu-id="437d0-107">SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs</span></span>  
  
  - [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="437d0-108">SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs</span><span class="sxs-lookup"><span data-stu-id="437d0-108">SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs</span></span>  
  
     <span data-ttu-id="437d0-109">たとえば、コマンド プロンプトで次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="437d0-109">For example, at a command prompt, run:</span></span>  
  
     <span data-ttu-id="437d0-110">**cscript RemoveSendPort.vbs\<送信ポートの名前\>**</span><span class="sxs-lookup"><span data-stu-id="437d0-110">**cscript RemoveSendPort.vbs \<Send port name\>**</span></span>  
  
