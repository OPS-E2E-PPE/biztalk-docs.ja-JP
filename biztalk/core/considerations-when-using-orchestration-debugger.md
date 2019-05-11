---
title: オーケストレーション デバッガーを使用する場合の考慮事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Orchestration Debugger, modified orchestrations
- Orchestration Debugger, planning
- atomic scopes
- planning, Orchestration Debugger
- Orchestration Debugger, atomic scopes
- Orchestration Debugger, simple types
- orchestrations, modifying
ms.assetid: 55bfef48-08bd-48bb-abd5-7264e683da46
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2457489bf5605b281b450f9c51df8b9fb21fab5e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390311"
---
# <a name="considerations-when-using-orchestration-debugger"></a><span data-ttu-id="bf9aa-102">オーケストレーション デバッガーを使用する場合の考慮事項</span><span class="sxs-lookup"><span data-stu-id="bf9aa-102">Considerations when Using Orchestration Debugger</span></span>
<span data-ttu-id="bf9aa-103">オーケストレーション デバッガーを使用する場合の考慮事項を次に示します。</span><span class="sxs-lookup"><span data-stu-id="bf9aa-103">Following are some things to consider when you work with the Orchestration Debugger.</span></span>  
  
## <a name="tracking-atomic-scopes"></a><span data-ttu-id="bf9aa-104">アトミックのスコープの追跡</span><span class="sxs-lookup"><span data-stu-id="bf9aa-104">Tracking atomic scopes</span></span>  
 <span data-ttu-id="bf9aa-105">オーケストレーションは、ルール エンジンの呼び出しを含めるにアトミックのスコープを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="bf9aa-105">An orchestration can contain atomic scopes to include calls to the Rule Engine.</span></span> <span data-ttu-id="bf9aa-106">オーケストレーション デバッガーのインスタンスにアタッチするときに、オーケストレーション インスタンスでのアトミックのスコープに追跡したイベントの一覧に表示するギャップが発生します。</span><span class="sxs-lookup"><span data-stu-id="bf9aa-106">When you attach to an instance in the orchestration debugger, any atomic scopes in the orchestration instance will cause gaps to appear in the tracked events list.</span></span> <span data-ttu-id="bf9aa-107">これは、2 つの理由が発生します。</span><span class="sxs-lookup"><span data-stu-id="bf9aa-107">This happens for two reasons:</span></span>  
  
- <span data-ttu-id="bf9aa-108">スコープがコミットされるまでアトミック トランザクション内部の図形に対するイベントは保存されないため、</span><span class="sxs-lookup"><span data-stu-id="bf9aa-108">Because events for the shapes inside atomic transactions do not get persisted until the scope commits</span></span>  
  
- <span data-ttu-id="bf9aa-109">デバッガーは、ライブ セッションの間にギャップが塗りつぶされていない残ったままに、リストの末尾にイベントを再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="bf9aa-109">The debugger reloads events onto the end of the list, so any gaps remain unfilled during the live session.</span></span>  
  
  <span data-ttu-id="bf9aa-110">表示を更新する場合は、ギャップを解消できます。</span><span class="sxs-lookup"><span data-stu-id="bf9aa-110">You can eliminate the gaps if you refresh the view.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bf9aa-111">アトミックのスコープ内部の図形にブレークポイントを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="bf9aa-111">You cannot set a breakpoint on shapes inside an atomic scope.</span></span>  
  
## <a name="setting-breakpoints-in-the-exception-handler-scope"></a><span data-ttu-id="bf9aa-112">例外ハンドラーのスコープにブレークポイントを設定</span><span class="sxs-lookup"><span data-stu-id="bf9aa-112">Setting breakpoints in the exception handler scope</span></span>  
 <span data-ttu-id="bf9aa-113">例外キャッチ ハンドラーにブレークポイントが設定されている場合、例外の種類は、シリアル化可能としてマークする必要があります。 またはオーケストレーション デバッガーは設定したブレークポイントで停止されません。</span><span class="sxs-lookup"><span data-stu-id="bf9aa-113">If the breakpoint is set at the exception catch handler, the exception types must be marked as serializable, or the orchestration debugger will not stop at the breakpoints you set.</span></span> <span data-ttu-id="bf9aa-114">これはのため、オーケストレーション デバッガーでは、ブレークポイントで永続化そのため、オーケストレーション インスタンスの状態にシリアル化できないオブジェクトが、永続化例外がスローされ、この場合も受け取ります、DebugBreakPointFailedException 例外。</span><span class="sxs-lookup"><span data-stu-id="bf9aa-114">This is because of that the orchestration debugger does persistence at the breakpoint, therefore, when there is a non-serializable object in the orchestration instance state, a persistence exception will be thrown, and in this case, you will also receive a DebugBreakPointFailedException exception.</span></span>  
  
