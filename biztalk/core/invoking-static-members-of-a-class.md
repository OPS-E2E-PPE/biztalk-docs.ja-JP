---
title: クラスの静的メンバーの呼び出し |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3a51171c-8de0-45dd-8659-f674cf27acbe
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 419b83518a9a5cbda54326cf757458afbcdd369b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329830"
---
# <a name="invoking-static-members-of-a-class"></a><span data-ttu-id="9ca4f-102">クラスの静的メンバーの呼び出し</span><span class="sxs-lookup"><span data-stu-id="9ca4f-102">Invoking Static Members of a Class</span></span>
<span data-ttu-id="9ca4f-103">既定では、ルール エンジンは、.NET クラスの静的メンバーを呼び出すポリシーを実行する .NET クラスのインスタンスをアサートすることが必要です。</span><span class="sxs-lookup"><span data-stu-id="9ca4f-103">By default, the rule engine requires you to assert an instance of a .NET class to execute a policy that invokes a static member of the .NET class.</span></span> <span data-ttu-id="9ca4f-104">値を変更することでこの動作を変更することができます、 **StaticSupport**下のレジストリ キー **HKEY_LOCAL_MACHINE\Software\Microsoft\BusinessRules\3.0**次の表の値の 1 つ。</span><span class="sxs-lookup"><span data-stu-id="9ca4f-104">You can modify this behavior by changing the value of the **StaticSupport** registry key under **HKEY_LOCAL_MACHINE\Software\Microsoft\BusinessRules\3.0** to one of the values in the following table.</span></span>  
  
|<span data-ttu-id="9ca4f-105">StaticSupport のレジストリ値</span><span class="sxs-lookup"><span data-stu-id="9ca4f-105">StaticSupport registry value</span></span>|<span data-ttu-id="9ca4f-106">ルール エンジンの動作</span><span class="sxs-lookup"><span data-stu-id="9ca4f-106">Rule engine behavior</span></span>|  
|----------------------------------|--------------------------|  
|<span data-ttu-id="9ca4f-107">0</span><span class="sxs-lookup"><span data-stu-id="9ca4f-107">0</span></span>|<span data-ttu-id="9ca4f-108">既定値です。</span><span class="sxs-lookup"><span data-stu-id="9ca4f-108">Default value.</span></span> <span data-ttu-id="9ca4f-109">ルール エンジンは、.NET クラスのインスタンスがアサートされる場合にのみ、静的メソッドが呼び出された場合、BizTalk Server 2004 のモデルに従います。</span><span class="sxs-lookup"><span data-stu-id="9ca4f-109">The rule engine follows the BizTalk Server 2004 model, where the static method is called only when an instance of the .NET class is asserted.</span></span>|  
|<span data-ttu-id="9ca4f-110">1</span><span class="sxs-lookup"><span data-stu-id="9ca4f-110">1</span></span>|<span data-ttu-id="9ca4f-111">オブジェクトのインスタンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="9ca4f-111">An object instance is not required.</span></span> <span data-ttu-id="9ca4f-112">ルールの評価または実行される静的メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="9ca4f-112">The static method is called when the rule is evaluated or executed.</span></span>|  
|<span data-ttu-id="9ca4f-113">2</span><span class="sxs-lookup"><span data-stu-id="9ca4f-113">2</span></span>|<span data-ttu-id="9ca4f-114">オブジェクトのインスタンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="9ca4f-114">An object instance is not required.</span></span> <span data-ttu-id="9ca4f-115">すべてのパラメーターは定数である場合、ポリシーの変換時に静的メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="9ca4f-115">The static method is called at the policy translation time if all parameters are constant.</span></span> <span data-ttu-id="9ca4f-116">これは、条件内の複数のルールで使用されている場合でも、静的メソッドを 1 回だけ呼び出しますので、パフォーマンスの最適化です。</span><span class="sxs-lookup"><span data-stu-id="9ca4f-116">This is a performance optimization because the static method is called only once even though it is used in multiple rules in conditions.</span></span> <span data-ttu-id="9ca4f-117">変換時に、アクションとして使用される静的メソッドは実行されませんが、パラメーターとして使用される静的メソッドが実行されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9ca4f-117">Note that static methods used as actions will not be executed at the translation time, but static methods used as parameters may be executed.</span></span>|  
  
## <a name="adding-and-changing-the-staticsupport-registry-key"></a><span data-ttu-id="9ca4f-118">追加と StaticSupport レジストリ キーの変更</span><span class="sxs-lookup"><span data-stu-id="9ca4f-118">Adding and Changing the StaticSupport Registry Key</span></span>  
 <span data-ttu-id="9ca4f-119">表示されない場合、 **StaticSupport**下のレジストリ キー **HKEY_LOCAL_MACHINE\Software\Microsoft\BusinessRules\3.0**、次の手順を実行することによって追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ca4f-119">If you do not see the **StaticSupport** registry key under **HKEY_LOCAL_MACHINE\Software\Microsoft\BusinessRules\3.0**, you should add it by performing the following steps.</span></span>  
  
 <span data-ttu-id="9ca4f-120">**StaticSupport レジストリ キーを追加するには**</span><span class="sxs-lookup"><span data-stu-id="9ca4f-120">**To add the StaticSupport registry key**</span></span>  
  
