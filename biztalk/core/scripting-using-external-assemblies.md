---
title: "外部アセンブリを使用するスクリプト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Scripting functoids, warnings
- Scripting functoids, external assemblies
ms.assetid: 0bdf6adc-91b9-462e-8fd0-9cb48bfa7817
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 475a3b9781eecb0ccc79165bbe54e6dfd542ecfc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="scripting-using-external-assemblies"></a><span data-ttu-id="c0c1a-102">外部アセンブリを使用するスクリプト</span><span class="sxs-lookup"><span data-stu-id="c0c1a-102">Scripting Using External Assemblies</span></span>
<span data-ttu-id="c0c1a-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でスクリプトを使用する場合は、外部アセンブリを使ったスクリプトをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c0c1a-103">Scripting with external assemblies is the preferred way to use scripting in Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="c0c1a-104">外部アセンブリは、いくつかの利点を提供します。</span><span class="sxs-lookup"><span data-stu-id="c0c1a-104">External assemblies provide several advantages:</span></span>  
  
-   <span data-ttu-id="c0c1a-105">コードを簡単に共有できる</span><span class="sxs-lookup"><span data-stu-id="c0c1a-105">Easy code sharing</span></span>  
  
-   <span data-ttu-id="c0c1a-106">保守が簡単である</span><span class="sxs-lookup"><span data-stu-id="c0c1a-106">Simpler maintenance</span></span>  
  
-   <span data-ttu-id="c0c1a-107">デバッグが簡単である</span><span class="sxs-lookup"><span data-stu-id="c0c1a-107">Easier debugging</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c0c1a-108">場合、マップのテストが失敗した、**スクリプト**functoid が GAC に登録されていない外部アセンブリを使用します。</span><span class="sxs-lookup"><span data-stu-id="c0c1a-108">Test Map fails if the **Scripting** functoid uses an external assembly which is not registered in the GAC.</span></span> <span data-ttu-id="c0c1a-109">正しく機能させるためには、外部アセンブリが、(ビルド後に配置される) 現在のプロジェクトのアセンブリと同じ bin フォルダーに格納されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0c1a-109">It works if the external assembly is in the same bin folder as the current project's assembly (placed after build).</span></span>  
  
 <span data-ttu-id="c0c1a-110">設定スクリプトの再利用のみが必要です、**スクリプト**のプロパティ、**スクリプト**functoid です。</span><span class="sxs-lookup"><span data-stu-id="c0c1a-110">Re-using the script only requires setting the **Script** property of the **Scripting** functoid.</span></span> <span data-ttu-id="c0c1a-111">スクリプトはマップの外部に格納されるため、マップを変更することなくスクリプトを変更できます。</span><span class="sxs-lookup"><span data-stu-id="c0c1a-111">Because the script is stored outside of the map, you can modify the script without changing the map.</span></span> <span data-ttu-id="c0c1a-112">また、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] デバッグ ツールの全機能を使用して、スクリプトが正常に実行されることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="c0c1a-112">And you can use the full array of [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] debugging tools to ensure your script runs correctly.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="c0c1a-113">外部アセンブリのコードは、スレッド セーフであることが必要です。</span><span class="sxs-lookup"><span data-stu-id="c0c1a-113">The code in the external assembly must be thread-safe.</span></span> <span data-ttu-id="c0c1a-114">ストレス条件下では、マップの複数のインスタンスが同時に実行される場合があります。</span><span class="sxs-lookup"><span data-stu-id="c0c1a-114">Under stress conditions, multiple instances of a map may be running concurrently.</span></span>  
  
 <span data-ttu-id="c0c1a-115">サンプル関数の外部アセンブリに格納されていた場合、次を参照してください。 [XML ツール (BizTalk Server Samples フォルダ)](../core/xml-tools-biztalk-server-samples-folder.md)です。</span><span class="sxs-lookup"><span data-stu-id="c0c1a-115">For a sample function housed in an external assembly, see [XML Tools (BizTalk Server Samples Folder)](../core/xml-tools-biztalk-server-samples-folder.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0c1a-116">参照</span><span class="sxs-lookup"><span data-stu-id="c0c1a-116">See Also</span></span>  
 <span data-ttu-id="c0c1a-117">[スクリプト Functoid](../core/scripting-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="c0c1a-117">[Scripting Functoid](../core/scripting-functoid.md) </span></span>  
 <span data-ttu-id="c0c1a-118">[インライン c#、JScript .NET、および Visual Basic .NET を使用するスクリプト](../core/scripting-using-inline-csharp-jscript-net-and-visual-basic-net.md) </span><span class="sxs-lookup"><span data-stu-id="c0c1a-118">[Scripting Using Inline C#, JScript .NET, and Visual Basic .NET](../core/scripting-using-inline-csharp-jscript-net-and-visual-basic-net.md) </span></span>  
 <span data-ttu-id="c0c1a-119">[スクリプトを使用してインライン XSLT および XSLT 呼び出しテンプレート](../core/scripting-using-inline-xslt-and-xslt-call-templates.md) </span><span class="sxs-lookup"><span data-stu-id="c0c1a-119">[Scripting Using Inline XSLT and XSLT Call Templates](../core/scripting-using-inline-xslt-and-xslt-call-templates.md) </span></span>  
 <span data-ttu-id="c0c1a-120">[スクリプト Functoid をマップに追加する方法](../core/how-to-add-scripting-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="c0c1a-120">[How to Add Scripting Functoids to a Map](../core/how-to-add-scripting-functoids-to-a-map.md) </span></span>  
 [<span data-ttu-id="c0c1a-121">スクリプト Functoid を構成する方法</span><span class="sxs-lookup"><span data-stu-id="c0c1a-121">How to Configure the Scripting Functoid</span></span>](../core/how-to-configure-the-scripting-functoid.md)