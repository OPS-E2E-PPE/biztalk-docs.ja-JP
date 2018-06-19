---
title: Functoid の移行 |Microsoft ドキュメント
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
ms.openlocfilehash: 5fac30a9b884bc769752623003d16e7089b140d4
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26009323"
---
# <a name="migrating-functoids"></a><span data-ttu-id="7a5ec-102">Functoid の移行</span><span class="sxs-lookup"><span data-stu-id="7a5ec-102">Migrating Functoids</span></span>
<span data-ttu-id="7a5ec-103">以前のバージョンの BizTalk Server から BizTalk Server にマップを移行するときに、マップに含まれる functoid も移行します。</span><span class="sxs-lookup"><span data-stu-id="7a5ec-103">When you migrate a map from previous versions of BizTalk Server to BizTalk Server, any functoids included in the map are also migrated.</span></span> <span data-ttu-id="7a5ec-104">移行する functoid が含まれない場合**スクリプト**functoid、追加の移行タスクは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="7a5ec-104">If the functoids you migrate do not include **Scripting** functoids, no additional migration tasks are required.</span></span> <span data-ttu-id="7a5ec-105">ただし、マップが含まれる場合**スクリプト**functoid またはカスタム functoid を追加の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a5ec-105">However if your map includes **Scripting** functoids or custom functoids, you may have additional steps to perform.</span></span>  
  
 <span data-ttu-id="7a5ec-106">すべてのカスタム スクリプトを BizTalk Server の以前のバージョンに含まれている、**スクリプト**functoid がインラインで書き込まれました。</span><span class="sxs-lookup"><span data-stu-id="7a5ec-106">In previous versions of BizTalk Server, all custom script included with a **Scripting** functoid was written inline.</span></span> <span data-ttu-id="7a5ec-107">つまり、Functoid を作成する際、実行時に Functoid で呼び出されるすべてのスクリプトが Functoid と共に格納されていました。</span><span class="sxs-lookup"><span data-stu-id="7a5ec-107">That is, when you created the functoid, all the script the functoid called during run time was stored with the functoid.</span></span> <span data-ttu-id="7a5ec-108">別の functoid で同じスクリプトを使用する場合をコピーして貼り付けるか、いずれかから**スクリプト**するか、別の functoid を最初からスクリプトを書き直していました。</span><span class="sxs-lookup"><span data-stu-id="7a5ec-108">If you wanted to use the same script with a different functoid, you either copied and pasted it from one **Scripting** functoid to another, or you rewrote the script from scratch.</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="7a5ec-109"> では、マップを移行すると、Functoid と共に既存のインライン スクリプトもコピーされます。</span><span class="sxs-lookup"><span data-stu-id="7a5ec-109"> copies existing inline scripts with the functoids when you migrate a map.</span></span> <span data-ttu-id="7a5ec-110">ただし、すべてのスクリプトは正常に機能します。</span><span class="sxs-lookup"><span data-stu-id="7a5ec-110">However, not all of the scripts may function correctly.</span></span> <span data-ttu-id="7a5ec-111">BizTalk Server は、VBScript ではなく、Visual Basic .NET および JScript .NET を使用し、JScript が以前のバージョンで使用します。</span><span class="sxs-lookup"><span data-stu-id="7a5ec-111">BizTalk Server uses Visual Basic .NET and JScript .NET rather than the VBScript and JScript used in previous versions.</span></span> <span data-ttu-id="7a5ec-112">.NET バージョンの言語では、構文に一部の変更があります。</span><span class="sxs-lookup"><span data-stu-id="7a5ec-112">The .NET versions of the languages include some changes in syntax.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7a5ec-113">必ずテストして、**スクリプト**functoid を移行した後です。</span><span class="sxs-lookup"><span data-stu-id="7a5ec-113">Be sure to test your **Scripting** functoids after migration.</span></span>  
  
 <span data-ttu-id="7a5ec-114">カスタム functoid を書き直す必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a5ec-114">You will need to rewrite custom functoids.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="7a5ec-115">.NET framework を使用するカスタム functoid が必要です。</span><span class="sxs-lookup"><span data-stu-id="7a5ec-115"> expects custom functoids to use the .NET framework.</span></span> <span data-ttu-id="7a5ec-116">COM ベースの古いカスタム Functoid は使用できません。</span><span class="sxs-lookup"><span data-stu-id="7a5ec-116">It cannot use the older, COM-based custom functoids.</span></span> <span data-ttu-id="7a5ec-117">.NET Framework を使用するように、カスタム Functoid を作成し直してください。</span><span class="sxs-lookup"><span data-stu-id="7a5ec-117">Custom functoids can be rewritten to use the .NET framework.</span></span> <span data-ttu-id="7a5ec-118">カスタム functoid のサンプル コードは、次を参照してください。[カスタム Functoid (BizTalk Server サンプル)](../core/custom-functoid-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="7a5ec-118">For sample code of a custom functoid, see [Custom Functoid (BizTalk Server Sample)](../core/custom-functoid-biztalk-server-sample.md).</span></span>  
  
 <span data-ttu-id="7a5ec-119">外部アセンブリにカスタム functoid の機能をラップして、によってこのアセンブリを呼び出すには、代わりに、**スクリプト**functoid です。</span><span class="sxs-lookup"><span data-stu-id="7a5ec-119">An alternative is to wrap the functionality of the custom functoid in an external assembly and call this assembly through a **Scripting** functoid.</span></span> <span data-ttu-id="7a5ec-120">次のセクションでは、この方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7a5ec-120">The following section describes this process.</span></span>  
  
