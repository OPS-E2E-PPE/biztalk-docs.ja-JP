---
title: 外部アセンブリを使用したスクリプト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Scripting functoids, warnings
- Scripting functoids, external assemblies
ms.assetid: 0bdf6adc-91b9-462e-8fd0-9cb48bfa7817
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4876d0b7c236be890649e5050b09e538b07742a3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395524"
---
# <a name="scripting-using-external-assemblies"></a><span data-ttu-id="dc438-102">外部アセンブリを使用するスクリプト</span><span class="sxs-lookup"><span data-stu-id="dc438-102">Scripting Using External Assemblies</span></span>
<span data-ttu-id="dc438-103">外部アセンブリを使用したスクリプトは、Microsoft でスクリプトを使用することをお勧め[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="dc438-103">Scripting with external assemblies is the preferred way to use scripting in Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="dc438-104">外部アセンブリは、いくつかの利点を提供します。</span><span class="sxs-lookup"><span data-stu-id="dc438-104">External assemblies provide several advantages:</span></span>  
  
-   <span data-ttu-id="dc438-105">簡単なコードの共有</span><span class="sxs-lookup"><span data-stu-id="dc438-105">Easy code sharing</span></span>  
  
-   <span data-ttu-id="dc438-106">保守が簡単</span><span class="sxs-lookup"><span data-stu-id="dc438-106">Simpler maintenance</span></span>  
  
-   <span data-ttu-id="dc438-107">デバッグの簡略化</span><span class="sxs-lookup"><span data-stu-id="dc438-107">Easier debugging</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dc438-108">場合、マップのテストが失敗した、 **Scripting** functoid は、GAC に登録されていない外部アセンブリを使用します。</span><span class="sxs-lookup"><span data-stu-id="dc438-108">Test Map fails if the **Scripting** functoid uses an external assembly which is not registered in the GAC.</span></span> <span data-ttu-id="dc438-109">場合、外部のアセンブリを (ビルド後に配置されます) 現在のプロジェクトのアセンブリと同じ bin フォルダーで動作します。</span><span class="sxs-lookup"><span data-stu-id="dc438-109">It works if the external assembly is in the same bin folder as the current project's assembly (placed after build).</span></span>  
  
 <span data-ttu-id="dc438-110">設定スクリプトの再利用のみが必要です、**スクリプト**のプロパティ、 **Scripting** functoid。</span><span class="sxs-lookup"><span data-stu-id="dc438-110">Re-using the script only requires setting the **Script** property of the **Scripting** functoid.</span></span> <span data-ttu-id="dc438-111">スクリプトで、マップの外部であるため、マップを変更することがなくスクリプトを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="dc438-111">Because the script is stored outside of the map, you can modify the script without changing the map.</span></span> <span data-ttu-id="dc438-112">すべての配列を使用して[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]デバッグ ツール、スクリプトの確認が正常に実行されます。</span><span class="sxs-lookup"><span data-stu-id="dc438-112">And you can use the full array of [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] debugging tools to ensure your script runs correctly.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="dc438-113">外部アセンブリ内のコードは、スレッド セーフである必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc438-113">The code in the external assembly must be thread-safe.</span></span> <span data-ttu-id="dc438-114">ストレス条件下で、マップの複数のインスタンスを同時に実行される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dc438-114">Under stress conditions, multiple instances of a map may be running concurrently.</span></span>  
  
 <span data-ttu-id="dc438-115">サンプル関数の外部アセンブリに格納されている場合、次を参照してください。 [XML ツール (BizTalk Server Samples フォルダー)](../core/xml-tools-biztalk-server-samples-folder.md)します。</span><span class="sxs-lookup"><span data-stu-id="dc438-115">For a sample function housed in an external assembly, see [XML Tools (BizTalk Server Samples Folder)](../core/xml-tools-biztalk-server-samples-folder.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc438-116">参照</span><span class="sxs-lookup"><span data-stu-id="dc438-116">See Also</span></span>  
 <span data-ttu-id="dc438-117">[スクリプト Functoid](../core/scripting-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="dc438-117">[Scripting Functoid](../core/scripting-functoid.md) </span></span>  
 <span data-ttu-id="dc438-118">[インライン c#、JScript .NET、および Visual Basic .NET を使用するスクリプト](../core/scripting-using-inline-csharp-jscript-net-and-visual-basic-net.md) </span><span class="sxs-lookup"><span data-stu-id="dc438-118">[Scripting Using Inline C#, JScript .NET, and Visual Basic .NET](../core/scripting-using-inline-csharp-jscript-net-and-visual-basic-net.md) </span></span>  
 <span data-ttu-id="dc438-119">[使用してインライン XSLT および XSLT 呼び出しテンプレート スクリプト](../core/scripting-using-inline-xslt-and-xslt-call-templates.md) </span><span class="sxs-lookup"><span data-stu-id="dc438-119">[Scripting Using Inline XSLT and XSLT Call Templates](../core/scripting-using-inline-xslt-and-xslt-call-templates.md) </span></span>  
 <span data-ttu-id="dc438-120">[マップにスクリプト Functoid を追加する方法](../core/how-to-add-scripting-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="dc438-120">[How to Add Scripting Functoids to a Map](../core/how-to-add-scripting-functoids-to-a-map.md) </span></span>  
 [<span data-ttu-id="dc438-121">スクリプト Functoid の構成方法</span><span class="sxs-lookup"><span data-stu-id="dc438-121">How to Configure the Scripting Functoid</span></span>](../core/how-to-configure-the-scripting-functoid.md)