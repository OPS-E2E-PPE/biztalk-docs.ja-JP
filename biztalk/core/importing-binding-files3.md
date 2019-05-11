---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-jd-edwards-oneworld/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 920693d0e3ff02b00d8675261db3050f8866b234
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65332169"
---
# <a name="importing-binding-files"></a><span data-ttu-id="759f7-101">バインド ファイルのインポート</span><span class="sxs-lookup"><span data-stu-id="759f7-101">Importing Binding Files</span></span>

## <a name="overview"></a><span data-ttu-id="759f7-102">概要</span><span class="sxs-lookup"><span data-stu-id="759f7-102">Overview</span></span>
<span data-ttu-id="759f7-103">BizTalk Server を使用してバインド ファイルをインポートする前に、次のことを確認します。</span><span class="sxs-lookup"><span data-stu-id="759f7-103">Before you use the BizTalk Server to import a binding file, verify the following:</span></span>  
  
-   <span data-ttu-id="759f7-104">CLASSPATH が JD Edwards 固有のファイルの特定の場所を指している。</span><span class="sxs-lookup"><span data-stu-id="759f7-104">The CLASSPATH is pointing to a specific location for the JD Edwards-specific files.</span></span> <span data-ttu-id="759f7-105">新しいコンピューターで、これらのファイルの場所が同じであることを確認します。同じでない場合は、バインド ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="759f7-105">Verify that the location of these files is the same on the new computer, or edit the binding file.</span></span>  
  
-   <span data-ttu-id="759f7-106">新しいコンピューターに、応答用の同じフォルダーが存在する。同じでない場合は、バインド ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="759f7-106">The folders for the responses exist and are identical on the new computer, or edit the binding file.</span></span>  
  
-   <span data-ttu-id="759f7-107">JD Edwards システム パスワードが構成に存在する場合、パスワードが \*\*\*\*\* としてバインド ファイルに保存されている。</span><span class="sxs-lookup"><span data-stu-id="759f7-107">JD Edwards system passwords, if present in the configuration, are saved as \*\*\*\*\* in the binding file.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="759f7-108">展開には、受信場所の構成が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="759f7-108">Deployment overwrites Receive Location configuration.</span></span> <span data-ttu-id="759f7-109">バインド ファイルとアセンブリをターゲット コンピューターに展開すると、送信ポートと受信場所が、インポートされた XML バインド ファイルの送信ポートと受信場所に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="759f7-109">When deploying a binding file (and assembly) on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are imported.</span></span>  
  
## <a name="import-the-binding-files"></a><span data-ttu-id="759f7-110">バインド ファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="759f7-110">Import the Binding Files</span></span>  
  
1.  <span data-ttu-id="759f7-111">**開始**メニューで、 **Program Files**、 をポイント**Microsoft BizTalk Server**、順にクリックします**BizTalk Server 管理**BizTalk Server 管理コンソールを開始します。</span><span class="sxs-lookup"><span data-stu-id="759f7-111">On the **Start** menu, point to **Program Files**, point to **Microsoft BizTalk Server**, and then click **BizTalk Server Administration** to start the BizTalk Server Administration Console.</span></span>  
  
2.  <span data-ttu-id="759f7-112">BizTalk Server 管理コンソールを展開し、 **BizTalk グループ**、順に展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="759f7-112">Expand BizTalk Server Administration, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="759f7-113">目的のアプリケーションを右クリックし、 をポイント**インポート**、 をクリックし、**バインド**します。</span><span class="sxs-lookup"><span data-stu-id="759f7-113">Right-click the desired application, point to **Import**, and then click **Bindings**.</span></span>  
  
4.  <span data-ttu-id="759f7-114">**バインドのインポート**ダイアログ ボックスで、参照し、バインド ファイルを選択してクリックして**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="759f7-114">In the **Import Bindings** dialog box, browse and select the binding files, and then click **Open**.</span></span>  
  
## <a name="cleaning-the-target-computer"></a><span data-ttu-id="759f7-115">ターゲット コンピューターのクリーニング</span><span class="sxs-lookup"><span data-stu-id="759f7-115">Cleaning the Target Computer</span></span>  
<span data-ttu-id="759f7-116">送信ポートとオーケストレーションにバインドされている受信場所を削除します。</span><span class="sxs-lookup"><span data-stu-id="759f7-116">Remove the send ports and the receive locations that are bound to the orchestration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="759f7-117">参照</span><span class="sxs-lookup"><span data-stu-id="759f7-117">See Also</span></span>  
 <span data-ttu-id="759f7-118">[BizTalk 管理コンソールに、アイテムを追加します。](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md) </span><span class="sxs-lookup"><span data-stu-id="759f7-118">[Add the artifacts to BizTalk Administration](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md) </span></span>  
 [<span data-ttu-id="759f7-119">インポートの JD Edwards OneWorld アプリ</span><span class="sxs-lookup"><span data-stu-id="759f7-119">Import the JD Edwards OneWorld app</span></span>](deploying-biztalk-adapter-for-jd-edwards-oneworld.md)