---
title: Functoid の移行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- functoids, migrating
- migrating, maps
- Migrating functoids, about Migrating functoids
- Migrating functoids
- Scripting functoids
- migrating, functoids
- migrating, Scripting functoids
ms.assetid: fc5b3ac9-28c6-41df-b779-15a8c3188528
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b01f37551b9d4c1aef13786be7094504f8cee08
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37020504"
---
# <a name="migrating-functoids"></a><span data-ttu-id="b2778-102">Functoid の移行</span><span class="sxs-lookup"><span data-stu-id="b2778-102">Migrating Functoids</span></span>
<span data-ttu-id="b2778-103">BizTalk Server の以前のバージョンから BizTalk Server にマップを移行する場合、マップに含まれる functoid も移行されます。</span><span class="sxs-lookup"><span data-stu-id="b2778-103">When you migrate a map from previous versions of BizTalk Server to BizTalk Server, any functoids included in the map are also migrated.</span></span> <span data-ttu-id="b2778-104">移行する functoid が含まれない場合**Scripting** functoid の場合、追加の移行タスクは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="b2778-104">If the functoids you migrate do not include **Scripting** functoids, no additional migration tasks are required.</span></span> <span data-ttu-id="b2778-105">ただし、マップが含まれている場合**Scripting** functoid またはカスタム functoid では、追加の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2778-105">However if your map includes **Scripting** functoids or custom functoids, you may have additional steps to perform.</span></span>  
  
 <span data-ttu-id="b2778-106">BizTalk Server の以前のバージョンに含まれるすべてのカスタム スクリプトを**Scripting** functoid はインラインで書き込まれました。</span><span class="sxs-lookup"><span data-stu-id="b2778-106">In previous versions of BizTalk Server, all custom script included with a **Scripting** functoid was written inline.</span></span> <span data-ttu-id="b2778-107">つまり、Functoid を作成する際、実行時に Functoid で呼び出されるすべてのスクリプトが Functoid と共に格納されていました。</span><span class="sxs-lookup"><span data-stu-id="b2778-107">That is, when you created the functoid, all the script the functoid called during run time was stored with the functoid.</span></span> <span data-ttu-id="b2778-108">別の functoid で同じスクリプトを使用する場合をコピーして貼り付けるか、いずれかから**Scripting**にするか、別の functoid がゼロからスクリプトを書き直しています。</span><span class="sxs-lookup"><span data-stu-id="b2778-108">If you wanted to use the same script with a different functoid, you either copied and pasted it from one **Scripting** functoid to another, or you rewrote the script from scratch.</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="b2778-109">では、マップを移行すると、Functoid と共に既存のインライン スクリプトもコピーされます。</span><span class="sxs-lookup"><span data-stu-id="b2778-109">copies existing inline scripts with the functoids when you migrate a map.</span></span> <span data-ttu-id="b2778-110">ただし、すべてのスクリプトが正しく機能します。</span><span class="sxs-lookup"><span data-stu-id="b2778-110">However, not all of the scripts may function correctly.</span></span> <span data-ttu-id="b2778-111">BizTalk Server は、VBScript ではなく、Visual Basic .NET および JScript .NET を使用し、JScript が以前のバージョンで使用します。</span><span class="sxs-lookup"><span data-stu-id="b2778-111">BizTalk Server uses Visual Basic .NET and JScript .NET rather than the VBScript and JScript used in previous versions.</span></span> <span data-ttu-id="b2778-112">.NET バージョンの言語では、構文に一部の変更があります。</span><span class="sxs-lookup"><span data-stu-id="b2778-112">The .NET versions of the languages include some changes in syntax.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b2778-113">必ずテストして、 **Scripting** functoid は移行後にします。</span><span class="sxs-lookup"><span data-stu-id="b2778-113">Be sure to test your **Scripting** functoids after migration.</span></span>  
  
 <span data-ttu-id="b2778-114">カスタム functoid を書き直す必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2778-114">You will need to rewrite custom functoids.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="b2778-115">.NET framework を使用するカスタム functoid が必要です。</span><span class="sxs-lookup"><span data-stu-id="b2778-115">expects custom functoids to use the .NET framework.</span></span> <span data-ttu-id="b2778-116">COM ベースの古いカスタム Functoid は使用できません。</span><span class="sxs-lookup"><span data-stu-id="b2778-116">It cannot use the older, COM-based custom functoids.</span></span> <span data-ttu-id="b2778-117">.NET Framework を使用するように、カスタム Functoid を作成し直してください。</span><span class="sxs-lookup"><span data-stu-id="b2778-117">Custom functoids can be rewritten to use the .NET framework.</span></span> <span data-ttu-id="b2778-118">カスタム functoid のサンプル コードを参照してください。[カスタム Functoid (BizTalk Server サンプル)](../core/custom-functoid-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="b2778-118">For sample code of a custom functoid, see [Custom Functoid (BizTalk Server Sample)](../core/custom-functoid-biztalk-server-sample.md).</span></span>  
  
 <span data-ttu-id="b2778-119">代わりに、外部アセンブリにカスタム functoid の機能をラップし、使用してこのアセンブリを呼び出すし、 **Scripting** functoid。</span><span class="sxs-lookup"><span data-stu-id="b2778-119">An alternative is to wrap the functionality of the custom functoid in an external assembly and call this assembly through a **Scripting** functoid.</span></span> <span data-ttu-id="b2778-120">次のセクションでは、この方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b2778-120">The following section describes this process.</span></span>  
  
