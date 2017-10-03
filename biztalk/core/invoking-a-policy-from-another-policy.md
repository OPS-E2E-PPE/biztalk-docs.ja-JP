---
title: "ポリシー別のポリシーからを呼び出す |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b5bf658a-02a1-426a-abe5-8c9de673cf0d
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b03204b9de4b763f516b7fb22ada1f4f3f6173a2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="invoking-a-policy-from-another-policy"></a><span data-ttu-id="439e7-102">別のポリシーからのポリシーの呼び出し</span><span class="sxs-lookup"><span data-stu-id="439e7-102">Invoking a Policy from Another Policy</span></span>
<span data-ttu-id="439e7-103">次のいずれかのメソッドを使用すると、ポリシー (子) を別のポリシー (親) から呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="439e7-103">You can invoke a policy (child) from another policy (parent) by using one of the following methods:</span></span>  
  
-   <span data-ttu-id="439e7-104">呼び出す、 **Policy.Execute**親ポリシーから直接メソッド</span><span class="sxs-lookup"><span data-stu-id="439e7-104">Calling the **Policy.Execute** method directly from the parent policy</span></span>  
  
-   <span data-ttu-id="439e7-105">ラップするヘルパー .NET コンポーネントのメソッドを呼び出す、 **Policy.Execute**親ポリシーからメソッド</span><span class="sxs-lookup"><span data-stu-id="439e7-105">Calling a method of a helper .NET component that wraps the **Policy.Execute** method from the parent policy</span></span>  
  
 <span data-ttu-id="439e7-106">2 番目のメソッドを使用する利点は、する処理前および処理後のコードを追加することができます、 **Policy.Execute**メソッドです。</span><span class="sxs-lookup"><span data-stu-id="439e7-106">The advantage of using the second method is that you can add pre-processing and post-processing code to the **Policy.Execute** method.</span></span> <span data-ttu-id="439e7-107">たとえば、子ポリシーで必要とされる任意のファクトを、このラッパー メソッドに作成できます。</span><span class="sxs-lookup"><span data-stu-id="439e7-107">For example, you can create any facts required from the child policy in this wrapper method.</span></span> <span data-ttu-id="439e7-108">以下のセクションでは、それぞれのメソッドの例を示します。</span><span class="sxs-lookup"><span data-stu-id="439e7-108">The following sections provide an example for each method.</span></span>  
  
## <a name="invoking-the-policyexecute-method-directly-from-the-parent-policy"></a><span data-ttu-id="439e7-109">親ポリシーからの Policy.Execute メソッドの直接呼び出し</span><span class="sxs-lookup"><span data-stu-id="439e7-109">Invoking the Policy.Execute Method Directly from the Parent Policy</span></span>  
 <span data-ttu-id="439e7-110">ここでは、大まかな手順を使用して、親ポリシーから子ポリシーを呼び出す、 **Policy.Execute**メソッドを直接です。</span><span class="sxs-lookup"><span data-stu-id="439e7-110">This section presents the high-level steps to invoke the child policy from the parent policy by using the **Policy.Execute** method directly.</span></span>  
  
### <a name="adding-the-policyexecute-action-to-the-parent-policy"></a><span data-ttu-id="439e7-111">親ポリシーへの Policy.Execute アクションの追加</span><span class="sxs-lookup"><span data-stu-id="439e7-111">Adding the Policy.Execute Action to the Parent Policy</span></span>  
 <span data-ttu-id="439e7-112">次の手順を追加する手順では、 **Policy.Execute**として XML ドキュメントをファクトとして子ポリシーに渡します親ポリシーにアクション メソッド。</span><span class="sxs-lookup"><span data-stu-id="439e7-112">The following procedure has steps to add the **Policy.Execute** method as an action to the parent policy that passes an XML document as a fact to the child policy.</span></span>  
  
##### <a name="to-add-the-policyexecute-method-as-an-action-to-a-policy"></a><span data-ttu-id="439e7-113">Policy.Execute メソッドをアクションとして親ポリシーに追加するには</span><span class="sxs-lookup"><span data-stu-id="439e7-113">To add the Policy.Execute method as an action to a policy</span></span>  
  
