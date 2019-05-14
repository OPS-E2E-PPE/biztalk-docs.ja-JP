---
title: SchemaValidator |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting, SchemaValidator utility
- validating, SchemaValidator utility
- SchemaValidator utility
- schemas, SchemaValidator utility
ms.assetid: 3bd61a03-d81e-4fd1-802c-f801000002d7
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2be96f3d87cb0744ca4e823942f7265bf6b3fa3e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281976"
---
# <a name="schemavalidator"></a><span data-ttu-id="7340c-102">SchemaValidator</span><span class="sxs-lookup"><span data-stu-id="7340c-102">SchemaValidator</span></span>
<span data-ttu-id="7340c-103">メッセージ インスタンスに関する問題のトラブルシューティングを行うには、SchemaValidator ユーティリティを使用します。</span><span class="sxs-lookup"><span data-stu-id="7340c-103">You use the SchemaValidator utility to troubleshoot problems with a message instance.</span></span> <span data-ttu-id="7340c-104">検証に失敗したメッセージを受信する場合は、エラーの原因を特定、SchemaValidator ユーティリティを実行できます。</span><span class="sxs-lookup"><span data-stu-id="7340c-104">If you receive a message that fails validation, you can run the SchemaValidator utility to determine the source of the failure.</span></span>  
  
 <span data-ttu-id="7340c-105">スキーマの .dll ファイルを含むアセンブリを使用している場合、このユーティリティを使用して、スキーマの .xsd ファイルがありません。</span><span class="sxs-lookup"><span data-stu-id="7340c-105">You use this utility if you are using an assembly that includes a schema .dll file, and you do not have a schema .xsd file.</span></span> <span data-ttu-id="7340c-106">SchemaValidator ユーティリティを使用して、スキーマの .dll ファイルを使用して検証できます。</span><span class="sxs-lookup"><span data-stu-id="7340c-106">The SchemaValidator utility lets you validate using the schema .dll file.</span></span>  
  
## <a name="location-in-sdk"></a><span data-ttu-id="7340c-107">SDK でのパス</span><span class="sxs-lookup"><span data-stu-id="7340c-107">Location in SDK</span></span>  
 <span data-ttu-id="7340c-108">\<*drive*\>\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\SchemaValidator</span><span class="sxs-lookup"><span data-stu-id="7340c-108">\<*drive*\>\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\SchemaValidator</span></span>  
  
## <a name="building-and-running-schemavalidator"></a><span data-ttu-id="7340c-109">SchemaValidator のビルドと</span><span class="sxs-lookup"><span data-stu-id="7340c-109">Building and Running SchemaValidator</span></span>  
  
#### <a name="to-build-the-schemavalidator-utility"></a><span data-ttu-id="7340c-110">SchemaValidator ユーティリティを構築するには</span><span class="sxs-lookup"><span data-stu-id="7340c-110">To build the SchemaValidator utility</span></span>  
  
1. <span data-ttu-id="7340c-111">コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="7340c-111">Open a command prompt.</span></span>  
  
2. <span data-ttu-id="7340c-112">移動\<*ドライブ*\>\Program Files (x86) \Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\schemavalidator します。</span><span class="sxs-lookup"><span data-stu-id="7340c-112">Move to \<*drive*\>\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\SchemaValidator.</span></span>  
  
3. <span data-ttu-id="7340c-113">コマンド プロンプトで「 **sn-k SchemaValidator.snk**、し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="7340c-113">At the command prompt, type **sn -k SchemaValidator.snk**, and then press ENTER.</span></span>  
  
4. <span data-ttu-id="7340c-114">開始**Microsoft Visual Studio 2012**します。</span><span class="sxs-lookup"><span data-stu-id="7340c-114">Start **Microsoft Visual Studio 2012**.</span></span>  
  
5. <span data-ttu-id="7340c-115">**ファイル**メニューで、**オープン**、 をクリックし、**ソリューションを開く**。</span><span class="sxs-lookup"><span data-stu-id="7340c-115">On the **File** menu, point to **Open**, and then click **Open Solution**.</span></span>  
  
6. <span data-ttu-id="7340c-116">移動\<*ドライブ*\>\Program Files (x86) \Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\schemavalidator、選択**SchemaValidator.sln**、 をクリックし、**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="7340c-116">Move to \<*drive*\>\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\SchemaValidator, select **SchemaValidator.sln**, and then click **Open**.</span></span>  
  