## <a name="tracking-a-modified-orchestration"></a><span data-ttu-id="bf9aa-115">変更されたオーケストレーションの追跡</span><span class="sxs-lookup"><span data-stu-id="bf9aa-115">Tracking a modified orchestration</span></span>  
 <span data-ttu-id="bf9aa-116">バージョン番号を変更せずに変更されたオーケストレーションを追跡する場合は、オーケストレーションが参加しているすべてのホスト インスタンスを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf9aa-116">If you track an orchestration modified without changing the version number, you must restart all the host instances to which the orchestration is enlisted.</span></span> <span data-ttu-id="bf9aa-117">これにより、変更を図形をいずれか、新しく展開されたバージョンで正しく表示される、オーケストレーション デバッガーをステップ実行するとします。</span><span class="sxs-lookup"><span data-stu-id="bf9aa-117">This insures that any shape change in the newly deployed version displays correctly, as you step through the Orchestration Debugger.</span></span>  
  
## <a name="tracking-simple-types"></a><span data-ttu-id="bf9aa-118">単純型の追跡</span><span class="sxs-lookup"><span data-stu-id="bf9aa-118">Tracking simple types</span></span>  
 <span data-ttu-id="bf9aa-119">オーケストレーション デバッガーは、単純型のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="bf9aa-119">The Orchestration Debugger only supports simple types.</span></span> <span data-ttu-id="bf9aa-120">たとえば、.NET オブジェクトを含むマルチパート メッセージを追跡する場合は、.NET オブジェクトのプロパティを除く、すべてのメッセージ部分のプロパティを表示できます。</span><span class="sxs-lookup"><span data-stu-id="bf9aa-120">For example, if you track a multipart message that contains a .NET object you can view the properties of all message parts, with the exception of the .NET object properties.</span></span>  
  
 <span data-ttu-id="bf9aa-121">開始のブレークポイントの状態とオーケストレーション デバッガーでオーケストレーションが表示されたら、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="bf9aa-121">When an orchestration appears in the In Breakpoint state and the Orchestration Debugger starts, you can perform the following actions:</span></span>  
  
-   <span data-ttu-id="bf9aa-122">使用して、**アタッチ**サービス オプション。</span><span class="sxs-lookup"><span data-stu-id="bf9aa-122">Use the **Attach** service option.</span></span>  
  
-   <span data-ttu-id="bf9aa-123">既に完了した手順を確認します。</span><span class="sxs-lookup"><span data-stu-id="bf9aa-123">Review the steps that have already completed.</span></span>  
  
-   <span data-ttu-id="bf9aa-124">変数およびメッセージの状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="bf9aa-124">View the state of variables and messages.</span></span>  
  
-   <span data-ttu-id="bf9aa-125">追加のブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="bf9aa-125">Set additional breakpoints.</span></span>  
  
-   <span data-ttu-id="bf9aa-126">選択、**サービスの続行**オプション。</span><span class="sxs-lookup"><span data-stu-id="bf9aa-126">Select the **Continue Service** option.</span></span>  
  
-   <span data-ttu-id="bf9aa-127">必要に応じて任意の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="bf9aa-127">Repeat any steps as required.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf9aa-128">参照</span><span class="sxs-lookup"><span data-stu-id="bf9aa-128">See Also</span></span>  
 <span data-ttu-id="bf9aa-129">[オーケストレーション デバッガーの対話モード](../core/interactive-mode-in-orchestration-debugger.md) </span><span class="sxs-lookup"><span data-stu-id="bf9aa-129">[Interactive Mode in Orchestration Debugger](../core/interactive-mode-in-orchestration-debugger.md) </span></span>  
 [<span data-ttu-id="bf9aa-130">オーケストレーションのデバッグ</span><span class="sxs-lookup"><span data-stu-id="bf9aa-130">Debugging an Orchestration</span></span>](../core/debugging-an-orchestration.md)