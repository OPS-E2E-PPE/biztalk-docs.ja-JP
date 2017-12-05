---
title: "SchemaValidator |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- troubleshooting, SchemaValidator utility
- validating, SchemaValidator utility
- SchemaValidator utility
- schemas, SchemaValidator utility
ms.assetid: 3bd61a03-d81e-4fd1-802c-f801000002d7
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9e3921b8bf83e3e7e775efef77a029bfda2e7e9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="schemavalidator"></a><span data-ttu-id="b77a4-102">SchemaValidator</span><span class="sxs-lookup"><span data-stu-id="b77a4-102">SchemaValidator</span></span>
<span data-ttu-id="b77a4-103">メッセージ インスタンスに関連した問題のトラブルシューティングを行うには、SchemaValidator ユーティリティを使用します。</span><span class="sxs-lookup"><span data-stu-id="b77a4-103">You use the SchemaValidator utility to troubleshoot problems with a message instance.</span></span> <span data-ttu-id="b77a4-104">検証に失敗したメッセージを受信した場合は、SchemaValidator ユーティリティを実行して、失敗の原因を特定できます。</span><span class="sxs-lookup"><span data-stu-id="b77a4-104">If you receive a message that fails validation, you can run the SchemaValidator utility to determine the source of the failure.</span></span>  
  
 <span data-ttu-id="b77a4-105">このユーティリティは、使用中のアセンブリにスキーマの .dll ファイルが含まれているが、スキーマの .xsd ファイルを持っていない場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="b77a4-105">You use this utility if you are using an assembly that includes a schema .dll file, and you do not have a schema .xsd file.</span></span> <span data-ttu-id="b77a4-106">SchemaValidator ユーティリティでは、スキーマの .dll ファイルを使用して検証できます。</span><span class="sxs-lookup"><span data-stu-id="b77a4-106">The SchemaValidator utility lets you validate using the schema .dll file.</span></span>  
  
## <a name="location-in-sdk"></a><span data-ttu-id="b77a4-107">SDK でのパス</span><span class="sxs-lookup"><span data-stu-id="b77a4-107">Location in SDK</span></span>  
 <span data-ttu-id="b77a4-108">\<*ドライブ*\>\Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\schemavalidator</span><span class="sxs-lookup"><span data-stu-id="b77a4-108">\<*drive*\>\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\SchemaValidator</span></span>  
  
## <a name="building-and-running-schemavalidator"></a><span data-ttu-id="b77a4-109">SchemaValidator のビルドと実行</span><span class="sxs-lookup"><span data-stu-id="b77a4-109">Building and Running SchemaValidator</span></span>  
  
#### <a name="to-build-the-schemavalidator-utility"></a><span data-ttu-id="b77a4-110">SchemaValidator ユーティリティをビルドするには</span><span class="sxs-lookup"><span data-stu-id="b77a4-110">To build the SchemaValidator utility</span></span>  
  
1.  <span data-ttu-id="b77a4-111">コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="b77a4-111">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="b77a4-112">移動\<*ドライブ*\>\Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\schemavalidator です。</span><span class="sxs-lookup"><span data-stu-id="b77a4-112">Move to \<*drive*\>\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\SchemaValidator.</span></span>  
  
3.  <span data-ttu-id="b77a4-113">コマンド プロンプトで次のように入力します。 **sn-k SchemaValidator.snk**、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="b77a4-113">At the command prompt, type **sn -k SchemaValidator.snk**, and then press ENTER.</span></span>  
  
4.  <span data-ttu-id="b77a4-114">開始**Microsoft Visual Studio 2012**です。</span><span class="sxs-lookup"><span data-stu-id="b77a4-114">Start **Microsoft Visual Studio 2012**.</span></span>  
  
5.  <span data-ttu-id="b77a4-115">**ファイル** メニューのをポイント**開く**、順にクリック**ソリューションを開く**です。</span><span class="sxs-lookup"><span data-stu-id="b77a4-115">On the **File** menu, point to **Open**, and then click **Open Solution**.</span></span>  
  
6.  <span data-ttu-id="b77a4-116">移動\<*ドライブ*\>\Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\schemavalidator、選択**SchemaValidator.sln**、クリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="b77a4-116">Move to \<*drive*\>\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\SchemaValidator, select **SchemaValidator.sln**, and then click **Open**.</span></span>  
  
7.  <span data-ttu-id="b77a4-117">ソリューション エクスプ ローラーで右クリック**SchemaValidator**、クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="b77a4-117">In Solution Explorer, right-click **SchemaValidator**, and then click **Properties**.</span></span>  
  