7. <span data-ttu-id="7340c-117">ソリューション エクスプ ローラーで右クリックして**SchemaValidator**、 をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="7340c-117">In Solution Explorer, right-click **SchemaValidator**, and then click **Properties**.</span></span>  
  
8. <span data-ttu-id="7340c-118">**MessageInspector プロパティ**] ページで [**署名**タブをクリックし、をクリックし、**アセンブリに署名**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="7340c-118">In the **MessageInspector Property**  page, click **Signing** tab, and then click **Sign the assembly** checkbox.</span></span> <span data-ttu-id="7340c-119">選択**SchemaValidator.snk**で**厳密な名前キー ファイルを選択して**します。</span><span class="sxs-lookup"><span data-stu-id="7340c-119">Select **SchemaValidator.snk** in **Choose a strong name key file**.</span></span>  
  
9. <span data-ttu-id="7340c-120">クリックして**SchemaValidator.cs**します。</span><span class="sxs-lookup"><span data-stu-id="7340c-120">Click **SchemaValidator.cs**.</span></span>  
  
10. <span data-ttu-id="7340c-121">次の既存のコードの行に適切なメッセージ インスタンス パスを入力`Main`:</span><span class="sxs-lookup"><span data-stu-id="7340c-121">Type the appropriate message instance path in the following existing line of code in `Main`:</span></span>  
  
    ```  
    const string xmlInstancePath = @"..\..\Sample3A4.xml";  
    ```  
  
11. <span data-ttu-id="7340c-122">次の既存のコードの行を置き換えます`Main`Rnpip アセンブリ、および選択し、適切なスキーマへの参照。</span><span class="sxs-lookup"><span data-stu-id="7340c-122">Replace the following existing line of code in `Main` with a reference to the RNPIPs assembly, and then select the appropriate schema:</span></span>  
  
    ```  
    _3A4_MS_V02_02_PurchaseOrderRequest BTSSchema = new _3A4_MS_V02_02_PurchaseOrderRequest();  
    ```  
  
12. <span data-ttu-id="7340c-123">右クリック**SchemaValidator**、 をクリックし、**ビルド**します。</span><span class="sxs-lookup"><span data-stu-id="7340c-123">Right-click **SchemaValidator**, and then click **Build**.</span></span>  
  
13. <span data-ttu-id="7340c-124">メッセージ インスタンスを変更するのには削除して、テストする、 \< \!DOCTYPE.\>タグは、XML インスタンスのヘッダーから DTD ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="7340c-124">Modify the message instance to you want to test by removing the \<\!DOCTYPE …\> tag specifying the DTD file from the header of the XML instance.</span></span>  
  
14. <span data-ttu-id="7340c-125">メッセージ インスタンスのルート ノードに対して検証するスキーマの XML 名前空間を追加します。</span><span class="sxs-lookup"><span data-stu-id="7340c-125">In the root node of the message instance, add an XML namespace of the schema that you will validate against.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7340c-126">SchemaValidator ユーティリティによる検証準備が整ったスキーマの例は、Sample3A4.xml を参照してください\<*ドライブ*\>\Program Files (x86) \Microsoft BizTalk\<バージョン\>。Accelerator for rosettanet \sdk\schemavalidator します。</span><span class="sxs-lookup"><span data-stu-id="7340c-126">For an example of a schema ready to be validated by the SchemaValidator utility, see Sample3A4.xml in \<*drive*\>\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\SchemaValidator.</span></span>  
  
15. <span data-ttu-id="7340c-127">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、 をクリックして**SchemaValidator.cs**とユーティリティを実行するには、ctrl キーと f5 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="7340c-127">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], click **SchemaValidator.cs**, and then press CTRL and F5 to run the utility.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7340c-128">コメント</span><span class="sxs-lookup"><span data-stu-id="7340c-128">Remarks</span></span>  
 <span data-ttu-id="7340c-129">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK には SchemaValidator のコードが含まれています、ロジックは、ユーティリティを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="7340c-129">Because the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK includes the SchemaValidator code, you can add logic to the utility.</span></span> <span data-ttu-id="7340c-130">たとえば、行うことができますが、コマンド ライン ユーティリティ。</span><span class="sxs-lookup"><span data-stu-id="7340c-130">For example, you can make it a command-line utility.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7340c-131">参照</span><span class="sxs-lookup"><span data-stu-id="7340c-131">See Also</span></span>  
 [<span data-ttu-id="7340c-132">ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="7340c-132">Utilities</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)
