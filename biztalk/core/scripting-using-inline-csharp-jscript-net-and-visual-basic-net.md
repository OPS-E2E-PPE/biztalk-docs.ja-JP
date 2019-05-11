---
title: インラインを使用したスクリプトをC#、JScript .NET、および Visual Basic .NET |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Scripting functoids, JScript
- Scripting functoids, warnings
- Scripting functoids, Visual Basic .NET
- Scripting functoids, inline C#
- Scripting functoids, .NET
ms.assetid: dda60024-58bd-483f-a750-31b21059eded
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74eca3ecd01af709b6b8c7aefe250e02679445a1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65251222"
---
# <a name="scripting-using-inline-c-jscript-net-and-visual-basic-net"></a><span data-ttu-id="8df0b-102">インライン c#、JScript .NET、および Visual Basic .NET を使用するスクリプト</span><span class="sxs-lookup"><span data-stu-id="8df0b-102">Scripting Using Inline C#, JScript .NET, and Visual Basic .NET</span></span>
<span data-ttu-id="8df0b-103">インライン スクリプトは、いない可能性がある他の場所を使用する、アプリケーションでカスタム コードに便利です。</span><span class="sxs-lookup"><span data-stu-id="8df0b-103">Inline scripts are convenient for custom code that you are unlikely to use elsewhere in your application.</span></span>  
  
 <span data-ttu-id="8df0b-104">BizTalk は、マップを定義する拡張スタイル シート言語変換 (XSLT) スタイル シートでインライン スクリプトを保存します。</span><span class="sxs-lookup"><span data-stu-id="8df0b-104">BizTalk saves inline scripts in the Extensible Stylesheet Language Transformations (XSLT) stylesheet defining the map.</span></span> <span data-ttu-id="8df0b-105">このため、インライン スクリプトは、他の XSLT スタイル シート スクリプトと同じ名前空間を使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="8df0b-105">Because of this, inline scripts may use the same namespaces as any other XSLT stylesheet script.</span></span> <span data-ttu-id="8df0b-106">次の表では、使用可能な名前空間を示します。</span><span class="sxs-lookup"><span data-stu-id="8df0b-106">The following table shows the available namespaces.</span></span>  
  
|<span data-ttu-id="8df0b-107">Namespace</span><span class="sxs-lookup"><span data-stu-id="8df0b-107">Namespace</span></span>|<span data-ttu-id="8df0b-108">説明</span><span class="sxs-lookup"><span data-stu-id="8df0b-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8df0b-109">システム</span><span class="sxs-lookup"><span data-stu-id="8df0b-109">System</span></span>|<span data-ttu-id="8df0b-110">System クラスです。</span><span class="sxs-lookup"><span data-stu-id="8df0b-110">The System class.</span></span>|  
|<span data-ttu-id="8df0b-111">System.Collection</span><span class="sxs-lookup"><span data-stu-id="8df0b-111">System.Collection</span></span>|<span data-ttu-id="8df0b-112">コレクション クラスです。</span><span class="sxs-lookup"><span data-stu-id="8df0b-112">The collection classes.</span></span>|  
|<span data-ttu-id="8df0b-113">System.Text</span><span class="sxs-lookup"><span data-stu-id="8df0b-113">System.Text</span></span>|<span data-ttu-id="8df0b-114">テキスト クラスです。</span><span class="sxs-lookup"><span data-stu-id="8df0b-114">The text classes.</span></span>|  
|<span data-ttu-id="8df0b-115">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="8df0b-115">System.Text.RegularExpressions</span></span>|<span data-ttu-id="8df0b-116">正規表現クラス。</span><span class="sxs-lookup"><span data-stu-id="8df0b-116">The regular expression classes.</span></span>|  
|<span data-ttu-id="8df0b-117">System.Xml</span><span class="sxs-lookup"><span data-stu-id="8df0b-117">System.Xml</span></span>|<span data-ttu-id="8df0b-118">コア XML クラスです。</span><span class="sxs-lookup"><span data-stu-id="8df0b-118">The core XML classes.</span></span>|  
|<span data-ttu-id="8df0b-119">System.Xml.Xsl</span><span class="sxs-lookup"><span data-stu-id="8df0b-119">System.Xml.Xsl</span></span>|<span data-ttu-id="8df0b-120">XSLT クラスです。</span><span class="sxs-lookup"><span data-stu-id="8df0b-120">The XSLT classes.</span></span>|  
|<span data-ttu-id="8df0b-121">System.Xml.Xpath</span><span class="sxs-lookup"><span data-stu-id="8df0b-121">System.Xml.Xpath</span></span>|<span data-ttu-id="8df0b-122">XPath クラスです。</span><span class="sxs-lookup"><span data-stu-id="8df0b-122">The XPath classes.</span></span>|  
|<span data-ttu-id="8df0b-123">Microsoft.VisualBasic</span><span class="sxs-lookup"><span data-stu-id="8df0b-123">Microsoft.VisualBasic</span></span>|<span data-ttu-id="8df0b-124">Visual Basic スクリプト クラスです。</span><span class="sxs-lookup"><span data-stu-id="8df0b-124">The Visual Basic script classes.</span></span>|  
  
 <span data-ttu-id="8df0b-125">名前空間およびデータの種類の詳細については、検索"XSLT スタイル シートのスクリプトを使用して\<msxsl:script\>」と「system.xml.xsl.xslcompiledtransform」で、.NET Framework のコレクション。</span><span class="sxs-lookup"><span data-stu-id="8df0b-125">For more information about namespaces and data types, search on "XSLT Stylesheet Scripting using \<msxsl:script\>" and on "System.Xml.Xsl.XslCompiledTransform" in the .NET Framework collection.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="8df0b-126">同じメソッド シグネチャを複数回使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="8df0b-126">Avoid using the same method signature more than once.</span></span> <span data-ttu-id="8df0b-127">複数のスクリプト functoid には、同じメソッド シグネチャがある、BizTalk は最初の実装を選択し、他は無視されます。</span><span class="sxs-lookup"><span data-stu-id="8df0b-127">When several Scripting functoids have the same method signature, BizTalk selects the first implementation and disregards the others.</span></span>  
  
 <span data-ttu-id="8df0b-128">1 回限りのスクリプトの便利なだけインライン スクリプトもスクリプトの数の間で使用するためのグローバル変数を宣言する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="8df0b-128">In addition to being convenient for one-time scripts, inline scripts are also useful for declaring global variables for use among a number of scripts.</span></span> <span data-ttu-id="8df0b-129">など、C#インライン スクリプトでは、次の任意のクラスの外部でのコード行に配置することです。</span><span class="sxs-lookup"><span data-stu-id="8df0b-129">For example, in a C# inline script, you could place the following line of code outside of any class.</span></span>  
  
