---
title: コンポーネント インターフェイスをテストする方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- testing component interfaces
- component interfaces, testing
ms.assetid: d637f76d-170d-4543-a2b2-a4ac4001386b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be50521e5c4421d8ac8902bcf7a414d734c3b9f8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256570"
---
# <a name="how-to-test-component-interfaces"></a><span data-ttu-id="1e842-102">コンポーネント インターフェイスをテストする方法</span><span class="sxs-lookup"><span data-stu-id="1e842-102">How to Test Component Interfaces</span></span>
<span data-ttu-id="1e842-103">Microsoft BizTalk Adapter for PeopleSoft Enterprise は PeopleSoft メタデータとコンポーネント インターフェイスを使用するため、新規または変更したコンポーネント インターフェイスを処理できます。</span><span class="sxs-lookup"><span data-stu-id="1e842-103">Microsoft BizTalk Adapter for PeopleSoft Enterprise uses PeopleSoft metadata and component interfaces; therefore, it can handle new or modified component interfaces.</span></span> <span data-ttu-id="1e842-104">アダプタは、コンポーネント インターフェイスが論理的かつ有効であることを除き、コンポーネント インターフェイスについて想定を行いません。</span><span class="sxs-lookup"><span data-stu-id="1e842-104">The adapter makes no assumptions about component interfaces except that they are logical and valid.</span></span> <span data-ttu-id="1e842-105">したがって、各コンポーネント インターフェイスをアダプタのソースとして使用する前にテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e842-105">Therefore, each component interface must be tested before it is used as a source for the adapter.</span></span>  
  
 <span data-ttu-id="1e842-106">ユーザーまたは PeopleSoft のアップグレードによって基になるアプリケーションに変更が加えられ、その変更によってコンポーネント インターフェイスが無効になる場合は、無効なコンポーネント インターフェイスをアダプタが使用する前に修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e842-106">If changes are made to the underlying application by the user or by a PeopleSoft upgrade, and the changes invalidate a component interface, the user must repair the invalid component interface before the adapter uses it.</span></span>  
  
### <a name="to-test-a-component-interface"></a><span data-ttu-id="1e842-107">コンポーネント インターフェイスをテストするには</span><span class="sxs-lookup"><span data-stu-id="1e842-107">To test a component interface</span></span>  
  
1.  <span data-ttu-id="1e842-108">アプリケーション デザイナーでの**ツール** メニューのをクリックして**Test Component Interface**です。</span><span class="sxs-lookup"><span data-stu-id="1e842-108">In Application Designer, on the **Tools** menu, click **Test Component Interface**.</span></span>  
  
     ![](../core/media/psadapter-54-ps-testcompinterface1.gif "PSAdapter_54_PS_TestCompInterface1")  
  