8.  <span data-ttu-id="b77a4-118">**MessageInspector プロパティ** ページで **署名** タブをクリックして**アセンブリに署名**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="b77a4-118">In the **MessageInspector Property**  page, click **Signing** tab, and then click **Sign the assembly** checkbox.</span></span> <span data-ttu-id="b77a4-119">選択**SchemaValidator.snk**で**厳密な名前キー ファイルを選択して**です。</span><span class="sxs-lookup"><span data-stu-id="b77a4-119">Select **SchemaValidator.snk** in **Choose a strong name key file**.</span></span>  
  
9. <span data-ttu-id="b77a4-120">をクリックして**SchemaValidator.cs**です。</span><span class="sxs-lookup"><span data-stu-id="b77a4-120">Click **SchemaValidator.cs**.</span></span>  
  
10. <span data-ttu-id="b77a4-121">`Main` の次の既存のコード行に適切なメッセージ インスタンス パスを入力します。</span><span class="sxs-lookup"><span data-stu-id="b77a4-121">Type the appropriate message instance path in the following existing line of code in `Main`:</span></span>  
  
    ```  
    const string xmlInstancePath = @"..\..\Sample3A4.xml";  
    ```  
  
11. <span data-ttu-id="b77a4-122">`Main` の次の既存のコード行を RNPIP アセンブリへの参照に置き換えて、適切なスキーマを選択します。</span><span class="sxs-lookup"><span data-stu-id="b77a4-122">Replace the following existing line of code in `Main` with a reference to the RNPIPs assembly, and then select the appropriate schema:</span></span>  
  
    ```  
    _3A4_MS_V02_02_PurchaseOrderRequest BTSSchema = new _3A4_MS_V02_02_PurchaseOrderRequest();  
    ```  
  
12. <span data-ttu-id="b77a4-123">右クリック**SchemaValidator**、クリックして**ビルド**です。</span><span class="sxs-lookup"><span data-stu-id="b77a4-123">Right-click **SchemaValidator**, and then click **Build**.</span></span>  
  
13. <span data-ttu-id="b77a4-124">メッセージ インスタンスを変更する削除して、テスト、 \< \!DOCTYPE しています.\>タグは、XML インスタンスのヘッダーから DTD ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="b77a4-124">Modify the message instance to you want to test by removing the \<\!DOCTYPE …\> tag specifying the DTD file from the header of the XML instance.</span></span>  
  
14. <span data-ttu-id="b77a4-125">メッセージ インスタンスのルート ノードに、検証に使用するスキーマの XML 名前空間を追加します。</span><span class="sxs-lookup"><span data-stu-id="b77a4-125">In the root node of the message instance, add an XML namespace of the schema that you will validate against.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b77a4-126">SchemaValidator ユーティリティによる検証する準備が整ったスキーマの例は、の Sample3A4.xml を参照してください\<*ドライブ*\>\Program Files\Microsoft BizTalk\<バージョン\>アクセラレータ。for rosettanet \sdk\schemavalidator です。</span><span class="sxs-lookup"><span data-stu-id="b77a4-126">For an example of a schema ready to be validated by the SchemaValidator utility, see Sample3A4.xml in \<*drive*\>\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\SchemaValidator.</span></span>  
  
15. <span data-ttu-id="b77a4-127">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]をクリックして**SchemaValidator.cs**ユーティリティを実行するには、ctrl キーと F5 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="b77a4-127">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], click **SchemaValidator.cs**, and then press CTRL and F5 to run the utility.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b77a4-128">解説</span><span class="sxs-lookup"><span data-stu-id="b77a4-128">Remarks</span></span>  
 <span data-ttu-id="b77a4-129">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK には SchemaValidator のコードが含まれているので、SchemaValidator にロジックを追加できます。</span><span class="sxs-lookup"><span data-stu-id="b77a4-129">Because the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK includes the SchemaValidator code, you can add logic to the utility.</span></span> <span data-ttu-id="b77a4-130">たとえば、SchemaValidator をコマンドライン ユーティリティにすることができます。</span><span class="sxs-lookup"><span data-stu-id="b77a4-130">For example, you can make it a command-line utility.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b77a4-131">参照</span><span class="sxs-lookup"><span data-stu-id="b77a4-131">See Also</span></span>  
 [<span data-ttu-id="b77a4-132">ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="b77a4-132">Utilities</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)