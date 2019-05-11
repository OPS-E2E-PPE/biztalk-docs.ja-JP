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
# <a name="considerations-when-using-orchestration-debugger"></a>オーケストレーション デバッガーを使用する場合の考慮事項
オーケストレーション デバッガーを使用する場合の考慮事項を次に示します。  
  
## <a name="tracking-atomic-scopes"></a>アトミックのスコープの追跡  
 オーケストレーションは、ルール エンジンの呼び出しを含めるにアトミックのスコープを含めることができます。 オーケストレーション デバッガーのインスタンスにアタッチするときに、オーケストレーション インスタンスでのアトミックのスコープに追跡したイベントの一覧に表示するギャップが発生します。 これは、2 つの理由が発生します。  
  
- スコープがコミットされるまでアトミック トランザクション内部の図形に対するイベントは保存されないため、  
  
- デバッガーは、ライブ セッションの間にギャップが塗りつぶされていない残ったままに、リストの末尾にイベントを再読み込みします。  
  
  表示を更新する場合は、ギャップを解消できます。  
  
> [!NOTE]
>  アトミックのスコープ内部の図形にブレークポイントを設定することはできません。  
  
## <a name="setting-breakpoints-in-the-exception-handler-scope"></a>例外ハンドラーのスコープにブレークポイントを設定  
 例外キャッチ ハンドラーにブレークポイントが設定されている場合、例外の種類は、シリアル化可能としてマークする必要があります。 またはオーケストレーション デバッガーは設定したブレークポイントで停止されません。 これはのため、オーケストレーション デバッガーでは、ブレークポイントで永続化そのため、オーケストレーション インスタンスの状態にシリアル化できないオブジェクトが、永続化例外がスローされ、この場合も受け取ります、DebugBreakPointFailedException 例外。  
  
## <a name="tracking-a-modified-orchestration"></a>変更されたオーケストレーションの追跡  
 バージョン番号を変更せずに変更されたオーケストレーションを追跡する場合は、オーケストレーションが参加しているすべてのホスト インスタンスを再起動する必要があります。 これにより、変更を図形をいずれか、新しく展開されたバージョンで正しく表示される、オーケストレーション デバッガーをステップ実行するとします。  
  
## <a name="tracking-simple-types"></a>単純型の追跡  
 オーケストレーション デバッガーは、単純型のみをサポートします。 たとえば、.NET オブジェクトを含むマルチパート メッセージを追跡する場合は、.NET オブジェクトのプロパティを除く、すべてのメッセージ部分のプロパティを表示できます。  
  
 開始のブレークポイントの状態とオーケストレーション デバッガーでオーケストレーションが表示されたら、次の操作を実行できます。  
  
-   使用して、**アタッチ**サービス オプション。  
  
-   既に完了した手順を確認します。  
  
-   変数およびメッセージの状態を表示します。  
  
-   追加のブレークポイントを設定します。  
  
-   選択、**サービスの続行**オプション。  
  
-   必要に応じて任意の手順を繰り返します。  
  
## <a name="see-also"></a>参照  
 [オーケストレーション デバッガーの対話モード](../core/interactive-mode-in-orchestration-debugger.md)   
 [オーケストレーションのデバッグ](../core/debugging-an-orchestration.md)