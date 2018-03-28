---
title: 式の要件と制限 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Expression Editor, about Expression Editor
- Expression Editor, requirements
- Orchestration Designer, Expression Editor
- Expression Editor, limitations
- Expression Editor
- Expression Editor, Orchestration Designer
ms.assetid: 1e0353d3-c2f3-4c10-86e3-8620e62dd0d5
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd819850f62d47c640753e843325c9851da177b5
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="requirements-and-limitations-for-expressions"></a><span data-ttu-id="07c42-102">式の要件と制限事項</span><span class="sxs-lookup"><span data-stu-id="07c42-102">Requirements and Limitations for Expressions</span></span>
<span data-ttu-id="07c42-103">オーケストレーション デザイナーの BizTalk 式エディターは、IntelliSense を備えた標準の Visual Studio テキスト エディターです。</span><span class="sxs-lookup"><span data-stu-id="07c42-103">BizTalk Expression Editor in Orchestration Designer is a standard Visual Studio text editor, which means it offers IntelliSense.</span></span> <span data-ttu-id="07c42-104">BizTalk 式エディターは、テキスト形式で式を入力するために使用します。</span><span class="sxs-lookup"><span data-stu-id="07c42-104">You use BizTalk Expression Editor to enter an expression in textual form.</span></span>  
  
 <span data-ttu-id="07c42-105">テキスト形式で 1 つの式を入力するには、テキスト ボックスを使用します。</span><span class="sxs-lookup"><span data-stu-id="07c42-105">Use the text box to enter a single expression in textual form.</span></span> <span data-ttu-id="07c42-106">1 つの式を複数行に記述できますが、行を 1 つのセミコロンで終了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07c42-106">The expression can span multiple lines, but must end with single semicolon.</span></span>  
  
 <span data-ttu-id="07c42-107">以下は、BizTalk 式エディターで式を使用するときの制限事項の一覧です。</span><span class="sxs-lookup"><span data-stu-id="07c42-107">The following is a list of limitations when using expressions in the BizTalk Expression Editor:</span></span>  
  
-   <span data-ttu-id="07c42-108">"+="、"-="、"\*=" などの複合代入はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="07c42-108">Compound assignment such as "+=", "-=", or "\*=" is not supported.</span></span>  
  
-   <span data-ttu-id="07c42-109">1 つのステートメントでの複数の代入演算子の使用は、サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="07c42-109">More than one assignment operator in a statement is not supported.</span></span>  
  
-   <span data-ttu-id="07c42-110">"if" または "while" の述語内での代入は、サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="07c42-110">Assignment within an “if” or “while” predicate is not supported.</span></span>  
  
-   <span data-ttu-id="07c42-111">インクリメントおよびデクリメントはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="07c42-111">Increment and decrement are not supported.</span></span> <span data-ttu-id="07c42-112">たとえば、"++" や "--" などです。</span><span class="sxs-lookup"><span data-stu-id="07c42-112">For example, "++" and "--".</span></span>  
  
-   <span data-ttu-id="07c42-113">メッセージ部分の場合、パブリック メソッド、入れ子になっている型、静的データ フィールド、Microsoft.XLANGs.BaseTypes.DistinguishedFieldAttribute によって注釈が付けられた読み取り専用の .NET プロパティ、すべてのパブリック データ フィールド、および読み取り専用ではない .NET プロパティについては、メンバー アクセスが許可されます。</span><span class="sxs-lookup"><span data-stu-id="07c42-113">For message parts, member access is allowed on public methods, nested types, static data fields, read-only .NET properties when annotated with Microsoft.XLANGs.BaseTypes.DistinguishedFieldAttribute, all public data fields, and non-read-only .NET properties.</span></span>  
  
-   <span data-ttu-id="07c42-114">インデクサーまたはパラメーター化された .NET プロパティはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="07c42-114">Indexers or parameterized .NET properties are not supported.</span></span>  
  
-   <span data-ttu-id="07c42-115">デリゲートおよびイベントはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="07c42-115">Delegates and events are not supported.</span></span>  
  
-   <span data-ttu-id="07c42-116">ジェネリックはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="07c42-116">Generics are not supported.</span></span>  
  
-   <span data-ttu-id="07c42-117">"foreach"、"for"、"do-while"、"break"、"continue" などのフロー制御構文は、サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="07c42-117">Flow control syntax such as "foreach", "for", "do-while", "break", and "continue" are not supported.</span></span>  
  
-   <span data-ttu-id="07c42-118">三項演算はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="07c42-118">Ternary operations are not supported.</span></span> <span data-ttu-id="07c42-119">たとえば、"?:" などです。</span><span class="sxs-lookup"><span data-stu-id="07c42-119">For example, "?:".</span></span>  
  
-   <span data-ttu-id="07c42-120">式図形にコメントを追加できますが、式図形には少なくとも 1 つのステートメントが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="07c42-120">You can add comments in the Expression shape, but the Expression shape must contain at least one statement.</span></span>  
  
-   <span data-ttu-id="07c42-121">配列はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="07c42-121">Arrays are not supported.</span></span>  
  
-   <span data-ttu-id="07c42-122">式図形をメッセージの構築図形の中に配置するときは、制御フローを実行できません。</span><span class="sxs-lookup"><span data-stu-id="07c42-122">When the Expression shape is placed in a Construct Message shape, you cannot do any control flow.</span></span> <span data-ttu-id="07c42-123">たとえば、"if-then-else" や "while" などです。</span><span class="sxs-lookup"><span data-stu-id="07c42-123">For example, "if-then-else" or "while".</span></span>  
  
-   <span data-ttu-id="07c42-124">すべての有効な式ステートメントの形式は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="07c42-124">All valid expression statements are of the form:</span></span>  
  
    -   <span data-ttu-id="07c42-125">ドット形式の名前 = 式;</span><span class="sxs-lookup"><span data-stu-id="07c42-125">Dotted-name = expression;</span></span>  
  
    -   <span data-ttu-id="07c42-126">ドット形式の名前 = 式;</span><span class="sxs-lookup"><span data-stu-id="07c42-126">Dotted-name = expression;</span></span>  
  
 <span data-ttu-id="07c42-127">BizTalk 式エディターを使用すると複雑な式を簡単かつすばやく入力できますが、任意の大きさのコードを入力することはできません。</span><span class="sxs-lookup"><span data-stu-id="07c42-127">Though you can use BizTalk Expression Editor to enter complex expressions easily and quickly, you cannot use it to enter an arbitrary amount of code.</span></span> <span data-ttu-id="07c42-128">これは、ビジネス プロセスのコードを実装コードから分離しておくためです。</span><span class="sxs-lookup"><span data-stu-id="07c42-128">The reason for this is to keep code for the business process separate from its implementation code.</span></span>