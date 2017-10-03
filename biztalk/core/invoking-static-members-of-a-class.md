---
title: "クラスの静的メンバーを呼び出す |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3a51171c-8de0-45dd-8659-f674cf27acbe
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2128bf6cb71c773cd31be497765e39b0d7815b4a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="invoking-static-members-of-a-class"></a><span data-ttu-id="c1113-102">クラスの静的メンバーの呼び出し</span><span class="sxs-lookup"><span data-stu-id="c1113-102">Invoking Static Members of a Class</span></span>
<span data-ttu-id="c1113-103">既定では、ルール エンジンは、.NET クラスのインスタンスをアサートして、.NET クラスの静的メンバーを呼び出すポリシーを実行するよう要求します。</span><span class="sxs-lookup"><span data-stu-id="c1113-103">By default, the rule engine requires you to assert an instance of a .NET class to execute a policy that invokes a static member of the .NET class.</span></span> <span data-ttu-id="c1113-104">値を変更することでこの動作を変更することができます、 **StaticSupport**下のレジストリ キー **HKEY_LOCAL_MACHINE\Software\Microsoft\BusinessRules\3.0**次の表に、値のいずれかにします。</span><span class="sxs-lookup"><span data-stu-id="c1113-104">You can modify this behavior by changing the value of the **StaticSupport** registry key under **HKEY_LOCAL_MACHINE\Software\Microsoft\BusinessRules\3.0** to one of the values in the following table.</span></span>  
  
|<span data-ttu-id="c1113-105">StaticSupport のレジストリ値</span><span class="sxs-lookup"><span data-stu-id="c1113-105">StaticSupport registry value</span></span>|<span data-ttu-id="c1113-106">ルール エンジンの動作</span><span class="sxs-lookup"><span data-stu-id="c1113-106">Rule engine behavior</span></span>|  
|----------------------------------|--------------------------|  
|<span data-ttu-id="c1113-107">0</span><span class="sxs-lookup"><span data-stu-id="c1113-107">0</span></span>|<span data-ttu-id="c1113-108">既定値です。</span><span class="sxs-lookup"><span data-stu-id="c1113-108">Default value.</span></span> <span data-ttu-id="c1113-109">ルール エンジンは、BizTalk Server 2004 のモデルに従って、.NET クラスのインスタンスがアサートされる場合にのみ、静的メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="c1113-109">The rule engine follows the BizTalk Server 2004 model, where the static method is called only when an instance of the .NET class is asserted.</span></span>|  
|<span data-ttu-id="c1113-110">1</span><span class="sxs-lookup"><span data-stu-id="c1113-110">1</span></span>|<span data-ttu-id="c1113-111">オブジェクト インスタンスは必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="c1113-111">An object instance is not required.</span></span> <span data-ttu-id="c1113-112">静的メソッドは、ルールが評価または実行されるときに呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c1113-112">The static method is called when the rule is evaluated or executed.</span></span>|  
|<span data-ttu-id="c1113-113">2</span><span class="sxs-lookup"><span data-stu-id="c1113-113">2</span></span>|<span data-ttu-id="c1113-114">オブジェクト インスタンスは必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="c1113-114">An object instance is not required.</span></span> <span data-ttu-id="c1113-115">すべてのパラメーターが定数である場合、静的メソッドは、ポリシーの変換時に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c1113-115">The static method is called at the policy translation time if all parameters are constant.</span></span> <span data-ttu-id="c1113-116">これは最適なパフォーマンスを提供します。なぜなら、条件内の複数のルールで静的メソッドが使用される場合でも、静的メソッドが呼び出されるのは 1 回だけだからです。</span><span class="sxs-lookup"><span data-stu-id="c1113-116">This is a performance optimization because the static method is called only once even though it is used in multiple rules in conditions.</span></span> <span data-ttu-id="c1113-117">アクションとして使用される静的メソッドは変換時に実行されません。代わりに、パラメーターとして使用される静的メソッドが実行される場合があります。</span><span class="sxs-lookup"><span data-stu-id="c1113-117">Note that static methods used as actions will not be executed at the translation time, but static methods used as parameters may be executed.</span></span>|  
  
## <a name="adding-and-changing-the-staticsupport-registry-key"></a><span data-ttu-id="c1113-118">StaticSupport レジストリ キーの追加と変更</span><span class="sxs-lookup"><span data-stu-id="c1113-118">Adding and Changing the StaticSupport Registry Key</span></span>  
 <span data-ttu-id="c1113-119">表示されない場合、 **StaticSupport**下のレジストリ キー **HKEY_LOCAL_MACHINE\Software\Microsoft\BusinessRules\3.0**、次の手順を実行することによって追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c1113-119">If you do not see the **StaticSupport** registry key under **HKEY_LOCAL_MACHINE\Software\Microsoft\BusinessRules\3.0**, you should add it by performing the following steps.</span></span>  
  
 <span data-ttu-id="c1113-120">**StaticSupport レジストリ キーを追加するには**</span><span class="sxs-lookup"><span data-stu-id="c1113-120">**To add the StaticSupport registry key**</span></span>  
  