1.  <span data-ttu-id="439e7-114">[ファクト エクスプ ローラー] ウィンドウ、 **.NET クラス**タブです。</span><span class="sxs-lookup"><span data-stu-id="439e7-114">In the Facts Explorer window, click the **.NET Classes** tab.</span></span>  
  
2.  <span data-ttu-id="439e7-115">右クリック**.NET アセンブリ**、クリックして**参照**です。</span><span class="sxs-lookup"><span data-stu-id="439e7-115">Right-click **.NET Assemblies**, and then click **Browse**.</span></span>  
  
3.  <span data-ttu-id="439e7-116">選択**Microsoft.RuleEngine**から、 **.NET アセンブリ**一覧をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="439e7-116">Select **Microsoft.RuleEngine** from the **.NET Assemblies** list, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="439e7-117">展開**ポリシー**です。</span><span class="sxs-lookup"><span data-stu-id="439e7-117">Expand **Policy**.</span></span>  
  
5.  <span data-ttu-id="439e7-118">ドラッグ**Execute (Object facts)**または**Execute (Object facts, IRuleSetTrackingInterceptor trackingInterceptor)** [THEN] ペインにします。</span><span class="sxs-lookup"><span data-stu-id="439e7-118">Drag **Execute(Object facts)** or **Execute(Object facts, IRuleSetTrackingInterceptor trackingInterceptor)** to the THEN pane.</span></span>  
  
6.  <span data-ttu-id="439e7-119">クリックして、 **XML スキーマ**ノード。</span><span class="sxs-lookup"><span data-stu-id="439e7-119">Click the **XML Schemas** node.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="439e7-120">このサンプル シナリオでは、ファクトとして親ポリシーに送信される XML ドキュメントが、ファクトとして子ポリシーに渡されます。</span><span class="sxs-lookup"><span data-stu-id="439e7-120">In this sample scenario, an XML document that is submitted as a fact to the parent policy is passed as a fact to the child policy.</span></span> <span data-ttu-id="439e7-121">代わりに、子ポリシー用のファクトを作成する .NET メソッドを呼び出すこともできます。</span><span class="sxs-lookup"><span data-stu-id="439e7-121">Instead, you can invoke a .NET method that creates the facts for the child policy.</span></span>  
  
7.  <span data-ttu-id="439e7-122">右クリック**スキーマ**、クリックして**参照**です。</span><span class="sxs-lookup"><span data-stu-id="439e7-122">Right-click **Schemas**, and then click **Browse**.</span></span>  
  
8.  <span data-ttu-id="439e7-123">スキーマをファクトとして渡すし、をクリックする、XML ドキュメントを選択**開く**です。</span><span class="sxs-lookup"><span data-stu-id="439e7-123">Select the schema for the XML document you want to pass as a fact, and then click **Open**.</span></span>  
  
9. <span data-ttu-id="439e7-124">ドラッグ*\<スキーマ名 >*の最初の引数は、.xsd、 **Policy.Execute**子ポリシーにファクトとして親ポリシーに渡される XML ドキュメントを渡す方法です。</span><span class="sxs-lookup"><span data-stu-id="439e7-124">Drag *\<Schema name>*.xsd to the first argument of the **Policy.Execute** method to pass the XML document that is passed to the parent policy as a fact to the child policy.</span></span>  
  
10. <span data-ttu-id="439e7-125">使用する場合、 **Execute**を受け取らないメソッド、 **IRuleSetTrackingInterceptor** 2 番目の引数として、次の手順をスキップします。</span><span class="sxs-lookup"><span data-stu-id="439e7-125">If you use the **Execute** method that does not take the **IRuleSetTrackingInterceptor** as the second argument, skip the following steps.</span></span>  
  
11. <span data-ttu-id="439e7-126">クリックして、 **.NET クラス**タブです。</span><span class="sxs-lookup"><span data-stu-id="439e7-126">Click the **.NET Classes** tab.</span></span>  
  
