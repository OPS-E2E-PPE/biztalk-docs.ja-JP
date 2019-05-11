---
title: コンポーネント インターフェイスをテストする方法 |Microsoft Docs
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
ms.openlocfilehash: d8450177cd97d7136d8ee4146ff93fceee20b351
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333853"
---
# <a name="how-to-test-component-interfaces"></a><span data-ttu-id="cafd1-102">コンポーネント インターフェイスをテストする方法</span><span class="sxs-lookup"><span data-stu-id="cafd1-102">How to Test Component Interfaces</span></span>
<span data-ttu-id="cafd1-103">Microsoft BizTalk Adapter for PeopleSoft Enterprise は PeopleSoft メタデータとコンポーネントのインターフェイスです。そのため、新しいまたは変更されたコンポーネントのインターフェイスに対応できます。</span><span class="sxs-lookup"><span data-stu-id="cafd1-103">Microsoft BizTalk Adapter for PeopleSoft Enterprise uses PeopleSoft metadata and component interfaces; therefore, it can handle new or modified component interfaces.</span></span> <span data-ttu-id="cafd1-104">アダプターによりの前提条件コンポーネント インターフェイスについてが、論理的かつ有効です。</span><span class="sxs-lookup"><span data-stu-id="cafd1-104">The adapter makes no assumptions about component interfaces except that they are logical and valid.</span></span> <span data-ttu-id="cafd1-105">そのため、アダプターのソースとして使用される前に、各コンポーネントのインターフェイスをテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cafd1-105">Therefore, each component interface must be tested before it is used as a source for the adapter.</span></span>  
  
 <span data-ttu-id="cafd1-106">ユーザーまたは PeopleSoft のアップグレードによって、基になるアプリケーションに変更が行われた変更が、コンポーネント インターフェイスを無効になる場合は、ユーザーは、アダプタが使用前に、無効なコンポーネント インターフェイスを修復する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cafd1-106">If changes are made to the underlying application by the user or by a PeopleSoft upgrade, and the changes invalidate a component interface, the user must repair the invalid component interface before the adapter uses it.</span></span>  
  
### <a name="to-test-a-component-interface"></a><span data-ttu-id="cafd1-107">コンポーネント インターフェイスをテストするには</span><span class="sxs-lookup"><span data-stu-id="cafd1-107">To test a component interface</span></span>  
  
1.  <span data-ttu-id="cafd1-108">アプリケーション デザイナーでの**ツール** メニューのをクリックして**Test Component Interface**します。</span><span class="sxs-lookup"><span data-stu-id="cafd1-108">In Application Designer, on the **Tools** menu, click **Test Component Interface**.</span></span>  
  
     <span data-ttu-id="cafd1-109">![](../core/media/psadapter-54-ps-testcompinterface1.gif "PSAdapter_54_PS_TestCompInterface1")</span><span class="sxs-lookup"><span data-stu-id="cafd1-109">![](../core/media/psadapter-54-ps-testcompinterface1.gif "PSAdapter_54_PS_TestCompInterface1")</span></span>  
  