2.  <span data-ttu-id="1e842-109">**Component Interface Tester**  ダイアログ ボックスで、1 つに、次のメソッドを使用してコンポーネント インターフェイスをテストします。</span><span class="sxs-lookup"><span data-stu-id="1e842-109">In the **Component Interface Tester** dialog box, test the component interface by using one the following methods.</span></span> <span data-ttu-id="1e842-110">変更を加えたら、ペインの一番上にあるアイテムを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="1e842-110">After you finish making changes, right-click the top item in the pane.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1e842-111">必要に応じて、ダイアログ ボックスをクリックして前面に表示します。</span><span class="sxs-lookup"><span data-stu-id="1e842-111">If required, click the dialog box to bring it to the foreground.</span></span>  
  
    -   <span data-ttu-id="1e842-112">Find メソッドを使用してコンポーネント インターフェイスをテストするには、クリックして**検索**です。</span><span class="sxs-lookup"><span data-stu-id="1e842-112">To test the component interface using the Find method, click **Find**.</span></span>  
  
         <span data-ttu-id="1e842-113">**Component Interface Tester - の検索結果** ダイアログ ボックスが開き、基になるコンポーネントの考えられるすべてのエントリを表示します。</span><span class="sxs-lookup"><span data-stu-id="1e842-113">The **Component Interface Tester - Find Results** dialog box opens, displaying all the possible entries for the underlying component.</span></span> <span data-ttu-id="1e842-114">エントリの数が 300 を超える場合は、メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1e842-114">If there are more than 300 entries, a message appears.</span></span>  
  
         <span data-ttu-id="1e842-115">a.</span><span class="sxs-lookup"><span data-stu-id="1e842-115">a.</span></span> <span data-ttu-id="1e842-116">左側のウィンドウで、**検索結果** ダイアログ ボックスでフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="1e842-116">In the left pane of the **Find Results** dialog box, select a field.</span></span>  
  
         <span data-ttu-id="1e842-117">b.</span><span class="sxs-lookup"><span data-stu-id="1e842-117">b.</span></span> <span data-ttu-id="1e842-118">その特定のフィールドに関連するデータを表示する をクリックして**Get Selected**です。</span><span class="sxs-lookup"><span data-stu-id="1e842-118">To display the relevant data for that particular field, click **Get Selected**.</span></span>  
  
         <span data-ttu-id="1e842-119">次の画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1e842-119">The following screen appears.</span></span>  
  
         ![](../core/media/psadapter-55-ps-testcompinterface2.gif "PSAdapter_55_PS_TestCompInterface2")  
  
         <span data-ttu-id="1e842-120">セキュリティ設定で許可される場合は、各フィールドの値を変更できます。</span><span class="sxs-lookup"><span data-stu-id="1e842-120">If the security settings allow, you can change the values in the individual fields.</span></span>  
  
         <span data-ttu-id="1e842-121">次のダイアログ ボックスが開きます。</span><span class="sxs-lookup"><span data-stu-id="1e842-121">The following dialog box opens.</span></span>  
  
         ![](../core/media/psadapter-56-ps-testcompinterface3.gif "PSAdapter_56_PS_TestCompInterface3")  
  
    -   <span data-ttu-id="1e842-122">使用してをコンポーネント インターフェイスをテストする、`Get`メソッド。</span><span class="sxs-lookup"><span data-stu-id="1e842-122">To test the component interface using the `Get` method:</span></span>  
  
         <span data-ttu-id="1e842-123">a.</span><span class="sxs-lookup"><span data-stu-id="1e842-123">a.</span></span> <span data-ttu-id="1e842-124">既存のキーを入力します。</span><span class="sxs-lookup"><span data-stu-id="1e842-124">Enter the existing key(s).</span></span>  
  
         <span data-ttu-id="1e842-125">b.</span><span class="sxs-lookup"><span data-stu-id="1e842-125">b.</span></span> <span data-ttu-id="1e842-126">をクリックして**既存**です。</span><span class="sxs-lookup"><span data-stu-id="1e842-126">Click **Get Existing**.</span></span>  
  
         <span data-ttu-id="1e842-127">入力したキーについて公開されているプロパティが返されます。</span><span class="sxs-lookup"><span data-stu-id="1e842-127">This returns the exposed properties for the key that you entered.</span></span>  
  
         <span data-ttu-id="1e842-128">値を変更するには、場合**更新アクセス**が指定されました。</span><span class="sxs-lookup"><span data-stu-id="1e842-128">You can change values if **Update access** was specified.</span></span>  
  
         <span data-ttu-id="1e842-129">または、`Create` メソッドを使用してテストすることもできます。</span><span class="sxs-lookup"><span data-stu-id="1e842-129">Alternatively, you can test using the `Create` method.</span></span>  
  
         ![](../core/media/psadapter-57-ps-testcompinterface4.gif "PSAdapter_57_PS_TestCompInterface4")  
  
    -   <span data-ttu-id="1e842-130">使用してをコンポーネント インターフェイスをテストする、`Create`メソッド。</span><span class="sxs-lookup"><span data-stu-id="1e842-130">To test the component interface using the `Create` method:</span></span>  
  
         <span data-ttu-id="1e842-131">a.</span><span class="sxs-lookup"><span data-stu-id="1e842-131">a.</span></span> <span data-ttu-id="1e842-132">必要なすべてのキー値を入力します。</span><span class="sxs-lookup"><span data-stu-id="1e842-132">Enter all required key values.</span></span>  
  
         <span data-ttu-id="1e842-133">b.</span><span class="sxs-lookup"><span data-stu-id="1e842-133">b.</span></span> <span data-ttu-id="1e842-134">をクリックして**新規作成**です。</span><span class="sxs-lookup"><span data-stu-id="1e842-134">Click **Create New**.</span></span>  
  
         <span data-ttu-id="1e842-135">有効な値を入力すると**キーを作成する**場所の既定データとテーブル名が展開された後に、JOBCODE データを表示するウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="1e842-135">When you enter valid values in **Create keys**, a pane that displays the JOBCODE data opens after the Table name is expanded with default data in place.</span></span>  
  
         <span data-ttu-id="1e842-136">この段階で、フィールドを変更できます。</span><span class="sxs-lookup"><span data-stu-id="1e842-136">You can change fields now.</span></span>  
  
         ![](../core/media/psadapter-58-ps-testcompinterface5.gif "PSAdapter_58_PS_TestCompInterface5")  
  
         <span data-ttu-id="1e842-137">コンポーネントの基になるビジネス ロジックに対して、変更が検証されます。</span><span class="sxs-lookup"><span data-stu-id="1e842-137">Changes are validated against the component's underlying business logic.</span></span>  
  
3.  <span data-ttu-id="1e842-138">をクリックして変更を保存、**保存**アイコン。</span><span class="sxs-lookup"><span data-stu-id="1e842-138">To save your changes, click the **Save** icon.</span></span>  
  
     <span data-ttu-id="1e842-139">レコードの作成に使用されるキーは、データを表示するために Get メソッドと共に使用できます。</span><span class="sxs-lookup"><span data-stu-id="1e842-139">The keys used to create the record can be used with the Get method for viewing data.</span></span> <span data-ttu-id="1e842-140">追加されたデータは、次の例に示すように、PeopleSoft コンポーネントで表示できます。</span><span class="sxs-lookup"><span data-stu-id="1e842-140">The data that was added can be viewed in the PeopleSoft Component as shown in the following example.</span></span>  
  
     ![](../core/media/psadapter-59-ps-testcompinterface6.gif "PSAdapter_59_PS_TestCompInterface6")  
  
     <span data-ttu-id="1e842-141">**発効日**既定値の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="1e842-141">**Effective Date** is one of the default values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e842-142">参照</span><span class="sxs-lookup"><span data-stu-id="1e842-142">See Also</span></span>  
 <span data-ttu-id="1e842-143">[付録 a: コンポーネント インターフェイス メソッド](../core/appendix-a-component-interface-methods.md) </span><span class="sxs-lookup"><span data-stu-id="1e842-143">[Appendix A: Component Interface Methods](../core/appendix-a-component-interface-methods.md) </span></span>  
 [<span data-ttu-id="1e842-144">付録 c: コンポーネント インターフェイスの使用</span><span class="sxs-lookup"><span data-stu-id="1e842-144">Appendix C: Using Component Interfaces</span></span>](../core/appendix-c-using-component-interfaces.md)