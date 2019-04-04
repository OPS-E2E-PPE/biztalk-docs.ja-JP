---
title: JD Edwards OneWorld スキーマを BizTalk Server プロジェクトにインポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- generating schemas
- importing schemas
- schemas, generating
- schemas, importing into BizTalk Server projects
ms.assetid: 5bcaa276-8c76-4212-b373-de86e3008a69
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5954f92e55dac362387d66a8b65375e92fe187fa
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966147"
---
# <a name="importing-jd-edwards-oneworld-schemas-into-biztalk-server-projects"></a><span data-ttu-id="57d80-102">JD Edwards OneWorld スキーマを BizTalk Server プロジェクトにインポートする</span><span class="sxs-lookup"><span data-stu-id="57d80-102">Importing JD Edwards OneWorld Schemas into BizTalk Server Projects</span></span>
<span data-ttu-id="57d80-103">ここでは、JD Edwards OneWorld サーバーを参照し、スキーマを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロジェクトにインポートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="57d80-103">This topic discusses browsing a JD Edwards OneWorld server and importing the schemas into a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="57d80-104">arglist を設定したことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="57d80-104">You must ensure that you set the arglist.</span></span> <span data-ttu-id="57d80-105">オーケストレーションでスキーマを生成する前に、jdearglist.txt を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="57d80-105">You must update the jdearglist.txt before you generate the schemas in the orchestration.</span></span> <span data-ttu-id="57d80-106">詳細については、[文字列値の処理](../core/handling-string-values1.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57d80-106">For more information, see [Handling String Values](../core/handling-string-values1.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="57d80-107">Jdearglist を変更するたびにそのビジネス オブジェクトのスキーマを再生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="57d80-107">Each time that you change the jdearglist, you must regenerate the schemas for that business object.</span></span>  
  
 <span data-ttu-id="57d80-108">JD Edwards OneWorld 論理システムを作成した後、BizTalk Server プロジェクトから Microsoft アダプター ウィザードを開くことで、JD Edwards OneWorld を参照できます。</span><span class="sxs-lookup"><span data-stu-id="57d80-108">After creating the JD Edwards OneWorld logical system, you can browse JD Edwards OneWorld by opening the Microsoft Adapter Wizard from a BizTalk Server project.</span></span>  
  
### <a name="to-import-schemas"></a><span data-ttu-id="57d80-109">スキーマをインポートするには</span><span class="sxs-lookup"><span data-stu-id="57d80-109">To import schemas</span></span>  
  
1. <span data-ttu-id="57d80-110">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]を開きます。</span><span class="sxs-lookup"><span data-stu-id="57d80-110">Open [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
2. <span data-ttu-id="57d80-111">右クリックし、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロジェクトをポイントして、**追加**、選択および**生成した項目の追加**します。</span><span class="sxs-lookup"><span data-stu-id="57d80-111">Right-click the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project, point to **Add**, and select **Add Generated Items**.</span></span>  
  
3. <span data-ttu-id="57d80-112">をクリックして**アダプタの追加**を選択し、**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="57d80-112">Click **Add adapter**, and select **Open**.</span></span>  
  
4. <span data-ttu-id="57d80-113">アダプターを選択し、クリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="57d80-113">Select the adapter, and click **Next**.</span></span>  
  
    <span data-ttu-id="57d80-114">JD します。</span><span class="sxs-lookup"><span data-stu-id="57d80-114">The JD.</span></span> <span data-ttu-id="57d80-115">Edwards OneWorld XE システムは、ブラウザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="57d80-115">Edwards OneWorld XE system appears in the browser.</span></span>  
  
    <span data-ttu-id="57d80-116">![](../core/media/jdedadapter-04-jdebrowse.gif "JDEdAdapter_04_JDEBrowse")</span><span class="sxs-lookup"><span data-stu-id="57d80-116">![](../core/media/jdedadapter-04-jdebrowse.gif "JDEdAdapter_04_JDEBrowse")</span></span>  
  
    <span data-ttu-id="57d80-117">アダプター ウィザードには、定義されているすべてのシステムのツリーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="57d80-117">The Adapter Wizard displays a tree of all of the defined systems.</span></span> <span data-ttu-id="57d80-118">JD Edwards OneWorld には、1 つの長いリストに表示するには多すぎるほどのモジュールがあります。</span><span class="sxs-lookup"><span data-stu-id="57d80-118">JD Edwards OneWorld has too many modules to show in one long list.</span></span> <span data-ttu-id="57d80-119">モジュールは名前の最初の 3 文字に従ってグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="57d80-119">The modules are grouped together according to the first three characters of their name.</span></span>  
  
   - <span data-ttu-id="57d80-120">階層の最初のレベルはモジュール名のすべての 3 文字プレフィックスのリストです。</span><span class="sxs-lookup"><span data-stu-id="57d80-120">The first level of the hierarchy is the list of all three-character prefixes for the module names.</span></span>  
  
   - <span data-ttu-id="57d80-121">2 番目のレベルは同じ 3 文字プレフィックスを共有するすべてのモジュールのリストを示します。</span><span class="sxs-lookup"><span data-stu-id="57d80-121">The second level lists all the modules that share the same three-character prefix.</span></span>  
  
   - <span data-ttu-id="57d80-122">最後のレベルはモジュールに属するビジネス関数のリストを示します。</span><span class="sxs-lookup"><span data-stu-id="57d80-122">The last level lists the business functions belonging to a module.</span></span> <span data-ttu-id="57d80-123">サービス アイコンを展開すると、その操作を表示できます。</span><span class="sxs-lookup"><span data-stu-id="57d80-123">When you expand the services icon you can view its operations.</span></span>  
  
     <span data-ttu-id="57d80-124">操作を展開すると、入出力引数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="57d80-124">Expanding an operation displays the input/output arguments.</span></span>  
  
     <span data-ttu-id="57d80-125">入出力引数を展開すると、引数のデータ型が表示されます。</span><span class="sxs-lookup"><span data-stu-id="57d80-125">You can expand the input/output arguments to view the data types of the arguments.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="57d80-126">サーバー オブジェクト定義が変更されると、スキーマを再生成し、そのデータを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="57d80-126">If the server object definitions change, you must regenerate the schema to refresh the data it contains.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="57d80-127">スキーマの生成後に jdearglist.txt を変更した場合、スキーマを再生成してそのデータを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="57d80-127">If you change jdearglist.txt after generating your schema, you must regenerate the schema to refresh the data it contains.</span></span> <span data-ttu-id="57d80-128">Jdearglist.txt についてを参照してください[文字列値の処理](../core/handling-string-values1.md)します。</span><span class="sxs-lookup"><span data-stu-id="57d80-128">For information on jdearglist.txt, see to [Handling String Values](../core/handling-string-values1.md).</span></span>  
  
## <a name="generating-schemas"></a><span data-ttu-id="57d80-129">スキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="57d80-129">Generating Schemas</span></span>  
 <span data-ttu-id="57d80-130">スキーマを生成するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="57d80-130">Use the following procedure to generate schemas.</span></span>  
  
#### <a name="to-generate-schemas"></a><span data-ttu-id="57d80-131">スキーマを生成するには</span><span class="sxs-lookup"><span data-stu-id="57d80-131">To generate schemas</span></span>  
  
1.  <span data-ttu-id="57d80-132">スキーマをインポートする項目を選択します。</span><span class="sxs-lookup"><span data-stu-id="57d80-132">Select the item for which you want to import schemas.</span></span>  
  
2.  <span data-ttu-id="57d80-133">項目を追加する をクリックします (またはドラッグ)、**送信**ウィンドウ (J. Edwards OneWorld への受信の呼び出し)。</span><span class="sxs-lookup"><span data-stu-id="57d80-133">Click (or drag) to add the item to the **Transmit** pane (for an inbound to J. Edwards OneWorld call).</span></span>  
  
3.  <span data-ttu-id="57d80-134">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="57d80-134">Click **OK**.</span></span>  
  
     <span data-ttu-id="57d80-135">選択した JD Edwards OneWorld 項目に対して生成されたスキーマが BizTalk Server プロジェクトにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="57d80-135">Schemas generated for the selected JD Edwards OneWorld item are imported into the BizTalk Server project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="57d80-136">AddressBook (N0100041) を使用する場合、フィールド名は**cActionCode**します。</span><span class="sxs-lookup"><span data-stu-id="57d80-136">When using AddressBook (N0100041) the field name is **cActionCode**.</span></span> <span data-ttu-id="57d80-137">アクションは XML ファイル自体の一部です。</span><span class="sxs-lookup"><span data-stu-id="57d80-137">The action is part of the XML file itself.</span></span> <span data-ttu-id="57d80-138">コードは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="57d80-138">The codes are:</span></span>  
>   
>  <span data-ttu-id="57d80-139">--A は追加</span><span class="sxs-lookup"><span data-stu-id="57d80-139">--A for Add</span></span>  
>   
>  <span data-ttu-id="57d80-140">--C は変更</span><span class="sxs-lookup"><span data-stu-id="57d80-140">--C for Change</span></span>  
>   
>  <span data-ttu-id="57d80-141">--D は削除</span><span class="sxs-lookup"><span data-stu-id="57d80-141">--D for Delete</span></span>  
>   
>  <span data-ttu-id="57d80-142">--I は照会</span><span class="sxs-lookup"><span data-stu-id="57d80-142">--I for Inquiry</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57d80-143">参照</span><span class="sxs-lookup"><span data-stu-id="57d80-143">See Also</span></span>  
 [<span data-ttu-id="57d80-144">BizTalk 管理へのアイテムの追加</span><span class="sxs-lookup"><span data-stu-id="57d80-144">Add the artifacts to BizTalk Administration</span></span>](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)