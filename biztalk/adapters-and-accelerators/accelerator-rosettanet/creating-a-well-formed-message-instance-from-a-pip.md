---
title: "PIP からの整形式メッセージ インスタンスを作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- message templates
- PIPs, message templates
ms.assetid: fed3698c-25d9-40ca-878a-60171f425bec
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e16020afb17d17c8add8e973ade0cd0c5cfcbbc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="creating-a-well-formed-message-instance-from-a-pip"></a><span data-ttu-id="d5f2d-102">PIP からの整形式メッセージ インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="d5f2d-102">Creating a Well-Formed Message Instance from a PIP</span></span>
<span data-ttu-id="d5f2d-103">ここでは、整形式のメッセージ インスタンスを生成する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="d5f2d-103">This topic describes how to produce a well-formed message instance.</span></span> <span data-ttu-id="d5f2d-104">PIP (Partner Interface Process) からメッセージ インスタンスのテンプレートを生成できます。</span><span class="sxs-lookup"><span data-stu-id="d5f2d-104">You can generate a template for a message instance from the Partner Interface Process (PIP).</span></span> <span data-ttu-id="d5f2d-105">その後、データを追加する前に、それが整形式になるように、そのテンプレートを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5f2d-105">After doing this, you have to modify that template, so that it is well formed, before adding your data.</span></span>  
  
### <a name="to-generate-a-message-instance-template-from-the-pip"></a><span data-ttu-id="d5f2d-106">PIP からメッセージ インスタンス テンプレートを生成するには</span><span class="sxs-lookup"><span data-stu-id="d5f2d-106">To generate a message instance template from the PIP</span></span>  
  
1.  <span data-ttu-id="d5f2d-107">開始**Microsoft Visual Studio 2012**です。</span><span class="sxs-lookup"><span data-stu-id="d5f2d-107">Start **Microsoft Visual Studio 2012**.</span></span>  
  
2.  <span data-ttu-id="d5f2d-108">**ファイル** メニューのをポイント**開く**、順にクリック**プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="d5f2d-108">On the **File** menu, point to **Open**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="d5f2d-109">検索\<*ドライブ*> \Program Files\Microsoft BizTalk\<バージョン > Accelerator for rosettanetsdk \schemas に移動をクリックして**RNPIPs.btproj**をクリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="d5f2d-109">Locate \<*drive*>\Program Files\Microsoft BizTalk \<version> Accelerator for RosettaNetSDK\Schemas, click **RNPIPs.btproj**, and then click **Open**.</span></span>  
  
4.  <span data-ttu-id="d5f2d-110">ソリューション エクスプ ローラーで、 **Rnpip**、し、インスタンスを作成する PIP を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="d5f2d-110">In Solution Explorer, expand **RNPIPs**, and then right-click the PIP for which you want to create an instance.</span></span>  
  
5.  <span data-ttu-id="d5f2d-111">をクリックして**インスタンスを生成する**です。</span><span class="sxs-lookup"><span data-stu-id="d5f2d-111">Click **Generate Instance**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d5f2d-112">選択した PIP の名前の後に "_output" が追加され、さらに .xml 拡張子を付けたファイル名が生成されます。</span><span class="sxs-lookup"><span data-stu-id="d5f2d-112">This generates a file named after the PIP, with "_output" appended to the file name, and with an .xml extension.</span></span> <span data-ttu-id="d5f2d-113">出力ペインのステートメントにより、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] でインスタンスが作成された場所が示されます。</span><span class="sxs-lookup"><span data-stu-id="d5f2d-113">A statement in the Output pane indicates where [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] generated the instance.</span></span>  
  
### <a name="to-modify-the-message-instance-template"></a><span data-ttu-id="d5f2d-114">メッセージ インスタンス テンプレートを変更するには</span><span class="sxs-lookup"><span data-stu-id="d5f2d-114">To modify the message instance template</span></span>  
  
1.  <span data-ttu-id="d5f2d-115">[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] エクスプローラーで、目的の XML ファイルが保存されているフォルダーに移動し、そのファイルの名前をダブルクリックして開きます。</span><span class="sxs-lookup"><span data-stu-id="d5f2d-115">In [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, locate the folder holding the XML file, and double-click the file name to open the folder.</span></span>  
  
2.  <span data-ttu-id="d5f2d-116">他のすべてのテキストの前に、XML のバージョンとエンコードを示す XML ヘッダー タグを追加します。</span><span class="sxs-lookup"><span data-stu-id="d5f2d-116">Add an XML header tag before all other text indicating the version of XML and the encoding.</span></span> <span data-ttu-id="d5f2d-117">例:</span><span class="sxs-lookup"><span data-stu-id="d5f2d-117">For example:</span></span>  
  
    ```  
    <?xml version="1.0" encoding="UTF-8" ?>  
    ```  
  
3.  <span data-ttu-id="d5f2d-118">追加した行の後に、DTD を示す DOCTYPE 行を追加します。</span><span class="sxs-lookup"><span data-stu-id="d5f2d-118">After the line that you just added, add a DOCTYPE line indicating the DTD.</span></span> <span data-ttu-id="d5f2d-119">たとえば、3A4 発注要求のインスタンスの場合、DOCTYPE 行は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="d5f2d-119">For example, for a 3A4 Purchase Order Request instance, the line would be as follows:</span></span>  
  
    ```  
    <!DOCTYPE Pip3A4PurchaseOrderRequest SYSTEM "3A4_MS_V02_02_PurchaseOrderRequest.dtd">  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="d5f2d-120">各メッセージ インスタンスを処理するには、それぞれ DOCTYPE 行を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5f2d-120">Each message instance must include the DOCTYPE line to be processed.</span></span>  
  
4.  <span data-ttu-id="d5f2d-121">これで、ビジネス ニーズに合わせてこのメッセージ インスタンスをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="d5f2d-121">You may now customize this message instance to suit your business needs.</span></span> <span data-ttu-id="d5f2d-122">XML 名前空間または名前空間プレフィックスを使用しないように、XML インスタンスを変更します。</span><span class="sxs-lookup"><span data-stu-id="d5f2d-122">Modify the XML instance so that it does not use XML namespaces or namespace prefixes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5f2d-123">参照</span><span class="sxs-lookup"><span data-stu-id="d5f2d-123">See Also</span></span>  
 [<span data-ttu-id="d5f2d-124">プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="d5f2d-124">Programming Guide</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)