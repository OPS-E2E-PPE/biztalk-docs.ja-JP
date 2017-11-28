---
title: "インライン c#、JScript .NET、および Visual Basic .NET を使用するスクリプト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Scripting functoids, JScript
- Scripting functoids, warnings
- Scripting functoids, Visual Basic .NET
- Scripting functoids, inline C#
- Scripting functoids, .NET
ms.assetid: dda60024-58bd-483f-a750-31b21059eded
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 68fe19b4616e23066603995b6403654fa3960789
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="scripting-using-inline-c-jscript-net-and-visual-basic-net"></a><span data-ttu-id="69180-102">インライン C#、JScript .NET、および Visual Basic .NET を使用するスクリプト</span><span class="sxs-lookup"><span data-stu-id="69180-102">Scripting Using Inline C#, JScript .NET, and Visual Basic .NET</span></span>
<span data-ttu-id="69180-103">インライン スクリプトは、カスタム コードとして利用できます。ただし、このコードは、アプリケーション以外で使用されることはほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="69180-103">Inline scripts are convenient for custom code that you are unlikely to use elsewhere in your application.</span></span>  
  
 <span data-ttu-id="69180-104">BizTalk は、マップを定義する XSLT (Extensible Stylesheet Language Transformations) スタイルシートでインライン スクリプトを保存します。</span><span class="sxs-lookup"><span data-stu-id="69180-104">BizTalk saves inline scripts in the Extensible Stylesheet Language Transformations (XSLT) stylesheet defining the map.</span></span> <span data-ttu-id="69180-105">このため、インライン スクリプトは、他の XSLT スタイルシート スクリプトと同じ名前空間を使用できます。</span><span class="sxs-lookup"><span data-stu-id="69180-105">Because of this, inline scripts may use the same namespaces as any other XSLT stylesheet script.</span></span> <span data-ttu-id="69180-106">使用可能な名前空間は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="69180-106">The following table shows the available namespaces.</span></span>  
  
|<span data-ttu-id="69180-107">名前空間</span><span class="sxs-lookup"><span data-stu-id="69180-107">Namespace</span></span>|<span data-ttu-id="69180-108">Description</span><span class="sxs-lookup"><span data-stu-id="69180-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="69180-109">システム</span><span class="sxs-lookup"><span data-stu-id="69180-109">System</span></span>|<span data-ttu-id="69180-110">System クラスです。</span><span class="sxs-lookup"><span data-stu-id="69180-110">The System class.</span></span>|  
|<span data-ttu-id="69180-111">System.Collection</span><span class="sxs-lookup"><span data-stu-id="69180-111">System.Collection</span></span>|<span data-ttu-id="69180-112">コレクション クラスです。</span><span class="sxs-lookup"><span data-stu-id="69180-112">The collection classes.</span></span>|  
|<span data-ttu-id="69180-113">System.Text</span><span class="sxs-lookup"><span data-stu-id="69180-113">System.Text</span></span>|<span data-ttu-id="69180-114">テキスト クラスです。</span><span class="sxs-lookup"><span data-stu-id="69180-114">The text classes.</span></span>|  
|<span data-ttu-id="69180-115">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="69180-115">System.Text.RegularExpressions</span></span>|<span data-ttu-id="69180-116">正規表現のクラスです。</span><span class="sxs-lookup"><span data-stu-id="69180-116">The regular expression classes.</span></span>|  
|<span data-ttu-id="69180-117">System.Xml</span><span class="sxs-lookup"><span data-stu-id="69180-117">System.Xml</span></span>|<span data-ttu-id="69180-118">コア XML クラスです。</span><span class="sxs-lookup"><span data-stu-id="69180-118">The core XML classes.</span></span>|  
|<span data-ttu-id="69180-119">System.Xml.Xsl</span><span class="sxs-lookup"><span data-stu-id="69180-119">System.Xml.Xsl</span></span>|<span data-ttu-id="69180-120">XSLT クラスです。</span><span class="sxs-lookup"><span data-stu-id="69180-120">The XSLT classes.</span></span>|  
|<span data-ttu-id="69180-121">System.Xml.Xpath</span><span class="sxs-lookup"><span data-stu-id="69180-121">System.Xml.Xpath</span></span>|<span data-ttu-id="69180-122">XPath クラスです。</span><span class="sxs-lookup"><span data-stu-id="69180-122">The XPath classes.</span></span>|  
|<span data-ttu-id="69180-123">Microsoft.VisualBasic</span><span class="sxs-lookup"><span data-stu-id="69180-123">Microsoft.VisualBasic</span></span>|<span data-ttu-id="69180-124">Visual Basic スクリプト クラスです。</span><span class="sxs-lookup"><span data-stu-id="69180-124">The Visual Basic script classes.</span></span>|  
  
 <span data-ttu-id="69180-125">名前空間およびデータ型の詳細についてを検索して"XSLT スタイル シートのスクリプトを使用して\<msxsl:script >"と「system.xml.xsl.xslcompiledtransform」で .NET Framework のコレクション。</span><span class="sxs-lookup"><span data-stu-id="69180-125">For more information about namespaces and data types, search on "XSLT Stylesheet Scripting using \<msxsl:script>" and on "System.Xml.Xsl.XslCompiledTransform" in the .NET Framework collection.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="69180-126">同じメソッド シグネチャを複数回使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="69180-126">Avoid using the same method signature more than once.</span></span> <span data-ttu-id="69180-127">複数のスクリプト Functoid が同じメソッド シグネチャを持つ場合、BizTalk は、最初の実装を選択し、他の実装を無視します。</span><span class="sxs-lookup"><span data-stu-id="69180-127">When several Scripting functoids have the same method signature, BizTalk selects the first implementation and disregards the others.</span></span>  
  
 <span data-ttu-id="69180-128">一度のみのスクリプトに役立つだけでなく、インライン スクリプトは、多くのスクリプトで使用するグローバル変数を宣言する場合にも利用できます。</span><span class="sxs-lookup"><span data-stu-id="69180-128">In addition to being convenient for one-time scripts, inline scripts are also useful for declaring global variables for use among a number of scripts.</span></span> <span data-ttu-id="69180-129">たとえば、C# インライン スクリプトで、クラスの外部に次のコード行を配置できます。</span><span class="sxs-lookup"><span data-stu-id="69180-129">For example, in a C# inline script, you could place the following line of code outside of any class.</span></span>  
  
