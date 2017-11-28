---
title: "手順 1: Contoso アセンブリへの厳密な名前の割り当て |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- private process tutorial, assigning strong-names
- strong-named assemblies
ms.assetid: c8ec4593-5a4d-47ab-8799-7b2cd3d15ffc
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7124561b9f842a7cc980c7a54230cd122ae32856
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-assigning-a-strong-name-to-the-contoso-assembly"></a><span data-ttu-id="e4e44-102">手順 1: Contoso アセンブリへの厳密な名前の割り当てください。</span><span class="sxs-lookup"><span data-stu-id="e4e44-102">Step 1: Assigning a Strong Name to the Contoso Assembly</span></span>
<span data-ttu-id="e4e44-103">ここでは、BizTalk アセンブリの厳密な名前を作成して割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e4e44-103">In this step, you create and assign a strong name for your BizTalk assembly.</span></span> <span data-ttu-id="e4e44-104">厳密な名前により、デジタル署名と一意のキーのペアを割り当てることで、アセンブリの一意性を保証します。</span><span class="sxs-lookup"><span data-stu-id="e4e44-104">A strong name guarantees the uniqueness of an assembly by assigning a digital signature and a unique key pair.</span></span> <span data-ttu-id="e4e44-105">また、アセンブリの内容が最後にビルドされてから変更されていないことを保証するための整合性チェックも行えます。</span><span class="sxs-lookup"><span data-stu-id="e4e44-105">Additionally, a strong name provides an integrity check to guarantee that the content of the assembly has not changed since you last built it.</span></span>  
  
### <a name="to-create-a-strong-name-assembly-key-file"></a><span data-ttu-id="e4e44-106">厳密な名前のアセンブリー キー ファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="e4e44-106">To create a strong name assembly key file</span></span>  
  
1.  <span data-ttu-id="e4e44-107">開始**Visual Studio 2012 コマンド プロンプト**です。</span><span class="sxs-lookup"><span data-stu-id="e4e44-107">Start **Visual Studio 2012 Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="e4e44-108">コマンド プロンプトで、Contoso ソリューションの場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="e4e44-108">At the command prompt, move to the location of the Contoso solution.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e4e44-109">既定では、Contoso ソリューションの場所は*\<ドライブ >*: \Documents and 設定\\*\<ユーザー名 >*\My Documents\Visual Studio \<バージョン > \Projects です。</span><span class="sxs-lookup"><span data-stu-id="e4e44-109">By default, the location of the Contoso solution is *\<drive>*:\Documents and Settings\\*\<user name>*\My Documents\Visual Studio \<version>\Projects.</span></span>  
  
3.  <span data-ttu-id="e4e44-110">コマンド プロンプトで次のように入力します。 **sn-k FabConPriceAvail.snk**、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="e4e44-110">At the command prompt, type **sn -k FabConPriceAvail.snk**, and then press **Enter**.</span></span>  
  
4.  <span data-ttu-id="e4e44-111">コマンド プロンプトで次のように入力します。**終了**、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="e4e44-111">At the command prompt, type **Exit**, and then press **Enter**.</span></span>  
  
### <a name="to-assign-a-strong-name-to-your-assembly"></a><span data-ttu-id="e4e44-112">アセンブリに厳密な名前を割り当てるには</span><span class="sxs-lookup"><span data-stu-id="e4e44-112">To assign a strong name to your assembly</span></span>  
  
1.  <span data-ttu-id="e4e44-113">ソリューション エクスプ ローラーで右クリックし、 **ContosoPriceAndAvailability**プロジェクトをクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="e4e44-113">In Solution Explorer, right-click the **ContosoPriceAndAvailability** project, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="e4e44-114">プロパティ ページで、をクリックして**署名**左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="e4e44-114">In the Property Pages, click **Signing** in the left pane.</span></span>  
  
3.  <span data-ttu-id="e4e44-115">右側のペインで選択**アセンブリに署名**です。</span><span class="sxs-lookup"><span data-stu-id="e4e44-115">In the right pane, select **Sign the assembly**.</span></span>  
  
4.  <span data-ttu-id="e4e44-116">をクリックして**参照**厳密な名前キー ファイル フィールドの選択 でします。</span><span class="sxs-lookup"><span data-stu-id="e4e44-116">Click **Browse** in the Choose the strong name key file field.</span></span>  
  
5.  <span data-ttu-id="e4e44-117">プロジェクト フォルダで、選択、 **FabConPriceAvail.snk**クリックして、前に作成したファイルに**開く**です。</span><span class="sxs-lookup"><span data-stu-id="e4e44-117">Locate your project folder, select the **FabConPriceAvail.snk** file you created earlier, and then click **Open**.</span></span>  
  
6.  <span data-ttu-id="e4e44-118">をクリックして**OK**変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="e4e44-118">Click **OK** to save the changes.</span></span>  
  
7.  <span data-ttu-id="e4e44-119">ソリューション エクスプ ローラーで右クリックし、 **ContosoPriceAndAvailability**プロジェクトをクリックして**ビルド**です。</span><span class="sxs-lookup"><span data-stu-id="e4e44-119">In Solution Explorer, right-click the **ContosoPriceAndAvailability** project, and then click **Build**.</span></span> <span data-ttu-id="e4e44-120">ビルドが完了すると、もう一度、プロジェクトを右クリックし、クリックして**展開**です。</span><span class="sxs-lookup"><span data-stu-id="e4e44-120">After the build has succeeded, right-click the project again, and then click **Deploy**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4e44-121">参照</span><span class="sxs-lookup"><span data-stu-id="e4e44-121">See Also</span></span>  
 [<span data-ttu-id="e4e44-122">手順 2: Contoso 3 a 2 Price and Availability クエリ/応答シナリオ用のポートの作成</span><span class="sxs-lookup"><span data-stu-id="e4e44-122">Step 2: Creating Ports for the Contoso 3A2 Price and Availability Query/Response Scenario</span></span>](step-2-create-ports-for-contoso-3a2-price-and-availability-query.md)