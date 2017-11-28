---
title: "マップ (EDI) の検証 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: caf58ecf-ed10-4c13-8d7d-e007b9158b0e
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 028a152be285bb79f3cd0899b2143e99ef2b6042
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="validating-a-map-edi"></a><span data-ttu-id="b837e-102">マップの検証 (EDI)</span><span class="sxs-lookup"><span data-stu-id="b837e-102">Validating a Map (EDI)</span></span>
<span data-ttu-id="b837e-103">マップは、デザイン時に検証できます。</span><span class="sxs-lookup"><span data-stu-id="b837e-103">You can validate a map at design time.</span></span> <span data-ttu-id="b837e-104">XML ツール拡張機能を使用するためには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]環境。</span><span class="sxs-lookup"><span data-stu-id="b837e-104">To do so, you use the XML Tool extensions to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] environment.</span></span> <span data-ttu-id="b837e-105">検証を行うと、マップの基になる XSLT を含むファイルと、拡張オブジェクトを含むファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="b837e-105">This operation generates a file containing the underlying XSLT of the map and a file containing extension objects.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b837e-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="b837e-106">Prerequisites</span></span>  
 <span data-ttu-id="b837e-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b837e-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-validate-a-map"></a><span data-ttu-id="b837e-108">マップを検証するには</span><span class="sxs-lookup"><span data-stu-id="b837e-108">To validate a map</span></span>  
  
1.  <span data-ttu-id="b837e-109">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="b837e-109">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open a project.</span></span> <span data-ttu-id="b837e-110">ソリューション エクスプローラーで、検証するマップと、その入力および出力のメッセージ スキーマをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="b837e-110">To the project in Solution Explorer, add the map that you want to validate and its input and output message schemas.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b837e-111">メッセージ スキーマは [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI folder フォルダーの下の該当するサブフォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="b837e-111">The message schemas are located in the appropriate subfolder under the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI folder.</span></span> <span data-ttu-id="b837e-112">スキーマ ファイルのインストールの詳細については、次を参照してください。 [EDI スキーマ ファイルをインストールする方法](http://msdn.microsoft.com/library/787f45d9-d95d-40f4-a4ac-0a0e711f7550)です。</span><span class="sxs-lookup"><span data-stu-id="b837e-112">For more information on installing the schema files, see [How to Install EDI Schema Files](http://msdn.microsoft.com/library/787f45d9-d95d-40f4-a4ac-0a0e711f7550).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b837e-113">マップを検証するためにプロジェクトをビルドする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b837e-113">You do not have to build the project to validate a map.</span></span>  
  
2.  <span data-ttu-id="b837e-114">ソリューション エクスプ ローラーでマップを右クリックし、をクリックして**マップの検証**です。</span><span class="sxs-lookup"><span data-stu-id="b837e-114">Right-click the map in Solution Explorer, and then click **Validate Map**.</span></span>  
  
3.  <span data-ttu-id="b837e-115">操作が成功したことを示すメッセージが [出力] ウィンドウに表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b837e-115">Verify that there is a message in the Output window indicating that the operation succeeded.</span></span>  
  
4.  <span data-ttu-id="b837e-116">すべての警告に注意してくださいを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]でをポストしましたが、**出力**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="b837e-116">Note any warnings that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] has posted in the **Output** window.</span></span>  
  
5.  <span data-ttu-id="b837e-117">**出力**ウィンドウ、出力された XSLT のパスと名前に注意してください。</span><span class="sxs-lookup"><span data-stu-id="b837e-117">In the **Output** window, note the name and path of the output XSLT.</span></span> <span data-ttu-id="b837e-118">この XSL ファイルにはマップ ファイルと同じ名前が設定されます。ただし、拡張子は XSL です。</span><span class="sxs-lookup"><span data-stu-id="b837e-118">This XSL file will be given the same name as the map file, but with an XSL extension.</span></span> <span data-ttu-id="b837e-119">Ctrl キーを押しながらリンクをクリックすると、BizTalk エディターに XSL ファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b837e-119">You can press CTRL and click the link to display the XSL file in the BizTalk Editor.</span></span>  
  
6.  <span data-ttu-id="b837e-120">**出力**ウィンドウで、拡張オブジェクト XML のパスと名前に注意してください。</span><span class="sxs-lookup"><span data-stu-id="b837e-120">In the **Output** window, note the name and path of the extension object XML.</span></span> <span data-ttu-id="b837e-121">Ctrl キーを押しながらリンクをクリックすると、BizTalk エディターに XSL ファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b837e-121">You can press CTRL and click the link to display the XSL file in the BizTalk Editor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b837e-122">参照</span><span class="sxs-lookup"><span data-stu-id="b837e-122">See Also</span></span>  
 [<span data-ttu-id="b837e-123">デザイン時 XML ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="b837e-123">Using Design-Time XML Tools</span></span>](../core/using-design-time-xml-tools.md)