### <a name="to-migrate-your-custom-functoids"></a><span data-ttu-id="7a5ec-121">カスタム Functoid を移行するには</span><span class="sxs-lookup"><span data-stu-id="7a5ec-121">To migrate your custom functoids</span></span>  
  
1.  <span data-ttu-id="7a5ec-122">Functoid の機能を、Microsoft Visual Basic .NET、JScript .NET、Microsoft Visual C# .NET などの .NET 言語で再作成します。</span><span class="sxs-lookup"><span data-stu-id="7a5ec-122">Re-create the functionality of the functoid in a .NET language, such as Microsoft Visual Basic .NET, JScript .NET, or Microsoft Visual C# .NET.</span></span>  
  
2.  <span data-ttu-id="7a5ec-123">新しい機能を含むアセンブリを作成します。</span><span class="sxs-lookup"><span data-stu-id="7a5ec-123">Create an assembly to contain the new functionality.</span></span>  
  
3.  <span data-ttu-id="7a5ec-124">グローバル アセンブリ キャッシュ (GAC) にアセンブリを登録します。</span><span class="sxs-lookup"><span data-stu-id="7a5ec-124">Register the assembly in the global assembly cache (GAC).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7a5ec-125">グローバル アセンブリ キャッシュにアセンブリを登録するには、アセンブリに厳密な名前を付けて署名する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a5ec-125">To register assemblies in the global assembly cache, they must be strong named and signed.</span></span> <span data-ttu-id="7a5ec-126">アセンブリ登録の詳細については、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 連結ヘルプ コレクションの「グローバル アセンブリ キャッシュ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a5ec-126">For more information about registering assemblies, see "Global Assembly Cache" in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Combined Collection.</span></span>  
  
4.  <span data-ttu-id="7a5ec-127">含むマップとの間の参照を作成、**スクリプト**functoid とを再作成された機能を含むアセンブリです。</span><span class="sxs-lookup"><span data-stu-id="7a5ec-127">Create a reference between the map that contains the **Scripting** functoid and the assembly that contains the rewritten functionality.</span></span>  
  
5.  <span data-ttu-id="7a5ec-128">構成、**スクリプト**プロパティを**スクリプト**functoid です。</span><span class="sxs-lookup"><span data-stu-id="7a5ec-128">Configure the **Script** property for the **Scripting** functoid.</span></span> <span data-ttu-id="7a5ec-129">このプロパティは、どのようなスクリプトを決定、**スクリプト**functoid の呼び出し時に実行します。</span><span class="sxs-lookup"><span data-stu-id="7a5ec-129">This property determines what script the **Scripting** functoid calls during run time.</span></span> <span data-ttu-id="7a5ec-130">このプロパティの値と、カスタム スクリプトの再作成で使用した言語を一致させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a5ec-130">You must match the value of this property to the language into which you converted your custom script.</span></span> <span data-ttu-id="7a5ec-131">スクリプト プロパティを構成する方法の詳細については、次を参照してください。 [Functoid のプロパティを編集および入力パラメーター](../core/editing-functoid-properties-and-input-parameters.md)です。</span><span class="sxs-lookup"><span data-stu-id="7a5ec-131">For more information about how to configure the Script property, see [Editing Functoid Properties and Input Parameters](../core/editing-functoid-properties-and-input-parameters.md).</span></span> <span data-ttu-id="7a5ec-132">参照してください[スクリプト Functoid の](../core/scripting-functoid.md)します。</span><span class="sxs-lookup"><span data-stu-id="7a5ec-132">Also see [Scripting Functoid](../core/scripting-functoid.md).</span></span>  
  
6.  <span data-ttu-id="7a5ec-133">マップを含んでいる BizTalk プロジェクトをビルド、**スクリプト**functoid です。</span><span class="sxs-lookup"><span data-stu-id="7a5ec-133">Build the BizTalk project that contains the map with the **Scripting** functoid.</span></span>  
  
7.  <span data-ttu-id="7a5ec-134">マップの検証とテストを行います。</span><span class="sxs-lookup"><span data-stu-id="7a5ec-134">Validate and test the map.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a5ec-135">参照</span><span class="sxs-lookup"><span data-stu-id="7a5ec-135">See Also</span></span>  
 <span data-ttu-id="7a5ec-136">[Functoid のプロパティおよび入力パラメーターの編集](../core/editing-functoid-properties-and-input-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="7a5ec-136">[Editing Functoid Properties and Input Parameters](../core/editing-functoid-properties-and-input-parameters.md) </span></span>  
 [<span data-ttu-id="7a5ec-137">スクリプト Functoid</span><span class="sxs-lookup"><span data-stu-id="7a5ec-137">Scripting Functoid</span></span>](../core/scripting-functoid.md)