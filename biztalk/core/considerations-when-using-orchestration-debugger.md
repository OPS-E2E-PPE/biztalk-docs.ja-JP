---
title: "オーケストレーション デバッガーを使用する際の考慮事項 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2815da55bc74d822cb5fe2540347855db75b3a8b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="considerations-when-using-orchestration-debugger"></a><span data-ttu-id="6fba9-102">オーケストレーション デバッガーを使用する際の考慮事項</span><span class="sxs-lookup"><span data-stu-id="6fba9-102">Considerations when Using Orchestration Debugger</span></span>
<span data-ttu-id="6fba9-103">オーケストレーション デバッガーを使用して作業するときの考慮事項を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6fba9-103">Following are some things to consider when you work with the Orchestration Debugger.</span></span>  
  
## <a name="tracking-atomic-scopes"></a><span data-ttu-id="6fba9-104">アトミックのスコープの追跡</span><span class="sxs-lookup"><span data-stu-id="6fba9-104">Tracking atomic scopes</span></span>  
 <span data-ttu-id="6fba9-105">オーケストレーションには、ルール エンジンへの呼び出しを含むアトミックのスコープを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="6fba9-105">An orchestration can contain atomic scopes to include calls to the Rule Engine.</span></span> <span data-ttu-id="6fba9-106">オーケストレーション デバッガーのインスタンスにアタッチしているアトミックのスコープがオーケストレーション インスタンスの追跡イベントの一覧に表示するギャップが発生します。</span><span class="sxs-lookup"><span data-stu-id="6fba9-106">When you attach to an instance in the orchestration debugger, any atomic scopes in the orchestration instance will cause gaps to appear in the tracked events list.</span></span> <span data-ttu-id="6fba9-107">この現象は、次に示す 2 つの理由によって発生します。</span><span class="sxs-lookup"><span data-stu-id="6fba9-107">This happens for two reasons:</span></span>  
  
-   <span data-ttu-id="6fba9-108">アトミックのトランザクション内部の図形に対するイベントは、スコープによってコミットされるまで保存されない。</span><span class="sxs-lookup"><span data-stu-id="6fba9-108">Because events for the shapes inside atomic transactions do not get persisted until the scope commits</span></span>  
  
-   <span data-ttu-id="6fba9-109">イベントがデバッガーによって一覧の末尾に再度読み込まれるため、ライブ セッションの間はそれらのギャップが残ったままになる。</span><span class="sxs-lookup"><span data-stu-id="6fba9-109">The debugger reloads events onto the end of the list, so any gaps remain unfilled during the live session.</span></span>  
  
 <span data-ttu-id="6fba9-110">表示を更新すると、ギャップがなくなります。</span><span class="sxs-lookup"><span data-stu-id="6fba9-110">You can eliminate the gaps if you refresh the view.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6fba9-111">アトミックのスコープ内部の図形にはブレークポイントを設定できません。</span><span class="sxs-lookup"><span data-stu-id="6fba9-111">You cannot set a breakpoint on shapes inside an atomic scope.</span></span>  
  
## <a name="setting-breakpoints-in-the-exception-handler-scope"></a><span data-ttu-id="6fba9-112">例外ハンドラーのスコープのブレークポイントの設定</span><span class="sxs-lookup"><span data-stu-id="6fba9-112">Setting breakpoints in the exception handler scope</span></span>  
 <span data-ttu-id="6fba9-113">ブレークポイントを例外キャッチ ハンドラーに設定する場合、例外の種類を必ずシリアル化可能としてマークするか、設定したブレークポイントでオーケストレーション デバッガーが停止しないようにします。</span><span class="sxs-lookup"><span data-stu-id="6fba9-113">If the breakpoint is set at the exception catch handler, the exception types must be marked as serializable, or the orchestration debugger will not stop at the breakpoints you set.</span></span> <span data-ttu-id="6fba9-114">これは、オーケストレーション デバッガーがブレークポイントで永続化を行うため、オーケストレーション インスタンスの状態にシリアル化できないオブジェクトが存在すると、永続性例外がスローされて、この場合は DebugBreakPointFailedException 例外も発生するためです。</span><span class="sxs-lookup"><span data-stu-id="6fba9-114">This is because of that the orchestration debugger does persistence at the breakpoint, therefore, when there is a non-serializable object in the orchestration instance state, a persistence exception will be thrown, and in this case, you will also receive a DebugBreakPointFailedException exception.</span></span>  
  