### <a name="to-migrate-your-custom-functoids"></a><span data-ttu-id="b2778-121">カスタム Functoid を移行するには</span><span class="sxs-lookup"><span data-stu-id="b2778-121">To migrate your custom functoids</span></span>  
  
1. <span data-ttu-id="b2778-122">Functoid の機能を、Microsoft Visual Basic .NET、JScript .NET、Microsoft Visual C# .NET などの .NET 言語で再作成します。</span><span class="sxs-lookup"><span data-stu-id="b2778-122">Re-create the functionality of the functoid in a .NET language, such as Microsoft Visual Basic .NET, JScript .NET, or Microsoft Visual C# .NET.</span></span>  
  
2. <span data-ttu-id="b2778-123">新しい機能を含むアセンブリを作成します。</span><span class="sxs-lookup"><span data-stu-id="b2778-123">Create an assembly to contain the new functionality.</span></span>  
  
3. <span data-ttu-id="b2778-124">グローバル アセンブリ キャッシュ (GAC) にアセンブリを登録します。</span><span class="sxs-lookup"><span data-stu-id="b2778-124">Register the assembly in the global assembly cache (GAC).</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="b2778-125">グローバル アセンブリ キャッシュにアセンブリを登録するには、アセンブリに厳密な名前を付けて署名する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2778-125">To register assemblies in the global assembly cache, they must be strong named and signed.</span></span> <span data-ttu-id="b2778-126">アセンブリ登録の詳細については、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 連結ヘルプ コレクションの「グローバル アセンブリ キャッシュ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2778-126">For more information about registering assemblies, see "Global Assembly Cache" in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Combined Collection.</span></span>  
  
4. <span data-ttu-id="b2778-127">含むマップとの間の参照を作成、 **Scripting** functoid と再作成された機能を格納するアセンブリ。</span><span class="sxs-lookup"><span data-stu-id="b2778-127">Create a reference between the map that contains the **Scripting** functoid and the assembly that contains the rewritten functionality.</span></span>  
  
5. <span data-ttu-id="b2778-128">構成、**スクリプト**プロパティを**Scripting** functoid。</span><span class="sxs-lookup"><span data-stu-id="b2778-128">Configure the **Script** property for the **Scripting** functoid.</span></span> <span data-ttu-id="b2778-129">このプロパティは、どのようなスクリプトを決定します、 **Scripting**実行時に functoid の呼び出し。</span><span class="sxs-lookup"><span data-stu-id="b2778-129">This property determines what script the **Scripting** functoid calls during run time.</span></span> <span data-ttu-id="b2778-130">このプロパティの値と、カスタム スクリプトの再作成で使用した言語を一致させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2778-130">You must match the value of this property to the language into which you converted your custom script.</span></span> <span data-ttu-id="b2778-131">スクリプト プロパティを構成する方法の詳細については、[Functoid のプロパティを編集および入力パラメーター](../core/editing-functoid-properties-and-input-parameters.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2778-131">For more information about how to configure the Script property, see [Editing Functoid Properties and Input Parameters](../core/editing-functoid-properties-and-input-parameters.md).</span></span> <span data-ttu-id="b2778-132">参照してください[スクリプト Functoid の](../core/scripting-functoid.md)します。</span><span class="sxs-lookup"><span data-stu-id="b2778-132">Also see [Scripting Functoid](../core/scripting-functoid.md).</span></span>  
  
6. <span data-ttu-id="b2778-133">マップを含んでいる BizTalk プロジェクトをビルド、 **Scripting** functoid。</span><span class="sxs-lookup"><span data-stu-id="b2778-133">Build the BizTalk project that contains the map with the **Scripting** functoid.</span></span>  
  
7. <span data-ttu-id="b2778-134">マップの検証とテストを行います。</span><span class="sxs-lookup"><span data-stu-id="b2778-134">Validate and test the map.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2778-135">参照</span><span class="sxs-lookup"><span data-stu-id="b2778-135">See Also</span></span>  
 <span data-ttu-id="b2778-136">[Functoid のプロパティおよび入力パラメーターの編集](../core/editing-functoid-properties-and-input-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="b2778-136">[Editing Functoid Properties and Input Parameters](../core/editing-functoid-properties-and-input-parameters.md) </span></span>  
 [<span data-ttu-id="b2778-137">スクリプト Functoid</span><span class="sxs-lookup"><span data-stu-id="b2778-137">Scripting Functoid</span></span>](../core/scripting-functoid.md)