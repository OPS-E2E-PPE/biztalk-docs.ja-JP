---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-peoplesoft-enterprise/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: 8a2b78ee2e8ec75c6ce83a8b78d1e779f012f324
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="import-binding-files"></a><span data-ttu-id="c623b-101">バインド ファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="c623b-101">Import Binding Files</span></span>

## <a name="overview"></a><span data-ttu-id="c623b-102">概要</span><span class="sxs-lookup"><span data-stu-id="c623b-102">Overview</span></span>
<span data-ttu-id="c623b-103">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を使用してバインド ファイルをインポートする前に、以下の項目について確認してください。</span><span class="sxs-lookup"><span data-stu-id="c623b-103">Before you use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to import a binding file, verify the following:</span></span>  
  
-   <span data-ttu-id="c623b-104">CLASSPATH が PeopleSoft 固有のファイルの特定の場所を指している。</span><span class="sxs-lookup"><span data-stu-id="c623b-104">The CLASSPATH is pointing to a specific location for the PeopleSoft-specific files.</span></span> <span data-ttu-id="c623b-105">新しいコンピュータで、これらのファイルの場所が同じであることを確認します。同じでない場合は、バインド ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="c623b-105">Verify that the location of these files is the same on the new computer—or edit the binding file.</span></span>  
  
-   <span data-ttu-id="c623b-106">新しいコンピュータで、応答用のフォルダが存在し、同じである。同じでない場合は、バインド ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="c623b-106">The folders for the responses must exist and be identical on the new computer—or edit the binding file.</span></span>  
  
-   <span data-ttu-id="c623b-107">PeopleSoft Enterprise システム パスワードが構成に存在する場合、パスワードが ***** としてバインド ファイルに保存されている。</span><span class="sxs-lookup"><span data-stu-id="c623b-107">PeopleSoft Enterprise system passwords, if present in the configuration, are saved as ***** in the binding file.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="c623b-108">展開すると、受信場所の構成が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="c623b-108">Deployment overwrites receive location configuration.</span></span> <span data-ttu-id="c623b-109">バインド ファイルとアセンブリを展開先のコンピュータに展開すると、送信ポートと受信場所が、インポートされた XML バインド ファイルの送信ポートと受信場所に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="c623b-109">When you deploy a binding file and assembly on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are imported.</span></span>  
  
 <span data-ttu-id="c623b-110">バインド ファイルをインポートする手順については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ドキュメントの「BizTalk グループにバインドをインポートする方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c623b-110">For step-by-step directions about importing binding files, see the topic "How to Import Bindings into a BizTalk Group" in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] documentation.</span></span>  
  
## <a name="clean-the-target-computer"></a><span data-ttu-id="c623b-111">ターゲット コンピューターをクリーニングします。</span><span class="sxs-lookup"><span data-stu-id="c623b-111">Clean the Target Computer</span></span>  
<span data-ttu-id="c623b-112">新しいアプリケーションの配置ターゲット コンピューターのクリーニング、送信ポートを削除、および受信場所をオーケストレーションにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="c623b-112">To clean the target computer for deploying the new application, remove send ports and receive locations bound to the orchestration.</span></span>  
  
<span data-ttu-id="c623b-113">Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] が展開先のコンピューターにインストールされていない場合は、次のスクリプトを実行してポートを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="c623b-113">If you do not have Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] installed on the target computer, you may remove the ports by running these scripts:</span></span>  
  
<span data-ttu-id="c623b-114">**\<Microsoft BizTalk Server > \SDK\Samples\Admin\WMI\Remove Port\VBScript\RemoveSendPort.vbs の送信**</span><span class="sxs-lookup"><span data-stu-id="c623b-114">**\<Microsoft BizTalk Server>\SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs**</span></span>  
  
<span data-ttu-id="c623b-115">**\<Microsoft BizTalk Server > \SDK\Samples\Admin\WMI\Remove Port\VBScript\RemoveReceivePort.vbs の受信**</span><span class="sxs-lookup"><span data-stu-id="c623b-115">**\<Microsoft BizTalk Server>\SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs**</span></span>  
  
<span data-ttu-id="c623b-116">たとえば、コマンド プロンプトで次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="c623b-116">For example, at a command prompt, run:</span></span>  
  
<span data-ttu-id="c623b-117">**cscript RemoveSendPort.vbs\<送信ポートの名前 >**</span><span class="sxs-lookup"><span data-stu-id="c623b-117">**cscript RemoveSendPort.vbs \<Send port name>**</span></span>  
  
