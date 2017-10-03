---
title: "マップのコンパイル |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- maps, compiling
- XSLT, generating
- maps, validating
- BizTalk Mapper, compiling
- BizTalk Mapper, validating
ms.assetid: 967181d6-22a9-4a76-ae45-3317c0c6321b
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 346769519343afe9456a7b1e7cf9a3bd5bb159ac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="compiling-maps"></a><span data-ttu-id="96c0e-102">マップのコンパイル</span><span class="sxs-lookup"><span data-stu-id="96c0e-102">Compiling Maps</span></span>
<span data-ttu-id="96c0e-103">マップを検証すると、BizTalk マッパーのコンパイラ コンポーネントが XSLT (Extensible Stylesheet Language Transformations) スタイルシートを生成します。</span><span class="sxs-lookup"><span data-stu-id="96c0e-103">When you validate maps, the BizTalk Mapper compiler component generates an Extensible Stylesheet Language Transformations (XSLT) style sheet.</span></span> <span data-ttu-id="96c0e-104">これにより、送信元スキーマによって定義されるインスタンス メッセージを送信先スキーマによって定義されるインスタンス メッセージに変換するコンパイル済みのマップが作成されます。</span><span class="sxs-lookup"><span data-stu-id="96c0e-104">This creates a compiled map that transforms an instance message defined by the source schema to an instance message defined by the destination schema.</span></span> <span data-ttu-id="96c0e-105">マップをコンパイルすると、構造上のルールが検証され、グリッド ページで指定されている変換が実行されます。</span><span class="sxs-lookup"><span data-stu-id="96c0e-105">Compiling a map enforces the structural rules and transformations specified in the grid pages.</span></span>  
  
 <span data-ttu-id="96c0e-106">リンクなどの変換は、送信先スキーマのレコードとフィールドの表示順に処理されます。</span><span class="sxs-lookup"><span data-stu-id="96c0e-106">Transformations, such as links, are processed in the same order that records and fields appear in the destination schema.</span></span> <span data-ttu-id="96c0e-107">たとえば、BizTalk マッパーが変換先を達したとき**レコード**または**フィールド**リンクでは、BizTalk マッパーでノードが、リンクのプロパティをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="96c0e-107">For example, when BizTalk Mapper reaches a destination **Record** or **Field** node with a link, BizTalk Mapper compiles the properties of the link.</span></span> <span data-ttu-id="96c0e-108">アクションは、送信元スキーマのレコードまたはフィールドからの単純なコピー値になります。また、Functoid および複数のレコードとフィールドを使用した、さまざまな計算になる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="96c0e-108">The action might be a simple copy value from a record or field in the source schema, or the action might involve multiple calculations using functoids and multiple records and fields.</span></span>  
  
 <span data-ttu-id="96c0e-109">BizTalk マッパーで警告の生成、**出力**ウィンドウと**タスク一覧**コンパイラが不正な出力が生成される状況を検出したときにウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="96c0e-109">BizTalk Mapper generates warnings in the **Output** window and **Task List** window when the compiler encounters a situation that might yield incorrect output.</span></span> <span data-ttu-id="96c0e-110">たとえば、functoid が 1 つの入力パラメーターが必要です、入力パラメーターがない場合は、BizTalk マッパーに警告を生成、**出力**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="96c0e-110">For example, if a functoid requires one input parameter and has no input parameters, BizTalk Mapper generates a warning in the **Output** window.</span></span> <span data-ttu-id="96c0e-111">一般的に、警告が生成された場合は、実稼働環境でそのマップを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="96c0e-111">In general, you should not use a map in a production environment if it is generating warnings.</span></span>  
  
 <span data-ttu-id="96c0e-112">生成された XSLT スタイル シートへのリンクにも表示されます、**出力**マップが正しくコンパイルするときにウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="96c0e-112">A link to the generated XSLT style sheet also appears in the **Output** window when the map compiles correctly.</span></span>  
  
 <span data-ttu-id="96c0e-113">BizTalk Server は、コンパイル済みのマップを使用して、入力インスタンス メッセージを出力インスタンス メッセージに変換します。</span><span class="sxs-lookup"><span data-stu-id="96c0e-113">BizTalk Server uses the compiled map to perform the translation of an input instance message to an output instance message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96c0e-114">参照</span><span class="sxs-lookup"><span data-stu-id="96c0e-114">See Also</span></span>  
 <span data-ttu-id="96c0e-115">[マップのテスト](../core/testing-maps.md) </span><span class="sxs-lookup"><span data-stu-id="96c0e-115">[Testing Maps](../core/testing-maps.md) </span></span>  
 <span data-ttu-id="96c0e-116">[データ変換の構成](../core/data-transformation-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="96c0e-116">[Data Transformation Configuration](../core/data-transformation-configuration.md) </span></span>  
 [<span data-ttu-id="96c0e-117">ノード階層レベルの照合</span><span class="sxs-lookup"><span data-stu-id="96c0e-117">Node-Hierarchy Level Matching</span></span>](../core/node-hierarchy-level-matching.md)