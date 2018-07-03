---
title: マップの検証 (EDI) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: caf58ecf-ed10-4c13-8d7d-e007b9158b0e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6cfe1394d82f4fedb57aacb40bad27c95de2a46
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993339"
---
# <a name="validating-a-map-edi"></a><span data-ttu-id="d819c-102">マップの検証 (EDI)</span><span class="sxs-lookup"><span data-stu-id="d819c-102">Validating a Map (EDI)</span></span>
<span data-ttu-id="d819c-103">マップは、デザイン時に検証できます。</span><span class="sxs-lookup"><span data-stu-id="d819c-103">You can validate a map at design time.</span></span> <span data-ttu-id="d819c-104">これを行うには、XML ツール拡張機能を使用して[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]環境。</span><span class="sxs-lookup"><span data-stu-id="d819c-104">To do so, you use the XML Tool extensions to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] environment.</span></span> <span data-ttu-id="d819c-105">検証を行うと、マップの基になる XSLT を含むファイルと、拡張オブジェクトを含むファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="d819c-105">This operation generates a file containing the underlying XSLT of the map and a file containing extension objects.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d819c-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="d819c-106">Prerequisites</span></span>  
 <span data-ttu-id="d819c-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d819c-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-validate-a-map"></a><span data-ttu-id="d819c-108">マップを検証するには</span><span class="sxs-lookup"><span data-stu-id="d819c-108">To validate a map</span></span>  
  
1. <span data-ttu-id="d819c-109">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="d819c-109">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open a project.</span></span> <span data-ttu-id="d819c-110">ソリューション エクスプローラーで、検証するマップと、その入力および出力のメッセージ スキーマをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="d819c-110">To the project in Solution Explorer, add the map that you want to validate and its input and output message schemas.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="d819c-111">メッセージ スキーマは [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI folder フォルダーの下の該当するサブフォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="d819c-111">The message schemas are located in the appropriate subfolder under the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI folder.</span></span> <span data-ttu-id="d819c-112">スキーマ ファイルをインストールする方法の詳細については、次を参照してください。 [EDI スキーマ ファイルをインストールする方法](http://msdn.microsoft.com/library/787f45d9-d95d-40f4-a4ac-0a0e711f7550)します。</span><span class="sxs-lookup"><span data-stu-id="d819c-112">For more information on installing the schema files, see [How to Install EDI Schema Files](http://msdn.microsoft.com/library/787f45d9-d95d-40f4-a4ac-0a0e711f7550).</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="d819c-113">マップを検証するためにプロジェクトをビルドする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d819c-113">You do not have to build the project to validate a map.</span></span>  
  
2. <span data-ttu-id="d819c-114">ソリューション エクスプ ローラーでマップを右クリックし、をクリックし、**マップの検証**です。</span><span class="sxs-lookup"><span data-stu-id="d819c-114">Right-click the map in Solution Explorer, and then click **Validate Map**.</span></span>  
  
3. <span data-ttu-id="d819c-115">操作が成功したことを示すメッセージが [出力] ウィンドウに表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d819c-115">Verify that there is a message in the Output window indicating that the operation succeeded.</span></span>  
  
4. <span data-ttu-id="d819c-116">すべての警告に注意してくださいを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]でポスト、**出力**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="d819c-116">Note any warnings that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] has posted in the **Output** window.</span></span>  
  
5. <span data-ttu-id="d819c-117">**出力**ウィンドウ、出力された XSLT のパスと名前に注意してください。</span><span class="sxs-lookup"><span data-stu-id="d819c-117">In the **Output** window, note the name and path of the output XSLT.</span></span> <span data-ttu-id="d819c-118">この XSL ファイルにはマップ ファイルと同じ名前が設定されます。ただし、拡張子は XSL です。</span><span class="sxs-lookup"><span data-stu-id="d819c-118">This XSL file will be given the same name as the map file, but with an XSL extension.</span></span> <span data-ttu-id="d819c-119">Ctrl キーを押しながらリンクをクリックすると、BizTalk エディターに XSL ファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d819c-119">You can press CTRL and click the link to display the XSL file in the BizTalk Editor.</span></span>  
  
6. <span data-ttu-id="d819c-120">**出力**ウィンドウで、拡張オブジェクト XML のパスと名前に注意してください。</span><span class="sxs-lookup"><span data-stu-id="d819c-120">In the **Output** window, note the name and path of the extension object XML.</span></span> <span data-ttu-id="d819c-121">Ctrl キーを押しながらリンクをクリックすると、BizTalk エディターに XSL ファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d819c-121">You can press CTRL and click the link to display the XSL file in the BizTalk Editor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d819c-122">参照</span><span class="sxs-lookup"><span data-stu-id="d819c-122">See Also</span></span>  
 [<span data-ttu-id="d819c-123">デザイン時 XML ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="d819c-123">Using Design-Time XML Tools</span></span>](../core/using-design-time-xml-tools.md)