12. <span data-ttu-id="439e7-127">ドラッグ**DebugTrackingInterceptor**で**Microsoft.RuleEngine**の 2 番目の引数、 **Policy.Execute**メソッドです。</span><span class="sxs-lookup"><span data-stu-id="439e7-127">Drag **DebugTrackingInterceptor** in **Microsoft.RuleEngine** to the second argument of the **Policy.Execute** method.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="439e7-128">この操作を実行する場合、クライアントがのインスタンスを渡す必要があります、 **DebugTrackingInterceptor**クラスをインスタンスをファクトとして子ポリシーに渡します親ポリシーにファクトとして。</span><span class="sxs-lookup"><span data-stu-id="439e7-128">If you perform this action, the client must pass an instance of the **DebugTrackingInterceptor** class as a fact to the parent policy, which in turn passes the instance as a fact to the child policy.</span></span> <span data-ttu-id="439e7-129">コンス トラクターをドラッグする代わりに、 **DebugTrackingInterceptor**クラスのインスタンスが自動的に作成するようにします。</span><span class="sxs-lookup"><span data-stu-id="439e7-129">Instead you could drag the constructor of the **DebugTrackingInterceptor** class so that the instance is automatically created for you.</span></span>  
  
### <a name="modifying-the-client-application-that-invokes-the-parent-policy"></a><span data-ttu-id="439e7-130">親ポリシーを呼び出すクライアント アプリケーションの変更</span><span class="sxs-lookup"><span data-stu-id="439e7-130">Modifying the Client Application that Invokes the Parent Policy</span></span>  
 <span data-ttu-id="439e7-131">親ポリシーを呼び出すクライアントのインスタンスを作成、**ポリシー**をパラメーターとして子ポリシー名を持つクラスをファクトとして他のファクトと共に親ポリシーに渡します。</span><span class="sxs-lookup"><span data-stu-id="439e7-131">The client that invokes the parent policy creates an instance of the **Policy** class with the child policy name as a parameter and passes it as a fact to the parent policy along with other facts.</span></span> <span data-ttu-id="439e7-132">このアクションを説明するサンプル コードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="439e7-132">The following sample code illustrates this action:</span></span>  
  
```  
DebugTrackingInterceptor dti = new DebugTrackingInterceptor("PolicyTracking.txt");  
Policy policy = new Policy("ParentPolicy");  
object[] facts = new object[3];  
facts[0] = txd;  
facts[1] = new Policy("ChildPolicy");  
facts[2] = new DebugTrackingInterceptor("PolicyTracking2.txt");  
policy.Execute(facts, dti);  
policy.Dispose();  
```  
  
 <span data-ttu-id="439e7-133">内のファクトを作成するコードを配置する必要がある場合は、BizTalk オーケストレーションは、クライアントは、**式**図形、およびパラメーターとして、ファクトを渡して、**ルールの呼び出し**図形です。</span><span class="sxs-lookup"><span data-stu-id="439e7-133">If the client is a BizTalk orchestration, you may need to place the code to create facts in an **Expression** shape, and then pass the facts as parameters to the **Call Rules** shape.</span></span>  
  
## <a name="invoking-a-net-wrapper-method-from-the-parent-policy"></a><span data-ttu-id="439e7-134">親ポリシーからの .NET ラッパー メソッドの呼び出し</span><span class="sxs-lookup"><span data-stu-id="439e7-134">Invoking a .NET Wrapper Method from the Parent Policy</span></span>  
 <span data-ttu-id="439e7-135">ここへの呼び出しをラップする .NET メソッドを呼び出すための大まかな手順、 **Policy.Execute**親ポリシーからのメソッドです。</span><span class="sxs-lookup"><span data-stu-id="439e7-135">This section presents the high-level steps to invoke a .NET method that wraps the call to the **Policy.Execute** method from the parent policy.</span></span>  
  
### <a name="creating-the-utility-net-class"></a><span data-ttu-id="439e7-136">ユーティリティ .NET クラスの作成</span><span class="sxs-lookup"><span data-stu-id="439e7-136">Creating the Utility .NET Class</span></span>  
  
##### <a name="to-create-the-utility-class"></a><span data-ttu-id="439e7-137">ユーティリティ クラスを作成するには</span><span class="sxs-lookup"><span data-stu-id="439e7-137">To create the utility class</span></span>  
  
