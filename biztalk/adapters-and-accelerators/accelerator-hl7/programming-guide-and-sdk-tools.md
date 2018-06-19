---
title: プログラミング ガイド、および SDK ツール |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- documentation, tips
- BTAHL7, developing
- developing
ms.assetid: 040ba1b6-d0bf-4477-a564-20e18231aee7
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ef9ffdaaeb0b8a2506e86ff8efc22a90f96a520
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206162"
---
# <a name="programming-guide-and-sdk-tools"></a><span data-ttu-id="96b7f-102">プログラミング ガイドと SDK ツール</span><span class="sxs-lookup"><span data-stu-id="96b7f-102">Programming guide and SDK tools</span></span>
<span data-ttu-id="96b7f-103">このソフトウェア開発キット (SDK) のツールを使用してアプリケーションを開発する開発者向けの情報を提供する[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]、パブリック アプリケーション プログラミング インターフェイス (API)、または提供されたサンプルおよびユーティリティ、BTAHL7 SDK。</span><span class="sxs-lookup"><span data-stu-id="96b7f-103">This Software Development Kit (SDK) provides information for developers who are creating applications using any of the tools in [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)], the public application programming interfaces (API), or the samples and utilities provided in the BTAHL7 SDK.</span></span>  
  
## <a name="tips-for-using-help-in-a-developer-environment"></a><span data-ttu-id="96b7f-104">開発環境でヘルプの使用に関するヒント</span><span class="sxs-lookup"><span data-stu-id="96b7f-104">Tips for using Help in a developer environment</span></span>  
 <span data-ttu-id="96b7f-105">BTAHL7 ヘルプには、BTAHL7 のヘルプし、Visual Studio のヘルプの間のリンクを任意の言語で開発者ドキュメントを表示に使用できる機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="96b7f-105">BTAHL7 Help contains features that you can use to display the developer documentation in your preferred language and to link between BTAHL7 Help and Visual Studio Help.</span></span>  
  
### <a name="using-language-filtering"></a><span data-ttu-id="96b7f-106">言語のフィルターを使用します。</span><span class="sxs-lookup"><span data-stu-id="96b7f-106">Using language filtering</span></span>  
 <span data-ttu-id="96b7f-107">BTAHL7[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]クラスのリファレンスでは、署名と複数のプログラミング言語のコード例です。</span><span class="sxs-lookup"><span data-stu-id="96b7f-107">The BTAHL7 [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] Class Reference provides signatures and code examples in multiple programming languages.</span></span> <span data-ttu-id="96b7f-108">次のタグは、言語固有の情報を示すため。</span><span class="sxs-lookup"><span data-stu-id="96b7f-108">The following tags denote the language-specific information:</span></span>  
  
 <span data-ttu-id="96b7f-109">**[** [!INCLUDE[btsCSharp](../../includes/btscsharp-md.md)] **]**</span><span class="sxs-lookup"><span data-stu-id="96b7f-109">**[** [!INCLUDE[btsCSharp](../../includes/btscsharp-md.md)] **]**</span></span>  
  
 <span data-ttu-id="96b7f-110">**[** [!INCLUDE[btsVBNoVersion](../../includes/btsvbnoversion-md.md)] **]**</span><span class="sxs-lookup"><span data-stu-id="96b7f-110">**[** [!INCLUDE[btsVBNoVersion](../../includes/btsvbnoversion-md.md)] **]**</span></span>  
  
 <span data-ttu-id="96b7f-111">**[C++]**</span><span class="sxs-lookup"><span data-stu-id="96b7f-111">**[C++]**</span></span>  
  
 <span data-ttu-id="96b7f-112">**[** [!INCLUDE[btsJScript](../../includes/btsjscript-md.md)] **]**</span><span class="sxs-lookup"><span data-stu-id="96b7f-112">**[** [!INCLUDE[btsJScript](../../includes/btsjscript-md.md)] **]**</span></span>  
  
 <span data-ttu-id="96b7f-113">リファレンス ページのコンテンツのビューをカスタマイズして、希望するプログラミング言語の情報だけを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="96b7f-113">You can customize your view of the content in the reference pages to display only information in your preferred programming language.</span></span> <span data-ttu-id="96b7f-114">カスタム言語を選択するには、**言語のフィルター**このページの左上隅にあるボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="96b7f-114">To select a custom language, use the **Language Filter** button in the upper-left corner of this page.</span></span> <span data-ttu-id="96b7f-115">有効にした場合は言語のフィルター処理が変更されるまで保持されます。</span><span class="sxs-lookup"><span data-stu-id="96b7f-115">Once enabled, language filtering persists until it is changed.</span></span> <span data-ttu-id="96b7f-116">言語フィルターが有効な場合は、ページ上部の青いバーのタイトルの後に、選択している言語の名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="96b7f-116">You can see that language filtering is enabled on a page, because the name of the language follows the title in the blue bar at the top of the page.</span></span>  
  