```  
ArrayList statusList = new ArrayList();  
```  
  
 <span data-ttu-id="69180-130">これを作成、 **ArrayList**、`statusList`は、マップ内のすべてのインライン スクリプトを利用できます。</span><span class="sxs-lookup"><span data-stu-id="69180-130">This creates an **ArrayList**, `statusList`, available to all inline scripts in the map.</span></span>  
  
 <span data-ttu-id="69180-131">サンプル インライン スクリプトでは、次を参照してください。 [XML ツール (BizTalk Server Samples フォルダ)](../core/xml-tools-biztalk-server-samples-folder.md)です。</span><span class="sxs-lookup"><span data-stu-id="69180-131">For a sample inline script, see [XML Tools (BizTalk Server Samples Folder)](../core/xml-tools-biztalk-server-samples-folder.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69180-132">参照</span><span class="sxs-lookup"><span data-stu-id="69180-132">See Also</span></span>  
 <span data-ttu-id="69180-133">[スクリプト Functoid](../core/scripting-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="69180-133">[Scripting Functoid](../core/scripting-functoid.md) </span></span>  
 <span data-ttu-id="69180-134">[外部アセンブリを使用するスクリプト](../core/scripting-using-external-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="69180-134">[Scripting Using External Assemblies](../core/scripting-using-external-assemblies.md) </span></span>  
 <span data-ttu-id="69180-135">[スクリプトを使用してインライン XSLT および XSLT 呼び出しテンプレート](../core/scripting-using-inline-xslt-and-xslt-call-templates.md) </span><span class="sxs-lookup"><span data-stu-id="69180-135">[Scripting Using Inline XSLT and XSLT Call Templates](../core/scripting-using-inline-xslt-and-xslt-call-templates.md) </span></span>  
 <span data-ttu-id="69180-136">[スクリプト Functoid をマップに追加する方法](../core/how-to-add-scripting-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="69180-136">[How to Add Scripting Functoids to a Map](../core/how-to-add-scripting-functoids-to-a-map.md) </span></span>  
 [<span data-ttu-id="69180-137">スクリプト Functoid を構成する方法</span><span class="sxs-lookup"><span data-stu-id="69180-137">How to Configure the Scripting Functoid</span></span>](../core/how-to-configure-the-scripting-functoid.md)