1.  <span data-ttu-id="439e7-138">.NET クラス ライブラリ プロジェクトを作成し、このプロジェクトにクラスを追加します。</span><span class="sxs-lookup"><span data-stu-id="439e7-138">Create a .NET class library project, and then add a class to the project.</span></span>  
  
2.  <span data-ttu-id="439e7-139">呼び出す静的メソッドを追加、 **Policy.Execute**に次のサンプル コードに示すように、名前を持つが、パラメーターとして渡されたポリシーを呼び出すメソッド。</span><span class="sxs-lookup"><span data-stu-id="439e7-139">Add a static method that calls the **Policy.Execute** method to invoke the policy whose name is passed as a parameter, as shown in the following sample code:</span></span>  
  
    ```  
    public static void Execute(string policyName, TypedXmlDocument txd)  
    {  
        DebugTrackingInterceptor dti = new   DebugTrackingInterceptor("PolicyTracking.txt");  
        Policy policy = new Policy("ParentPolicy");  
        object[] facts = new object[3];  
        facts[0] = txd;  
        facts[1] = new Policy("ChildPolicy");  
        facts[2] = new DebugTrackingInterceptor("PolicyTracking2.txt");  
        policy.Execute(facts, dti);  
        policy.Dispose();  
    }   
    ```  
  
3.  <span data-ttu-id="439e7-140">確認して、 **StaticSupport**レジストリ キーが 1 または 2 に設定します。</span><span class="sxs-lookup"><span data-stu-id="439e7-140">Make sure that the **StaticSupport** registry key is set to 1 or 2.</span></span> <span data-ttu-id="439e7-141">レジストリ キーの詳細については、次を参照してください。[クラスの静的メンバーの呼び出し](../core/invoking-static-members-of-a-class.md)です。</span><span class="sxs-lookup"><span data-stu-id="439e7-141">For more information about the registry key, see [Invoking Static Members of a Class](../core/invoking-static-members-of-a-class.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="439e7-142">静的メソッドの代わりにインスタンス メソッドを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="439e7-142">You can use an instance method instead of a static method.</span></span> <span data-ttu-id="439e7-143">インスタンス メソッドを使用する場合、クライアントは、ヘルパー .NET クラスのインスタンスをファクトとして親ポリシーに渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="439e7-143">Remember that, if you use an instance method, the client must pass an instance of the helper .NET class as a fact to the parent policy.</span></span>  
  
### <a name="modifying-the-client-application"></a><span data-ttu-id="439e7-144">クライアント アプリケーションの変更</span><span class="sxs-lookup"><span data-stu-id="439e7-144">Modifying the Client Application</span></span>  
 <span data-ttu-id="439e7-145">クライアントが親ポリシーを呼び出し、親ポリシーが、子ポリシーを呼び出すヘルパー メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="439e7-145">The client invokes the parent policy, and the parent policy invokes the helper method that invokes the child policy.</span></span> <span data-ttu-id="439e7-146">クライアントのサンプル コードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="439e7-146">The sample code for the client is as follows:</span></span>  
  
```  
facts[0] = txd;  
facts[1] = new PolicyExecutor(txd);  
//call the first or parent policy  
Policy policy = new Policy(policyName);  
DebugTrackingInterceptor dti = new DebugTrackingInterceptor("PolicyTracking.txt");  
policy.Execute(facts, dti);  
policy.Dispose();  
```  
  
> [!NOTE]
>  <span data-ttu-id="439e7-147">メソッドがインスタンス メソッドの場合、クライアントは、ヘルパー .NET クラスのインスタンスを作成し、ファクトとして親ポリシーに渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="439e7-147">If the method is an instance method, the client must create an instance of the helper .NET class, and pass it as a fact to the parent policy.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="439e7-148">内のファクトを作成するコードを配置する必要がある場合は、BizTalk オーケストレーションは、クライアントは、**式**図形、およびパラメーターとして、ファクトを渡して、**ルールの呼び出し**図形です。</span><span class="sxs-lookup"><span data-stu-id="439e7-148">If the client is a BizTalk orchestration, you may need to place the code to create facts in an **Expression** shape, and then pass the facts as parameters to the **Call Rules** shape.</span></span>