### <a name="linking-between-btahl7-help-and-microsoft-visual-studio-help"></a><span data-ttu-id="96b7f-117">BTAHL7 ヘルプおよび Microsoft Visual Studio ヘルプ間のリンク</span><span class="sxs-lookup"><span data-stu-id="96b7f-117">Linking between BTAHL7 Help and Microsoft Visual Studio Help</span></span>  
 <span data-ttu-id="96b7f-118">メンバーを継承する場合、[!INCLUDE[btsDotNetFramework](../../includes/btsdotnetframework-md.md)]基底クラス ライブラリでは、2 つのリンクが提供される、次の例で示すようにします。</span><span class="sxs-lookup"><span data-stu-id="96b7f-118">When a member is inherited from the [!INCLUDE[btsDotNetFramework](../../includes/btsdotnetframework-md.md)] Base Class Library, two links are provided, as shown in the following example:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="96b7f-119">![](../../adapters-and-accelerators/accelerator-hl7/media/protmethod.gif "protmethod")最終処理 (から継承された**System.Object**)</span><span class="sxs-lookup"><span data-stu-id="96b7f-119">![](../../adapters-and-accelerators/accelerator-hl7/media/protmethod.gif "protmethod") Finalize (inherited from **System.Object**)</span></span>|<span data-ttu-id="96b7f-120">システム名前空間に関する詳細については、次を参照してください。[システム Namespace クラス](https://msdn.microsoft.com/library/system(v=vs.110).aspx)です。</span><span class="sxs-lookup"><span data-stu-id="96b7f-120">For additional information about the System namespace, see [System Namespace class](https://msdn.microsoft.com/library/system(v=vs.110).aspx).</span></span>|  
  
 <span data-ttu-id="96b7f-121">BTAHL7 でを表示している場合[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]または、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]ドキュメントについては、左の列にリンク、正確なメンバー ページに進みます。</span><span class="sxs-lookup"><span data-stu-id="96b7f-121">If you are viewing BTAHL7 in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] or in the [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] documentation, the link in the left column goes to the exact member page.</span></span> <span data-ttu-id="96b7f-122">BTAHL7 が外部のヘルプを表示している場合[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、右側の列のリンクを使用して、MSDN ライブラリの System 名前空間 ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="96b7f-122">If you are viewing BTAHL7 Help outside of [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], use the link in the right column to go to the System namespace page in the MSDN Library.</span></span> <span data-ttu-id="96b7f-123">リンクは特定のメンバーのページに移動していないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="96b7f-123">Note that the link will not go to the specific member page.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="96b7f-124">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="96b7f-124">In This Section</span></span>  
  
-   [<span data-ttu-id="96b7f-125">プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="96b7f-125">Programming Guide</span></span>](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md)  
  
-   [<span data-ttu-id="96b7f-126">ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="96b7f-126">Utilities</span></span>](../../adapters-and-accelerators/accelerator-hl7/utilities2.md)