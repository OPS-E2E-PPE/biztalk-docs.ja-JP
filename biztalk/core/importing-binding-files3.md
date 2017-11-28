---
title: "Files3 のバインドのインポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- binding files, importing
- target computer, cleaning
- importing binding files
- cleaning target computer
ms.assetid: 955bb3e1-3dbc-43ce-9126-205d838ae662
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa1d95c40e3e556068e15a269ee4cbb7e995429a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="importing-binding-files"></a><span data-ttu-id="04240-102">バインド ファイルのインポート</span><span class="sxs-lookup"><span data-stu-id="04240-102">Importing Binding Files</span></span>
<span data-ttu-id="04240-103">バインド ファイルをインポートする BizTalk Server を使用する前に、次の操作を確認します。</span><span class="sxs-lookup"><span data-stu-id="04240-103">Before you use the BizTalk Server to import a binding file, verify the following:</span></span>  
  
-   <span data-ttu-id="04240-104">CLASSPATH が JD Edwards 固有のファイルの特定の場所を指している。</span><span class="sxs-lookup"><span data-stu-id="04240-104">The CLASSPATH is pointing to a specific location for the JD Edwards-specific files.</span></span> <span data-ttu-id="04240-105">新しいコンピューターで、これらのファイルの場所が同じであることを確認します。同じでない場合は、バインド ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="04240-105">Verify that the location of these files is the same on the new computer, or edit the binding file.</span></span>  
  
-   <span data-ttu-id="04240-106">新しいコンピューターに、応答用の同じフォルダーが存在する。同じでない場合は、バインド ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="04240-106">The folders for the responses exist and are identical on the new computer, or edit the binding file.</span></span>  
  
-   <span data-ttu-id="04240-107">JD Edwards システム パスワードが構成に存在する場合、パスワードが ***** としてバインド ファイルに保存されている。</span><span class="sxs-lookup"><span data-stu-id="04240-107">JD Edwards system passwords, if present in the configuration, are saved as ***** in the binding file.</span></span> <span data-ttu-id="04240-108">詳細については、次を参照してください。[展開の制限事項](../core/deployment-limitations2.md)です。</span><span class="sxs-lookup"><span data-stu-id="04240-108">For more information, see [Deployment Limitations](../core/deployment-limitations2.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="04240-109">展開には、受信場所の構成が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="04240-109">Deployment overwrites Receive Location configuration.</span></span> <span data-ttu-id="04240-110">バインド ファイルとアセンブリを展開先のコンピューターに展開すると、送信ポートと受信場所が、インポートされた XML バインド ファイルの送信ポートと受信場所に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="04240-110">When deploying a binding file (and assembly) on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are imported.</span></span>  
  
## <a name="importing-the-binding-files"></a><span data-ttu-id="04240-111">バインド ファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="04240-111">Importing the Binding Files</span></span>  
 <span data-ttu-id="04240-112">バインド ファイルをインポートするには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="04240-112">Use the following procedure to import the binding files.</span></span>  
  
#### <a name="to-import-the-binding-files"></a><span data-ttu-id="04240-113">バインド ファイルをインポートするには</span><span class="sxs-lookup"><span data-stu-id="04240-113">To import the binding files</span></span>  
  
1.  <span data-ttu-id="04240-114">**開始** メニューのをポイント**Program Files**、 をポイント**Microsoft BizTalk Server**、順にクリック**BizTalk Server 管理コンソール**BizTalk Server 管理コンソールを開始します。</span><span class="sxs-lookup"><span data-stu-id="04240-114">On the **Start** menu, point to **Program Files**, point to **Microsoft BizTalk Server**, and then click **BizTalk Server Administration** to start the BizTalk Server Administration Console.</span></span>  
  
2.  <span data-ttu-id="04240-115">BizTalk Server 管理コンソールを展開し、 **BizTalk グループ**の順に展開および**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="04240-115">Expand BizTalk Server Administration, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="04240-116">目的のアプリケーションを右クリックし、順にポイント**インポート**、順にクリック**バインド**です。</span><span class="sxs-lookup"><span data-stu-id="04240-116">Right-click the desired application, point to **Import**, and then click **Bindings**.</span></span>  
  
4.  <span data-ttu-id="04240-117">**バインドのインポート**ダイアログ ボックスで、参照し、バインド ファイルを選択してクリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="04240-117">In the **Import Bindings** dialog box, browse and select the binding files, and then click **Open**.</span></span>  
  
## <a name="cleaning-the-target-computer"></a><span data-ttu-id="04240-118">展開先のコンピューターのクリーニング</span><span class="sxs-lookup"><span data-stu-id="04240-118">Cleaning the Target Computer</span></span>  
 <span data-ttu-id="04240-119">次の手順を使用して展開先のコンピューターをクリーニングします。</span><span class="sxs-lookup"><span data-stu-id="04240-119">Use the following procedure to clean the target computer.</span></span>  
  
#### <a name="to-clean-the-target-computer"></a><span data-ttu-id="04240-120">展開先のコンピューターをクリーニングするには</span><span class="sxs-lookup"><span data-stu-id="04240-120">To clean the target computer</span></span>  
  
-   <span data-ttu-id="04240-121">送信ポートおよびオーケストレーションにバインドされている受信場所を削除します。</span><span class="sxs-lookup"><span data-stu-id="04240-121">Remove the send ports and the receive locations that are bound to the orchestration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04240-122">参照</span><span class="sxs-lookup"><span data-stu-id="04240-122">See Also</span></span>  
 <span data-ttu-id="04240-123">[JD Edwards OneWorld 送信ハンドラーの作成](../core/creating-jd-edwards-oneworld-send-handlers.md) </span><span class="sxs-lookup"><span data-stu-id="04240-123">[Creating JD Edwards OneWorld Send Handlers](../core/creating-jd-edwards-oneworld-send-handlers.md) </span></span>  
 [<span data-ttu-id="04240-124">ポートとアセンブリの展開</span><span class="sxs-lookup"><span data-stu-id="04240-124">Deploying Ports and Assemblies</span></span>](../core/deploying-ports-and-assemblies4.md)