```  
ArrayList statusList = new ArrayList();  
```  
  
 <span data-ttu-id="8df0b-130">これを作成、 **ArrayList**、`statusList`マップ内のすべてのインライン スクリプトを使用できます。</span><span class="sxs-lookup"><span data-stu-id="8df0b-130">This creates an **ArrayList**, `statusList`, available to all inline scripts in the map.</span></span>  
  
 <span data-ttu-id="8df0b-131">サンプル インライン スクリプトでは、次を参照してください。 [XML ツール (BizTalk Server Samples フォルダー)](../core/xml-tools-biztalk-server-samples-folder.md)します。</span><span class="sxs-lookup"><span data-stu-id="8df0b-131">For a sample inline script, see [XML Tools (BizTalk Server Samples Folder)](../core/xml-tools-biztalk-server-samples-folder.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8df0b-132">参照</span><span class="sxs-lookup"><span data-stu-id="8df0b-132">See Also</span></span>  
 <span data-ttu-id="8df0b-133">[スクリプト Functoid](../core/scripting-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="8df0b-133">[Scripting Functoid](../core/scripting-functoid.md) </span></span>  
 <span data-ttu-id="8df0b-134">[外部アセンブリを使用するスクリプト](../core/scripting-using-external-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="8df0b-134">[Scripting Using External Assemblies](../core/scripting-using-external-assemblies.md) </span></span>  
 <span data-ttu-id="8df0b-135">[使用してインライン XSLT および XSLT 呼び出しテンプレート スクリプト](../core/scripting-using-inline-xslt-and-xslt-call-templates.md) </span><span class="sxs-lookup"><span data-stu-id="8df0b-135">[Scripting Using Inline XSLT and XSLT Call Templates](../core/scripting-using-inline-xslt-and-xslt-call-templates.md) </span></span>  
 <span data-ttu-id="8df0b-136">[マップにスクリプト Functoid を追加する方法](../core/how-to-add-scripting-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="8df0b-136">[How to Add Scripting Functoids to a Map](../core/how-to-add-scripting-functoids-to-a-map.md) </span></span>  
 [<span data-ttu-id="8df0b-137">スクリプト Functoid の構成方法</span><span class="sxs-lookup"><span data-stu-id="8df0b-137">How to Configure the Scripting Functoid</span></span>](../core/how-to-configure-the-scripting-functoid.md)