1. <span data-ttu-id="9ca4f-121">をクリックして**開始**、 をクリックして**実行**、型**RegEdit**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="9ca4f-121">Click **Start**, click **Run**, type **RegEdit**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="9ca4f-122">展開**HKEY_LOCAL_MACHINE**、展開**ソフトウェア**、展開**Microsoft**、展開**BusinessRules**、し、 **3.0**します。</span><span class="sxs-lookup"><span data-stu-id="9ca4f-122">Expand **HKEY_LOCAL_MACHINE**, expand **Software**, expand **Microsoft**, expand **BusinessRules**, and then select **3.0**.</span></span>  
  
3. <span data-ttu-id="9ca4f-123">右側のウィンドウで右クリックして**新規**、 をクリックし、 **DWORD 値**します。</span><span class="sxs-lookup"><span data-stu-id="9ca4f-123">In the right pane, right-click, point to **New**, and then click **DWORD value**.</span></span>  
  
4. <span data-ttu-id="9ca4f-124">**名前**、型**StaticSupport**します。</span><span class="sxs-lookup"><span data-stu-id="9ca4f-124">For **Name**, type **StaticSupport**.</span></span>  
  
   <span data-ttu-id="9ca4f-125">場合、 **StaticSupport**レジストリ キーが既に存在して、その値を変更するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ca4f-125">If the **StaticSupport** registry key already exists, and you need to change its value, perform the following steps.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9ca4f-126">BizTalk が 64 ビット コンピューターにインストールされているかどうかは、追加することができます**StaticSupport**を使用して、次のオプションのいずれかのレジストリ キー。</span><span class="sxs-lookup"><span data-stu-id="9ca4f-126">If BizTalk is installed on a 64-bit machine, then you can add **StaticSupport** registry key using either of the following options:</span></span>  
> 
> - <span data-ttu-id="9ca4f-127">HKLM\Software\Wow6432Node\Microsoft\BusinessRules\3.0 を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ca4f-127">You need to look under HKLM\Software\Wow6432Node\Microsoft\BusinessRules\3.0.</span></span> <span data-ttu-id="9ca4f-128">このキーが存在するかどうかは、追加することができます**StaticSupport**ここです。</span><span class="sxs-lookup"><span data-stu-id="9ca4f-128">If this key exists, then you can add **StaticSupport** here.</span></span>  
>   -   <span data-ttu-id="9ca4f-129">配置するもう 1 つの方法が**StaticSupport**で、 **BTNTsvc [64].exe.config**ファイルを設定がレジストリの新機能をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="9ca4f-129">Another option is to put **StaticSupport** in the **BTNTsvc[64].exe.config** file, as any settings here override what's in the Registry.</span></span>  <span data-ttu-id="9ca4f-130">さらに、このオプションが優先既定の動作の BizTalk にのみ、分離され、そのためレジストリ設定は、オペレーティング システムのグローバル引数こといずれかのこともできます。</span><span class="sxs-lookup"><span data-stu-id="9ca4f-130">Further, one can also make the argument that this option is preferred since it isolates the change in default behavior to BizTalk only, whereas Registry settings are global to the Operating System.</span></span>  
  
 <span data-ttu-id="9ca4f-131">**StaticSupport レジストリ キーの値を変更するには**</span><span class="sxs-lookup"><span data-stu-id="9ca4f-131">**To change the value of the StaticSupport registry key**</span></span>  
  
1.  <span data-ttu-id="9ca4f-132">をクリックして**開始**、 をクリックして**実行**、型**RegEdit**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="9ca4f-132">Click **Start**, click **Run**, type **RegEdit**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="9ca4f-133">展開**HKEY_LOCAL_MACHINE**、展開**ソフトウェア**、展開**Microsoft**、展開**BusinessRules**を展開し**3.0**します。</span><span class="sxs-lookup"><span data-stu-id="9ca4f-133">Expand **HKEY_LOCAL_MACHINE**, expand **Software**, expand **Microsoft**, expand **BusinessRules**, and then expand **3.0**.</span></span>  
  
3.  <span data-ttu-id="9ca4f-134">ダブルクリックして、 **StaticSupport**レジストリ キー、または右クリックし、をクリックし、**変更**します。</span><span class="sxs-lookup"><span data-stu-id="9ca4f-134">Double-click the **StaticSupport** registry key, or right-click it and then click **Modify**.</span></span>