---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-jd-edwards-oneworld/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 5c5cce40f3fbeb580ec7ba854d02cb243e1742b4
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013465"
---
# <a name="importing-binding-files"></a><span data-ttu-id="d0421-101">バインド ファイルのインポート</span><span class="sxs-lookup"><span data-stu-id="d0421-101">Importing Binding Files</span></span>

## <a name="overview"></a><span data-ttu-id="d0421-102">概要</span><span class="sxs-lookup"><span data-stu-id="d0421-102">Overview</span></span>
<span data-ttu-id="d0421-103">バインド ファイルをインポートする BizTalk Server を使用する前に、次の操作を確認します。</span><span class="sxs-lookup"><span data-stu-id="d0421-103">Before you use the BizTalk Server to import a binding file, verify the following:</span></span>  
  
-   <span data-ttu-id="d0421-104">CLASSPATH が JD Edwards 固有のファイルの特定の場所を指している。</span><span class="sxs-lookup"><span data-stu-id="d0421-104">The CLASSPATH is pointing to a specific location for the JD Edwards-specific files.</span></span> <span data-ttu-id="d0421-105">新しいコンピューターで、これらのファイルの場所が同じであることを確認します。同じでない場合は、バインド ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="d0421-105">Verify that the location of these files is the same on the new computer, or edit the binding file.</span></span>  
  
-   <span data-ttu-id="d0421-106">新しいコンピューターに、応答用の同じフォルダーが存在する。同じでない場合は、バインド ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="d0421-106">The folders for the responses exist and are identical on the new computer, or edit the binding file.</span></span>  
  
-   <span data-ttu-id="d0421-107">JD Edwards システム パスワードが構成に存在する場合、パスワードが \*\*\*\*\* としてバインド ファイルに保存されている。</span><span class="sxs-lookup"><span data-stu-id="d0421-107">JD Edwards system passwords, if present in the configuration, are saved as \*\*\*\*\* in the binding file.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="d0421-108">展開には、受信場所の構成が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="d0421-108">Deployment overwrites Receive Location configuration.</span></span> <span data-ttu-id="d0421-109">バインド ファイルとアセンブリを展開先のコンピューターに展開すると、送信ポートと受信場所が、インポートされた XML バインド ファイルの送信ポートと受信場所に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="d0421-109">When deploying a binding file (and assembly) on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are imported.</span></span>  
  
## <a name="import-the-binding-files"></a><span data-ttu-id="d0421-110">バインド ファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="d0421-110">Import the Binding Files</span></span>  
  
1.  <span data-ttu-id="d0421-111">**開始** メニューのをポイント**Program Files**、 をポイント**Microsoft BizTalk Server**、順にクリック**BizTalk Server 管理コンソール**BizTalk Server 管理コンソールを開始します。</span><span class="sxs-lookup"><span data-stu-id="d0421-111">On the **Start** menu, point to **Program Files**, point to **Microsoft BizTalk Server**, and then click **BizTalk Server Administration** to start the BizTalk Server Administration Console.</span></span>  
  
2.  <span data-ttu-id="d0421-112">BizTalk Server 管理コンソールを展開し、 **BizTalk グループ**の順に展開および**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="d0421-112">Expand BizTalk Server Administration, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="d0421-113">目的のアプリケーションを右クリックし、順にポイント**インポート**、順にクリック**バインド**です。</span><span class="sxs-lookup"><span data-stu-id="d0421-113">Right-click the desired application, point to **Import**, and then click **Bindings**.</span></span>  
  
4.  <span data-ttu-id="d0421-114">**バインドのインポート**ダイアログ ボックスで、参照し、バインド ファイルを選択してクリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="d0421-114">In the **Import Bindings** dialog box, browse and select the binding files, and then click **Open**.</span></span>  
  
## <a name="cleaning-the-target-computer"></a><span data-ttu-id="d0421-115">展開先のコンピューターのクリーニング</span><span class="sxs-lookup"><span data-stu-id="d0421-115">Cleaning the Target Computer</span></span>  
<span data-ttu-id="d0421-116">送信ポートおよびオーケストレーションにバインドされている受信場所を削除します。</span><span class="sxs-lookup"><span data-stu-id="d0421-116">Remove the send ports and the receive locations that are bound to the orchestration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0421-117">参照</span><span class="sxs-lookup"><span data-stu-id="d0421-117">See Also</span></span>  
 <span data-ttu-id="d0421-118">[BizTalk 管理コンソールに、アイテムを追加します。](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md) </span><span class="sxs-lookup"><span data-stu-id="d0421-118">[Add the artifacts to BizTalk Administration](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md) </span></span>  
 [<span data-ttu-id="d0421-119">インポート JD Edwards OneWorld アプリ</span><span class="sxs-lookup"><span data-stu-id="d0421-119">Import the JD Edwards OneWorld app</span></span>](deploying-biztalk-adapter-for-jd-edwards-oneworld.md)