## <a name="tracking-a-modified-orchestration"></a><span data-ttu-id="6fba9-115">変更されたオーケストレーションの追跡</span><span class="sxs-lookup"><span data-stu-id="6fba9-115">Tracking a modified orchestration</span></span>  
 <span data-ttu-id="6fba9-116">バージョン番号を変えずに変更されたオーケストレーションを追跡する場合、そのオーケストレーションが参加しているすべてのホスト インスタンスを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fba9-116">If you track an orchestration modified without changing the version number, you must restart all the host instances to which the orchestration is enlisted.</span></span> <span data-ttu-id="6fba9-117">これにより、変更を図形いずれか、新しく展開されたバージョンで正しく表示される、オーケストレーション デバッガーをステップ実行するとします。</span><span class="sxs-lookup"><span data-stu-id="6fba9-117">This insures that any shape change in the newly deployed version displays correctly, as you step through the Orchestration Debugger.</span></span>  
  
## <a name="tracking-simple-types"></a><span data-ttu-id="6fba9-118">単純型の追跡</span><span class="sxs-lookup"><span data-stu-id="6fba9-118">Tracking simple types</span></span>  
 <span data-ttu-id="6fba9-119">オーケストレーション デバッガーでサポートされているのは、単純型のみです。</span><span class="sxs-lookup"><span data-stu-id="6fba9-119">The Orchestration Debugger only supports simple types.</span></span> <span data-ttu-id="6fba9-120">たとえば、.NET オブジェクトが含まれたマルチパート メッセージを追跡する場合、.NET オブジェクト プロパティを除くすべてのメッセージ部分のプロパティを表示できます。</span><span class="sxs-lookup"><span data-stu-id="6fba9-120">For example, if you track a multipart message that contains a .NET object you can view the properties of all message parts, with the exception of the .NET object properties.</span></span>  
  
 <span data-ttu-id="6fba9-121">オーケストレーションが "ブレークポイント" 状態のときにオーケストレーション デバッガーを起動すると、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="6fba9-121">When an orchestration appears in the In Breakpoint state and the Orchestration Debugger starts, you can perform the following actions:</span></span>  
  
-   <span data-ttu-id="6fba9-122">使用して、**アタッチ**サービス オプション。</span><span class="sxs-lookup"><span data-stu-id="6fba9-122">Use the **Attach** service option.</span></span>  
  
-   <span data-ttu-id="6fba9-123">既に完了したステップを確認します。</span><span class="sxs-lookup"><span data-stu-id="6fba9-123">Review the steps that have already completed.</span></span>  
  
-   <span data-ttu-id="6fba9-124">変数とメッセージの状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="6fba9-124">View the state of variables and messages.</span></span>  
  
-   <span data-ttu-id="6fba9-125">追加のブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="6fba9-125">Set additional breakpoints.</span></span>  
  
-   <span data-ttu-id="6fba9-126">選択、**サービスの続行**オプション。</span><span class="sxs-lookup"><span data-stu-id="6fba9-126">Select the **Continue Service** option.</span></span>  
  
-   <span data-ttu-id="6fba9-127">必要に応じて任意のステップを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="6fba9-127">Repeat any steps as required.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fba9-128">参照</span><span class="sxs-lookup"><span data-stu-id="6fba9-128">See Also</span></span>  
 <span data-ttu-id="6fba9-129">[オーケストレーション デバッガーの対話モード](../core/interactive-mode-in-orchestration-debugger.md) </span><span class="sxs-lookup"><span data-stu-id="6fba9-129">[Interactive Mode in Orchestration Debugger](../core/interactive-mode-in-orchestration-debugger.md) </span></span>  
 [<span data-ttu-id="6fba9-130">オーケストレーションのデバッグ</span><span class="sxs-lookup"><span data-stu-id="6fba9-130">Debugging an Orchestration</span></span>](../core/debugging-an-orchestration.md)