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
ms.openlocfilehash: 8e3e244691d61ef27c55f606414dd08857d58f14
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998155"
---
# <a name="considerations-when-using-orchestration-debugger"></a>オーケストレーション デバッガーを使用する際の考慮事項
オーケストレーション デバッガーを使用して作業するときの考慮事項を次に示します。  
  
## <a name="tracking-atomic-scopes"></a>アトミックのスコープの追跡  
 オーケストレーションには、ルール エンジンへの呼び出しを含むアトミックのスコープを含めることができます。 オーケストレーション デバッガーのインスタンスにアタッチするときに、オーケストレーション インスタンスでのアトミックのスコープに追跡したイベントの一覧に表示するギャップが発生します。 この現象は、次に示す 2 つの理由によって発生します。  
  
- アトミックのトランザクション内部の図形に対するイベントは、スコープによってコミットされるまで保存されない。  
  
- イベントがデバッガーによって一覧の末尾に再度読み込まれるため、ライブ セッションの間はそれらのギャップが残ったままになる。  
  
  表示を更新すると、ギャップがなくなります。  
  
> [!NOTE]
>  アトミックのスコープ内部の図形にはブレークポイントを設定できません。  
  
## <a name="setting-breakpoints-in-the-exception-handler-scope"></a>例外ハンドラーのスコープのブレークポイントの設定  
 ブレークポイントを例外キャッチ ハンドラーに設定する場合、例外の種類を必ずシリアル化可能としてマークするか、設定したブレークポイントでオーケストレーション デバッガーが停止しないようにします。 これは、オーケストレーション デバッガーがブレークポイントで永続化を行うため、オーケストレーション インスタンスの状態にシリアル化できないオブジェクトが存在すると、永続性例外がスローされて、この場合は DebugBreakPointFailedException 例外も発生するためです。  
  
## <a name="tracking-a-modified-orchestration"></a>変更されたオーケストレーションの追跡  
 バージョン番号を変えずに変更されたオーケストレーションを追跡する場合、そのオーケストレーションが参加しているすべてのホスト インスタンスを再起動する必要があります。 これにより、変更を図形をいずれか、新しく展開されたバージョンで正しく表示される、オーケストレーション デバッガーをステップ実行するとします。  
  
## <a name="tracking-simple-types"></a>単純型の追跡  
 オーケストレーション デバッガーでサポートされているのは、単純型のみです。 たとえば、.NET オブジェクトが含まれたマルチパート メッセージを追跡する場合、.NET オブジェクト プロパティを除くすべてのメッセージ部分のプロパティを表示できます。  
  
 オーケストレーションが "ブレークポイント" 状態のときにオーケストレーション デバッガーを起動すると、次の操作を実行できます。  
  
-   使用して、**アタッチ**サービス オプション。  
  
-   既に完了したステップを確認します。  
  
-   変数とメッセージの状態を表示します。  
  
-   追加のブレークポイントを設定します。  
  
-   選択、**サービスの続行**オプション。  
  
-   必要に応じて任意のステップを繰り返します。  
  
## <a name="see-also"></a>参照  
 [オーケストレーション デバッガーの対話モード](../core/interactive-mode-in-orchestration-debugger.md)   
 [オーケストレーションのデバッグ](../core/debugging-an-orchestration.md)