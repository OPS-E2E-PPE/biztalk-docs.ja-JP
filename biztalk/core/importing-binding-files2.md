---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 7dbc9ef8624404b9fa7bdcb7b6a21b2d2a4c69f2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25971248"
---
# <a name="importing-binding-files"></a><span data-ttu-id="e0f94-101">バインド ファイルのインポート</span><span class="sxs-lookup"><span data-stu-id="e0f94-101">Importing Binding Files</span></span>
<span data-ttu-id="e0f94-102">このトピックでは、BizTalk Adapter for JD Edwards EnterpriseOne の展開時のインポート プロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e0f94-102">This topic provides some information concerning the import process when you deploy BizTalk Adapter for JD Edwards EnterpriseOne.</span></span> <span data-ttu-id="e0f94-103">バインド ファイルとアセンブリを展開先のコンピューターに再展開すると、送信ポートと受信場所が、再インポートされた XML バインド ファイルの送信ポートと受信場所に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="e0f94-103">When you redeploy a binding file (and assembly) on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are reimported.</span></span>  
  
### <a name="to-clean-the-target-computer"></a><span data-ttu-id="e0f94-104">展開先のコンピューターをクリーニングするには</span><span class="sxs-lookup"><span data-stu-id="e0f94-104">To clean the target computer</span></span>  
  
-   <span data-ttu-id="e0f94-105">送信ポートを削除して、受信場所、オーケストレーションにバインドします。</span><span class="sxs-lookup"><span data-stu-id="e0f94-105">Remove Send ports and Receive locations bound to the orchestration.</span></span>  
  
     <span data-ttu-id="e0f94-106">Visual Studio が展開先のコンピューターにインストールされていない場合は、次のスクリプトを実行してポートを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="e0f94-106">If you do not have Visual Studio installed on the target computer, you can remove the ports by running the scripts:</span></span>  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="e0f94-107">SDK\Samples\Admin\WMI\\</span><span class="sxs-lookup"><span data-stu-id="e0f94-107">SDK\Samples\Admin\WMI\\</span></span>  
  
     <span data-ttu-id="e0f94-108">Remove Send Port\VBScript\RemoveSendPort.vbs</span><span class="sxs-lookup"><span data-stu-id="e0f94-108">Remove Send Port\VBScript\RemoveSendPort.vbs</span></span>  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="e0f94-109">SDK\Samples\Admin\WMI\\</span><span class="sxs-lookup"><span data-stu-id="e0f94-109">SDK\Samples\Admin\WMI\\</span></span>  
  
     <span data-ttu-id="e0f94-110">Remove Receive Port\VBScript\RemoveReceivePort.vbs</span><span class="sxs-lookup"><span data-stu-id="e0f94-110">Remove Receive Port\VBScript\RemoveReceivePort.vbs</span></span>  
  
     <span data-ttu-id="e0f94-111">たとえば、コマンド プロンプトで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e0f94-111">For example, from a command prompt run:</span></span>  
  
     <span data-ttu-id="e0f94-112">**cscript RemoveSendPort.vbs\<送信ポートの名前\>**</span><span class="sxs-lookup"><span data-stu-id="e0f94-112">**cscript RemoveSendPort.vbs \<Send port name\>**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0f94-113">参照</span><span class="sxs-lookup"><span data-stu-id="e0f94-113">See Also</span></span>  
 [<span data-ttu-id="e0f94-114">インポート JD Edwards EnterpriseOne アプリケーション</span><span class="sxs-lookup"><span data-stu-id="e0f94-114">Import the JD Edwards EnterpriseOne app</span></span>](../core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone.md)