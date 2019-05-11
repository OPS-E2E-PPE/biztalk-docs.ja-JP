---
title: 手順 1:Contoso アセンブリへの厳密な名前の割り当て |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, assigning strong-names
- strong-named assemblies
ms.assetid: c8ec4593-5a4d-47ab-8799-7b2cd3d15ffc
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 17ce82403581101a2cc88749a40cbdb786e54a97
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281704"
---
# <a name="step-1-assigning-a-strong-name-to-the-contoso-assembly"></a><span data-ttu-id="3d961-102">手順 1:Contoso アセンブリへの厳密な名前の割り当てください。</span><span class="sxs-lookup"><span data-stu-id="3d961-102">Step 1: Assigning a Strong Name to the Contoso Assembly</span></span>
<span data-ttu-id="3d961-103">この手順では、作成し、BizTalk アセンブリの厳密な名前を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="3d961-103">In this step, you create and assign a strong name for your BizTalk assembly.</span></span> <span data-ttu-id="3d961-104">厳密な名前では、デジタル署名と一意キーのペアを割り当てることで、アセンブリの一意性を保証します。</span><span class="sxs-lookup"><span data-stu-id="3d961-104">A strong name guarantees the uniqueness of an assembly by assigning a digital signature and a unique key pair.</span></span> <span data-ttu-id="3d961-105">さらに、厳密な名前は、アセンブリの内容が前回のビルド以降に変更していないことを保証するために、整合性チェックを提供します。</span><span class="sxs-lookup"><span data-stu-id="3d961-105">Additionally, a strong name provides an integrity check to guarantee that the content of the assembly has not changed since you last built it.</span></span>  
  
### <a name="to-create-a-strong-name-assembly-key-file"></a><span data-ttu-id="3d961-106">厳密な名前のアセンブリー キー ファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="3d961-106">To create a strong name assembly key file</span></span>  
  
1.  <span data-ttu-id="3d961-107">開始**Visual Studio 2012 のコマンド プロンプト**します。</span><span class="sxs-lookup"><span data-stu-id="3d961-107">Start **Visual Studio 2012 Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="3d961-108">コマンド プロンプトで、Contoso ソリューションの場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="3d961-108">At the command prompt, move to the location of the Contoso solution.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3d961-109">既定では、Contoso ソリューションの場所は*\<ドライブ\>*: \Documents and Settings\\*\<ユーザー名\>* \MyDocuments \visual Studio\<バージョン\>\Projects です。</span><span class="sxs-lookup"><span data-stu-id="3d961-109">By default, the location of the Contoso solution is *\<drive\>*:\Documents and Settings\\*\<user name\>* \My Documents\Visual Studio \<version\>\Projects.</span></span>  
  
3.  <span data-ttu-id="3d961-110">コマンド プロンプトで「 **sn-k FabConPriceAvail.snk**、キーを押しますと **」と入力**します。</span><span class="sxs-lookup"><span data-stu-id="3d961-110">At the command prompt, type **sn -k FabConPriceAvail.snk**, and then press **Enter**.</span></span>  
  
4.  <span data-ttu-id="3d961-111">コマンド プロンプトで「**終了**、押します **」と入力**します。</span><span class="sxs-lookup"><span data-stu-id="3d961-111">At the command prompt, type **Exit**, and then press **Enter**.</span></span>  
  
### <a name="to-assign-a-strong-name-to-your-assembly"></a><span data-ttu-id="3d961-112">アセンブリに厳密な名前を割り当てる</span><span class="sxs-lookup"><span data-stu-id="3d961-112">To assign a strong name to your assembly</span></span>  
  
1.  <span data-ttu-id="3d961-113">ソリューション エクスプ ローラーで右クリックし、 **ContosoPriceAndAvailability**プロジェクトをクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="3d961-113">In Solution Explorer, right-click the **ContosoPriceAndAvailability** project, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="3d961-114">[プロパティ ページ] でクリックして**署名**左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="3d961-114">In the Property Pages, click **Signing** in the left pane.</span></span>  
  
3.  <span data-ttu-id="3d961-115">右側のウィンドウで次のように選択します。**アセンブリに署名**します。</span><span class="sxs-lookup"><span data-stu-id="3d961-115">In the right pane, select **Sign the assembly**.</span></span>  
  
4.  <span data-ttu-id="3d961-116">クリックして**参照**厳密な名前キー ファイルのフィールドの選択 でします。</span><span class="sxs-lookup"><span data-stu-id="3d961-116">Click **Browse** in the Choose the strong name key file field.</span></span>  
  
5.  <span data-ttu-id="3d961-117">プロジェクト フォルダーを見つけ、選択、 **FabConPriceAvail.snk**クリックして、先ほど作成したファイルに**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="3d961-117">Locate your project folder, select the **FabConPriceAvail.snk** file you created earlier, and then click **Open**.</span></span>  
  
6.  <span data-ttu-id="3d961-118">**[OK]** をクリックして変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="3d961-118">Click **OK** to save the changes.</span></span>  
  
7.  <span data-ttu-id="3d961-119">ソリューション エクスプ ローラーで右クリックし、 **[contosopriceandavailability]** プロジェクトをクリックして**ビルド**します。</span><span class="sxs-lookup"><span data-stu-id="3d961-119">In Solution Explorer, right-click the **ContosoPriceAndAvailability** project, and then click **Build**.</span></span> <span data-ttu-id="3d961-120">ビルドが完了すると、もう一度、プロジェクトを右クリックし、クリックして**デプロイ**します。</span><span class="sxs-lookup"><span data-stu-id="3d961-120">After the build has succeeded, right-click the project again, and then click **Deploy**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d961-121">参照</span><span class="sxs-lookup"><span data-stu-id="3d961-121">See Also</span></span>  
 [<span data-ttu-id="3d961-122">手順 2:Contoso 3 a 2 Price and Availability クエリ/応答シナリオ用のポートの作成</span><span class="sxs-lookup"><span data-stu-id="3d961-122">Step 2: Creating Ports for the Contoso 3A2 Price and Availability Query/Response Scenario</span></span>](step-2-create-ports-for-contoso-3a2-price-and-availability-query.md)