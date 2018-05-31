---
title: コンポーネント インターフェイスを作成する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 86ee68edba66b05d3c2541dd9c41cc074bd790b7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249298"
---
# <a name="how-to-create-component-interfaces"></a><span data-ttu-id="3ad68-102">コンポーネント インターフェイスの作成方法</span><span class="sxs-lookup"><span data-stu-id="3ad68-102">How to Create Component Interfaces</span></span>
<span data-ttu-id="3ad68-103">コンポーネント インターフェイスは、PeopleSoft アプリケーション デザイナーを使用して作成します </span><span class="sxs-lookup"><span data-stu-id="3ad68-103">You create component interfaces using the PeopleSoft Application Designer.</span></span> <span data-ttu-id="3ad68-104">(アプリケーション デザイナの詳細については、PeopleSoft Enterprise のドキュメントを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="3ad68-104">(For more information about Application Designer, see the PeopleSoft Enterprise documentation.)</span></span>  
  
 <span data-ttu-id="3ad68-105">コンポーネント ビューでは、レコードからプロパティを追加できます。</span><span class="sxs-lookup"><span data-stu-id="3ad68-105">You can add properties from the records in the component view.</span></span> <span data-ttu-id="3ad68-106">コンポーネント インターフェイスで、公開しないプロパティを削除できます。</span><span class="sxs-lookup"><span data-stu-id="3ad68-106">In the component interface, you can delete a property that you do not want to expose.</span></span> <span data-ttu-id="3ad68-107">プロパティをクリックし、新しい名前を入力できるようになるまで繰り返しクリックすることにより、プロパティの名前を変更できます。</span><span class="sxs-lookup"><span data-stu-id="3ad68-107">You can rename properties by clicking the property and then clicking again until you can type a new name.</span></span> <span data-ttu-id="3ad68-108">プロパティの名前を変更した場合は、コンポーネント インターフェイスで、基になるコンポーネント名ではなく、新しい名前のみでそのプロパティを参照できます。</span><span class="sxs-lookup"><span data-stu-id="3ad68-108">If you rename a property, you can reference it in the component interface only by the new name, not by the underlying component name.</span></span>  
  
 <span data-ttu-id="3ad68-109">プロパティには、その横にさまざまなアイコンがある場合があります。</span><span class="sxs-lookup"><span data-stu-id="3ad68-109">Properties may have various icons adjacent to them.</span></span> <span data-ttu-id="3ad68-110">たとえば、EMPLID には、それが基になるレコードからのキー フィールドであることを示すアイコンがあります。</span><span class="sxs-lookup"><span data-stu-id="3ad68-110">For example, EMPLID has an icon that indicates that it is a key field from the underlying record.</span></span> <span data-ttu-id="3ad68-111">NAME には、それが基になるレコードからの代替キー フィールドであることを示すアイコンがあります </span><span class="sxs-lookup"><span data-stu-id="3ad68-111">NAME has an icon that indicates that it is an alternate key field from the underlying record.</span></span> <span data-ttu-id="3ad68-112">(全プロパティ アイコンの一覧については、PeopleBooks のドキュメントを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="3ad68-112">(For a complete list of property icons, see the PeopleBooks documentation.)</span></span>  
  
### <a name="creating-a-new-component-interface"></a><span data-ttu-id="3ad68-113">新しいコンポーネント インターフェイスの作成</span><span class="sxs-lookup"><span data-stu-id="3ad68-113">Creating a new component interface</span></span>  
  
1.  <span data-ttu-id="3ad68-114">PeopleSoft アプリケーション デザイナを開きます。</span><span class="sxs-lookup"><span data-stu-id="3ad68-114">Open the PeopleSoft Application Designer.</span></span>  
  
2.  <span data-ttu-id="3ad68-115">**[ファイル]** メニューの **[新規作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3ad68-115">On the **File** menu, click **New**.</span></span>  
  
     ![](../core/media/psadapter-42-ps-new-compinterface.gif "PSAdapter_42_PS_New_CompInterface")  
  
3.  <span data-ttu-id="3ad68-116">**新規**ダイアログ ボックスで、**コンポーネント インターフェイス**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="3ad68-116">In the **New** dialog box, select **Component Interface**, and then click **OK**.</span></span>  
  
     ![](../core/media/psadapter-43-ps-selectsourcecomp.gif "PSAdapter_43_PS_SelectSourceComp")  
  
4.  <span data-ttu-id="3ad68-117">**コンポーネント インターフェイスのソース コンポーネントを選択して**ウィンドウで、コンポーネント インターフェイスの基礎として使用し、をクリックするコンポーネントを選択**選択**です。</span><span class="sxs-lookup"><span data-stu-id="3ad68-117">In the **Select Source Component for Component Interface** window, select the component to use as a basis for the component interface, and then click **Select**.</span></span>  
  
     ![](../core/media/psadapter-44-ps-appdesigner1.gif "PSAdapter_44_PS_AppDesigner1")  
  
    > [!NOTE]
    >  <span data-ttu-id="3ad68-118">コンポーネント インターフェイスが大きい場合は、コンポーネントのプロパティを手動で公開します。</span><span class="sxs-lookup"><span data-stu-id="3ad68-118">If the component interface is large, expose the component properties manually.</span></span>  
  
5.  <span data-ttu-id="3ad68-119">**アプリケーション デザイナー**  ダイアログ ボックスで、次のオプションのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="3ad68-119">In the **Application Designer** dialog box, choose one of the following options:</span></span>  
  
    -   <span data-ttu-id="3ad68-120">をクリックして**いいえ**プロパティを表示することがなく、コンポーネント インターフェイスを作成して、コンポーネントのプロパティを手動で公開します。</span><span class="sxs-lookup"><span data-stu-id="3ad68-120">Click **No** to create the component interface without displaying properties and to expose component properties manually.</span></span>  
  
         <span data-ttu-id="3ad68-121">a.</span><span class="sxs-lookup"><span data-stu-id="3ad68-121">a.</span></span> <span data-ttu-id="3ad68-122">左側のペインから右側のペインに関連するフィールドをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="3ad68-122">Drag the relevant fields from the left pane to the right pane.</span></span>  
  
         <span data-ttu-id="3ad68-123">b.</span><span class="sxs-lookup"><span data-stu-id="3ad68-123">b.</span></span> <span data-ttu-id="3ad68-124">実行するさまざまな機能を選択するには、か、どのウィンドウがアクティブなに応じての右または左のペインを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="3ad68-124">To select various functions to perform, right-click either the right or left pane, depending on which pane is active.</span></span>  
  
         <span data-ttu-id="3ad68-125">全機能の一覧については、PeopleBooks のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ad68-125">For a complete list of functions, see the PeopleBooks documentation.</span></span>  
  
    -   <span data-ttu-id="3ad68-126">をクリックして**はい**コンポーネント インターフェイスを作成し、基になるコンポーネント インターフェイスのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="3ad68-126">Click **Yes** to create the component interface and display the properties of the underlying component interface.</span></span>  
  
         ![](../core/media/psadapter-45-ps-appdesigner2.gif "PSAdapter_45_PS_AppDesigner2")  
  
## <a name="see-also"></a><span data-ttu-id="3ad68-127">参照</span><span class="sxs-lookup"><span data-stu-id="3ad68-127">See Also</span></span>  
 <span data-ttu-id="3ad68-128">[コンポーネント インターフェイスの標準メソッド](../core/standard-methods-in-component-interfaces.md) </span><span class="sxs-lookup"><span data-stu-id="3ad68-128">[Standard Methods in Component Interfaces](../core/standard-methods-in-component-interfaces.md) </span></span>  
 <span data-ttu-id="3ad68-129">[付録 c: コンポーネント インターフェイスの使用](../core/appendix-c-using-component-interfaces.md) </span><span class="sxs-lookup"><span data-stu-id="3ad68-129">[Appendix C: Using Component Interfaces](../core/appendix-c-using-component-interfaces.md) </span></span>  
 [<span data-ttu-id="3ad68-130">付録 a: コンポーネント インターフェイス メソッド</span><span class="sxs-lookup"><span data-stu-id="3ad68-130">Appendix A: Component Interface Methods</span></span>](../core/appendix-a-component-interface-methods.md)