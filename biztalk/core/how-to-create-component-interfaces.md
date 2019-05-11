---
title: コンポーネント インターフェイスを作成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating component interfaces
- component interfaces, creating
ms.assetid: 9def053a-cbf6-4b34-b2e8-b2d03bffc5fe
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 778f9b59db2712fffb50d5e83e55155386ed81d9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65339445"
---
# <a name="how-to-create-component-interfaces"></a><span data-ttu-id="1cf2d-102">コンポーネント インターフェイスを作成する方法</span><span class="sxs-lookup"><span data-stu-id="1cf2d-102">How to Create Component Interfaces</span></span>
<span data-ttu-id="1cf2d-103">PeopleSoft アプリケーション デザイナを使用してコンポーネント インターフェイスを作成します。</span><span class="sxs-lookup"><span data-stu-id="1cf2d-103">You create component interfaces using the PeopleSoft Application Designer.</span></span> <span data-ttu-id="1cf2d-104">(アプリケーション デザイナーの詳細については、PeopleSoft Enterprise のドキュメントを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="1cf2d-104">(For more information about Application Designer, see the PeopleSoft Enterprise documentation.)</span></span>  
  
 <span data-ttu-id="1cf2d-105">コンポーネント ビュー内のレコードからプロパティを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="1cf2d-105">You can add properties from the records in the component view.</span></span> <span data-ttu-id="1cf2d-106">コンポーネント インターフェイスで公開したくないプロパティを削除できます。</span><span class="sxs-lookup"><span data-stu-id="1cf2d-106">In the component interface, you can delete a property that you do not want to expose.</span></span> <span data-ttu-id="1cf2d-107">プロパティの名前を変更するには、プロパティをクリックして新しい名前を入力するまでもう一度クリックします。</span><span class="sxs-lookup"><span data-stu-id="1cf2d-107">You can rename properties by clicking the property and then clicking again until you can type a new name.</span></span> <span data-ttu-id="1cf2d-108">プロパティの名前を変更する場合参照できますが、コンポーネント インターフェイスで新しい名前のみで、基になるコンポーネント名ではなく。</span><span class="sxs-lookup"><span data-stu-id="1cf2d-108">If you rename a property, you can reference it in the component interface only by the new name, not by the underlying component name.</span></span>  
  
 <span data-ttu-id="1cf2d-109">プロパティには、さまざまなアイコンに隣接する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1cf2d-109">Properties may have various icons adjacent to them.</span></span> <span data-ttu-id="1cf2d-110">たとえば、EMPLID には、基になるレコードからキー フィールドであることを示すアイコンがあります。</span><span class="sxs-lookup"><span data-stu-id="1cf2d-110">For example, EMPLID has an icon that indicates that it is a key field from the underlying record.</span></span> <span data-ttu-id="1cf2d-111">名前が、アイコンを基になるレコードからの代替キー フィールドであることを示します。</span><span class="sxs-lookup"><span data-stu-id="1cf2d-111">NAME has an icon that indicates that it is an alternate key field from the underlying record.</span></span> <span data-ttu-id="1cf2d-112">(プロパティのアイコンの一覧は、PeopleBooks のドキュメントを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="1cf2d-112">(For a complete list of property icons, see the PeopleBooks documentation.)</span></span>  
  
### <a name="creating-a-new-component-interface"></a><span data-ttu-id="1cf2d-113">新しいコンポーネント インターフェイスを作成します。</span><span class="sxs-lookup"><span data-stu-id="1cf2d-113">Creating a new component interface</span></span>  
  
1.  <span data-ttu-id="1cf2d-114">PeopleSoft アプリケーション デザイナーを開きます。</span><span class="sxs-lookup"><span data-stu-id="1cf2d-114">Open the PeopleSoft Application Designer.</span></span>  
  
2.  <span data-ttu-id="1cf2d-115">**[ファイル]** メニューの **[新規作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1cf2d-115">On the **File** menu, click **New**.</span></span>  
  
     <span data-ttu-id="1cf2d-116">![](../core/media/psadapter-42-ps-new-compinterface.gif "PSAdapter_42_PS_New_CompInterface")</span><span class="sxs-lookup"><span data-stu-id="1cf2d-116">![](../core/media/psadapter-42-ps-new-compinterface.gif "PSAdapter_42_PS_New_CompInterface")</span></span>  
  
3.  <span data-ttu-id="1cf2d-117">**新規**ダイアログ ボックスで、**コンポーネント インターフェイス**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="1cf2d-117">In the **New** dialog box, select **Component Interface**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="1cf2d-118">![](../core/media/psadapter-43-ps-selectsourcecomp.gif "PSAdapter_43_PS_SelectSourceComp")</span><span class="sxs-lookup"><span data-stu-id="1cf2d-118">![](../core/media/psadapter-43-ps-selectsourcecomp.gif "PSAdapter_43_PS_SelectSourceComp")</span></span>  
  
4.  <span data-ttu-id="1cf2d-119">**のコンポーネント インターフェイスの変換元コンポーネントの選択**ウィンドウで、クリックして、コンポーネント インターフェイスの基礎として使用するコンポーネントを選択**選択**します。</span><span class="sxs-lookup"><span data-stu-id="1cf2d-119">In the **Select Source Component for Component Interface** window, select the component to use as a basis for the component interface, and then click **Select**.</span></span>  
  
     <span data-ttu-id="1cf2d-120">![](../core/media/psadapter-44-ps-appdesigner1.gif "PSAdapter_44_PS_AppDesigner1")</span><span class="sxs-lookup"><span data-stu-id="1cf2d-120">![](../core/media/psadapter-44-ps-appdesigner1.gif "PSAdapter_44_PS_AppDesigner1")</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1cf2d-121">コンポーネント インターフェイスのサイズが大きい場合は、手動でコンポーネントのプロパティを公開します。</span><span class="sxs-lookup"><span data-stu-id="1cf2d-121">If the component interface is large, expose the component properties manually.</span></span>  
  
5.  <span data-ttu-id="1cf2d-122">**アプリケーション デザイナー**  ダイアログ ボックスで、次のオプションのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="1cf2d-122">In the **Application Designer** dialog box, choose one of the following options:</span></span>  
  
    -   <span data-ttu-id="1cf2d-123">クリックして**いいえ**プロパティを表示せずに、コンポーネント インターフェイスを作成して、コンポーネントのプロパティを手動で公開します。</span><span class="sxs-lookup"><span data-stu-id="1cf2d-123">Click **No** to create the component interface without displaying properties and to expose component properties manually.</span></span>  
  
         <span data-ttu-id="1cf2d-124">A.</span><span class="sxs-lookup"><span data-stu-id="1cf2d-124">a.</span></span> <span data-ttu-id="1cf2d-125">左側のペインから右側のペインに関連するフィールドをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="1cf2d-125">Drag the relevant fields from the left pane to the right pane.</span></span>  
  
         <span data-ttu-id="1cf2d-126">B.</span><span class="sxs-lookup"><span data-stu-id="1cf2d-126">b.</span></span> <span data-ttu-id="1cf2d-127">実行するさまざまな機能を選択するには、かに応じてどのペインがアクティブの右側または左側のウィンドウを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="1cf2d-127">To select various functions to perform, right-click either the right or left pane, depending on which pane is active.</span></span>  
  
         <span data-ttu-id="1cf2d-128">関数の完全な一覧は、PeopleBooks のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1cf2d-128">For a complete list of functions, see the PeopleBooks documentation.</span></span>  
  
    -   <span data-ttu-id="1cf2d-129">クリックして**はい**コンポーネント インターフェイスを作成し、基になるコンポーネント インターフェイスのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="1cf2d-129">Click **Yes** to create the component interface and display the properties of the underlying component interface.</span></span>  
  
         <span data-ttu-id="1cf2d-130">![](../core/media/psadapter-45-ps-appdesigner2.gif "PSAdapter_45_PS_AppDesigner2")</span><span class="sxs-lookup"><span data-stu-id="1cf2d-130">![](../core/media/psadapter-45-ps-appdesigner2.gif "PSAdapter_45_PS_AppDesigner2")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cf2d-131">参照</span><span class="sxs-lookup"><span data-stu-id="1cf2d-131">See Also</span></span>  
 <span data-ttu-id="1cf2d-132">[コンポーネント インターフェイスの標準メソッド](../core/standard-methods-in-component-interfaces.md) </span><span class="sxs-lookup"><span data-stu-id="1cf2d-132">[Standard Methods in Component Interfaces](../core/standard-methods-in-component-interfaces.md) </span></span>  
 <span data-ttu-id="1cf2d-133">[付録 c:コンポーネント インターフェイスの使用](../core/appendix-c-using-component-interfaces.md) </span><span class="sxs-lookup"><span data-stu-id="1cf2d-133">[Appendix C: Using Component Interfaces](../core/appendix-c-using-component-interfaces.md) </span></span>  
 [<span data-ttu-id="1cf2d-134">付録 a:コンポーネント インターフェイス メソッド</span><span class="sxs-lookup"><span data-stu-id="1cf2d-134">Appendix A: Component Interface Methods</span></span>](../core/appendix-a-component-interface-methods.md)