2.  <span data-ttu-id="cafd1-110">**Component Interface Tester**  ダイアログ ボックスで、次のメソッドを 1 つを使用してコンポーネント インターフェイスをテストします。</span><span class="sxs-lookup"><span data-stu-id="cafd1-110">In the **Component Interface Tester** dialog box, test the component interface by using one the following methods.</span></span> <span data-ttu-id="cafd1-111">変更が完了したら、ウィンドウの最上位の項目を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="cafd1-111">After you finish making changes, right-click the top item in the pane.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cafd1-112">必要な場合は、フォア グラウンドに表示させる ダイアログ ボックスをクリックします。</span><span class="sxs-lookup"><span data-stu-id="cafd1-112">If required, click the dialog box to bring it to the foreground.</span></span>  
  
    -   <span data-ttu-id="cafd1-113">Find メソッドを使用してコンポーネント インターフェイスをテストするには、クリックして**検索**します。</span><span class="sxs-lookup"><span data-stu-id="cafd1-113">To test the component interface using the Find method, click **Find**.</span></span>  
  
         <span data-ttu-id="cafd1-114">**Component Interface Tester - 検索結果** ダイアログ ボックスが開き、基になるコンポーネントのすべての可能なエントリを表示します。</span><span class="sxs-lookup"><span data-stu-id="cafd1-114">The **Component Interface Tester - Find Results** dialog box opens, displaying all the possible entries for the underlying component.</span></span> <span data-ttu-id="cafd1-115">300 以上のエントリがある場合は、メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cafd1-115">If there are more than 300 entries, a message appears.</span></span>  
  
         <span data-ttu-id="cafd1-116">A.</span><span class="sxs-lookup"><span data-stu-id="cafd1-116">a.</span></span> <span data-ttu-id="cafd1-117">左側のウィンドウで、**検索結果** ダイアログ ボックスで、フィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="cafd1-117">In the left pane of the **Find Results** dialog box, select a field.</span></span>  
  
         <span data-ttu-id="cafd1-118">B.</span><span class="sxs-lookup"><span data-stu-id="cafd1-118">b.</span></span> <span data-ttu-id="cafd1-119">その特定のフィールドに関連するデータを表示する をクリックして**Get Selected**します。</span><span class="sxs-lookup"><span data-stu-id="cafd1-119">To display the relevant data for that particular field, click **Get Selected**.</span></span>  
  
         <span data-ttu-id="cafd1-120">次の画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cafd1-120">The following screen appears.</span></span>  
  
         <span data-ttu-id="cafd1-121">![](../core/media/psadapter-55-ps-testcompinterface2.gif "PSAdapter_55_PS_TestCompInterface2")</span><span class="sxs-lookup"><span data-stu-id="cafd1-121">![](../core/media/psadapter-55-ps-testcompinterface2.gif "PSAdapter_55_PS_TestCompInterface2")</span></span>  
  
         <span data-ttu-id="cafd1-122">セキュリティ設定で許可される場合は、個々 のフィールドの値を変更できます。</span><span class="sxs-lookup"><span data-stu-id="cafd1-122">If the security settings allow, you can change the values in the individual fields.</span></span>  
  
         <span data-ttu-id="cafd1-123">次のダイアログ ボックスが開きます。</span><span class="sxs-lookup"><span data-stu-id="cafd1-123">The following dialog box opens.</span></span>  
  
         <span data-ttu-id="cafd1-124">![](../core/media/psadapter-56-ps-testcompinterface3.gif "PSAdapter_56_PS_TestCompInterface3")</span><span class="sxs-lookup"><span data-stu-id="cafd1-124">![](../core/media/psadapter-56-ps-testcompinterface3.gif "PSAdapter_56_PS_TestCompInterface3")</span></span>  
  
    -   <span data-ttu-id="cafd1-125">使用してコンポーネント インターフェイスをテストする、`Get`メソッド。</span><span class="sxs-lookup"><span data-stu-id="cafd1-125">To test the component interface using the `Get` method:</span></span>  
  
         <span data-ttu-id="cafd1-126">A.</span><span class="sxs-lookup"><span data-stu-id="cafd1-126">a.</span></span> <span data-ttu-id="cafd1-127">既存のキーを入力します。</span><span class="sxs-lookup"><span data-stu-id="cafd1-127">Enter the existing key(s).</span></span>  
  
         <span data-ttu-id="cafd1-128">B.</span><span class="sxs-lookup"><span data-stu-id="cafd1-128">b.</span></span> <span data-ttu-id="cafd1-129">クリックして**既存**します。</span><span class="sxs-lookup"><span data-stu-id="cafd1-129">Click **Get Existing**.</span></span>  
  
         <span data-ttu-id="cafd1-130">これは、入力したキーの公開されているプロパティを返します。</span><span class="sxs-lookup"><span data-stu-id="cafd1-130">This returns the exposed properties for the key that you entered.</span></span>  
  
         <span data-ttu-id="cafd1-131">値を変更するには、場合**更新アクセス**が指定されました。</span><span class="sxs-lookup"><span data-stu-id="cafd1-131">You can change values if **Update access** was specified.</span></span>  
  
         <span data-ttu-id="cafd1-132">使用してをテストする代わりに、`Create`メソッド。</span><span class="sxs-lookup"><span data-stu-id="cafd1-132">Alternatively, you can test using the `Create` method.</span></span>  
  
         <span data-ttu-id="cafd1-133">![](../core/media/psadapter-57-ps-testcompinterface4.gif "PSAdapter_57_PS_TestCompInterface4")</span><span class="sxs-lookup"><span data-stu-id="cafd1-133">![](../core/media/psadapter-57-ps-testcompinterface4.gif "PSAdapter_57_PS_TestCompInterface4")</span></span>  
  
    -   <span data-ttu-id="cafd1-134">使用してコンポーネント インターフェイスをテストする、`Create`メソッド。</span><span class="sxs-lookup"><span data-stu-id="cafd1-134">To test the component interface using the `Create` method:</span></span>  
  
         <span data-ttu-id="cafd1-135">A.</span><span class="sxs-lookup"><span data-stu-id="cafd1-135">a.</span></span> <span data-ttu-id="cafd1-136">必要なすべてのキー値を入力します。</span><span class="sxs-lookup"><span data-stu-id="cafd1-136">Enter all required key values.</span></span>  
  
         <span data-ttu-id="cafd1-137">B.</span><span class="sxs-lookup"><span data-stu-id="cafd1-137">b.</span></span> <span data-ttu-id="cafd1-138">クリックして**新規作成**です。</span><span class="sxs-lookup"><span data-stu-id="cafd1-138">Click **Create New**.</span></span>  
  
         <span data-ttu-id="cafd1-139">有効な値を入力すると**キーを作成する**テーブル名には、配置の既定のデータが展開されてから、JOBCODE データを表示するウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="cafd1-139">When you enter valid values in **Create keys**, a pane that displays the JOBCODE data opens after the Table name is expanded with default data in place.</span></span>  
  
         <span data-ttu-id="cafd1-140">これでフィールドを変更できます。</span><span class="sxs-lookup"><span data-stu-id="cafd1-140">You can change fields now.</span></span>  
  
         <span data-ttu-id="cafd1-141">![](../core/media/psadapter-58-ps-testcompinterface5.gif "PSAdapter_58_PS_TestCompInterface5")</span><span class="sxs-lookup"><span data-stu-id="cafd1-141">![](../core/media/psadapter-58-ps-testcompinterface5.gif "PSAdapter_58_PS_TestCompInterface5")</span></span>  
  
         <span data-ttu-id="cafd1-142">変更は、コンポーネントの基になるビジネス ロジックに対して検証されます。</span><span class="sxs-lookup"><span data-stu-id="cafd1-142">Changes are validated against the component's underlying business logic.</span></span>  
  