1.  <span data-ttu-id="c1113-121">をクリックして**開始**、 をクリックして**実行**、型**RegEdit**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="c1113-121">Click **Start**, click **Run**, type **RegEdit**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="c1113-122">展開**HKEY_LOCAL_MACHINE**、展開**ソフトウェア**、展開**Microsoft**を展開**BusinessRules**、し、 **3.0**です。</span><span class="sxs-lookup"><span data-stu-id="c1113-122">Expand **HKEY_LOCAL_MACHINE**, expand **Software**, expand **Microsoft**, expand **BusinessRules**, and then select **3.0**.</span></span>  
  
3.  <span data-ttu-id="c1113-123">右側のペインで右クリックし、**新規**、クリックして**DWORD 値**です。</span><span class="sxs-lookup"><span data-stu-id="c1113-123">In the right pane, right-click, point to **New**, and then click **DWORD value**.</span></span>  
  
4.  <span data-ttu-id="c1113-124">**名前**、型**StaticSupport**です。</span><span class="sxs-lookup"><span data-stu-id="c1113-124">For **Name**, type **StaticSupport**.</span></span>  
  
 <span data-ttu-id="c1113-125">場合、 **StaticSupport**レジストリ キーが既に存在し、その値を変更するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c1113-125">If the **StaticSupport** registry key already exists, and you need to change its value, perform the following steps.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c1113-126">BizTalk が 64 ビット コンピューターにインストールされているかどうかは、追加することができます**StaticSupport**を使用して、次のオプションのいずれかのレジストリ キー。</span><span class="sxs-lookup"><span data-stu-id="c1113-126">If BizTalk is installed on a 64-bit machine, then you can add **StaticSupport** registry key using either of the following options:</span></span>  
>   
>  -   <span data-ttu-id="c1113-127">HKLM\Software\Wow6432Node\Microsoft\BusinessRules\3.0 の下を見る必要があります。</span><span class="sxs-lookup"><span data-stu-id="c1113-127">You need to look under HKLM\Software\Wow6432Node\Microsoft\BusinessRules\3.0.</span></span> <span data-ttu-id="c1113-128">このキーが存在するかどうかは、追加することができます**StaticSupport**ここです。</span><span class="sxs-lookup"><span data-stu-id="c1113-128">If this key exists, then you can add **StaticSupport** here.</span></span>  
> -   <span data-ttu-id="c1113-129">別のオプションは**StaticSupport**で、 **BTNTsvc [64].exe.config**ファイル、ここで設定がレジストリには何を上書きします。</span><span class="sxs-lookup"><span data-stu-id="c1113-129">Another option is to put **StaticSupport** in the **BTNTsvc[64].exe.config** file, as any settings here override what's in the Registry.</span></span>  <span data-ttu-id="c1113-130">また、レジストリ設定の変更はオペレーティング システム全体に適用されるのに対し、このオプションでは既定の動作の変更が BizTalk に限定されるので、このオプションの方が好ましいとも考えられます。</span><span class="sxs-lookup"><span data-stu-id="c1113-130">Further, one can also make the argument that this option is preferred since it isolates the change in default behavior to BizTalk only, whereas Registry settings are global to the Operating System.</span></span>  
  
 <span data-ttu-id="c1113-131">**StaticSupport レジストリ キーの値を変更するには**</span><span class="sxs-lookup"><span data-stu-id="c1113-131">**To change the value of the StaticSupport registry key**</span></span>  
  
1.  <span data-ttu-id="c1113-132">をクリックして**開始**、 をクリックして**実行**、型**RegEdit**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="c1113-132">Click **Start**, click **Run**, type **RegEdit**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="c1113-133">展開**HKEY_LOCAL_MACHINE**、展開**ソフトウェア**、展開**Microsoft**、展開**BusinessRules**の順に展開および**3.0**です。</span><span class="sxs-lookup"><span data-stu-id="c1113-133">Expand **HKEY_LOCAL_MACHINE**, expand **Software**, expand **Microsoft**, expand **BusinessRules**, and then expand **3.0**.</span></span>  
  
3.  <span data-ttu-id="c1113-134">ダブルクリックして、 **StaticSupport**レジストリ キー、または右クリックし、をクリックして**変更**です。</span><span class="sxs-lookup"><span data-stu-id="c1113-134">Double-click the **StaticSupport** registry key, or right-click it and then click **Modify**.</span></span>