3.  <span data-ttu-id="cafd1-143">をクリックして変更を保存、**保存**アイコン。</span><span class="sxs-lookup"><span data-stu-id="cafd1-143">To save your changes, click the **Save** icon.</span></span>  
  
     <span data-ttu-id="cafd1-144">レコードの作成に使用されるキーは、データを表示するための Get メソッドで使用できます。</span><span class="sxs-lookup"><span data-stu-id="cafd1-144">The keys used to create the record can be used with the Get method for viewing data.</span></span> <span data-ttu-id="cafd1-145">追加されたデータは、次の例に示すように、PeopleSoft コンポーネントで表示できます。</span><span class="sxs-lookup"><span data-stu-id="cafd1-145">The data that was added can be viewed in the PeopleSoft Component as shown in the following example.</span></span>  
  
     <span data-ttu-id="cafd1-146">![](../core/media/psadapter-59-ps-testcompinterface6.gif "PSAdapter_59_PS_TestCompInterface6")</span><span class="sxs-lookup"><span data-stu-id="cafd1-146">![](../core/media/psadapter-59-ps-testcompinterface6.gif "PSAdapter_59_PS_TestCompInterface6")</span></span>  
  
     <span data-ttu-id="cafd1-147">**有効日**は既定値の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="cafd1-147">**Effective Date** is one of the default values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cafd1-148">参照</span><span class="sxs-lookup"><span data-stu-id="cafd1-148">See Also</span></span>  
 <span data-ttu-id="cafd1-149">[付録 a:コンポーネント インターフェイス メソッド](../core/appendix-a-component-interface-methods.md) </span><span class="sxs-lookup"><span data-stu-id="cafd1-149">[Appendix A: Component Interface Methods](../core/appendix-a-component-interface-methods.md) </span></span>  
 [<span data-ttu-id="cafd1-150">付録 c:コンポーネント インターフェイスの使用</span><span class="sxs-lookup"><span data-stu-id="cafd1-150">Appendix C: Using Component Interfaces</span></span>](../core/appendix-c-using-component-interfaces.md)