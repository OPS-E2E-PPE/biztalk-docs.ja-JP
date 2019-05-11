---
title: オーケストレーションのデバッグ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- debugging, Orchestration Debugger
- debugging, orchestrations
- Orchestration Debugger, about Orchestration Debugger
- Orchestrations Debugger
- orchestrations, debugging
- debugging, HAT
- HAT, debugging
ms.assetid: aae99cfd-d3dd-41c8-ae7a-b2733352cd69
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b0e1ad8529e3f91f5b34ad60585677892989368
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390438"
---
# <a name="debugging-an-orchestration"></a>オーケストレーションのデバッグ
オーケストレーション デバッガーを使用すると、単一のオーケストレーション インスタンスのアクティビティを図形ごとに追跡できます。 これにより、オーケストレーション デザイナーで作成されたオーケストレーションの描画されたビューが表示されます。  
  
 オーケストレーション デバッガーには、BizTalk Server 管理コンソールの [グループの概要] ページでアクセスします。  それには、追跡クエリの出力から、オーケストレーションの種類に関連付けられたサービスまたはメッセージ インスタンスを右クリックして表示されるショートカット メニューにより行います。 このページで、オーケストレーション デバッガーとメッセージ フロー ビューを切り替えることができます。  
  
 オーケストレーション デバッガーには、次の機能があります。  
  
- 特定のオーケストレーションの各処理手順を再生できる、そのオーケストレーションの描画されたビューを表示します。  
  
- オーケストレーション図形の前にブレークポイントを設定して実行を続行できます。  
  
- 特定の変数およびメッセージ データを参照できます。  
  
- 特定のオーケストレーション インスタンスがオーケストレーション デバッガーで開かれるときにそのインスタンスのすべての追跡オプションを自動的に有効にします。  
  
- 特定のオーケストレーション インスタンスを、デバッグ モードで続行、再開、および終了することができます。  
  
  > [!NOTE]
  >  アセンブリの展開を解除すると、データベースには、展開を解除されたアセンブリの追跡オプションおよびブレークポイント情報が格納されます。 その後、同じアセンブリを展開すると、そのアセンブリのオプションおよびブレークポイント情報が復元されます。  
  
  オーケストレーション デバッガーは、次の 2 つのモードで使用できます。  
  
- [オーケストレーション デバッガーの報告モード](../core/reporting-mode-in-orchestration-debugger.md)  
  
- [オーケストレーション デバッガーの対話モード](../core/interactive-mode-in-orchestration-debugger.md)  
  
  機能は、サービスの状態によって異なります。 対話形式のデバッグを実行するには、現在 "ブレークポイント" 状態のサービス インスタンスを、任意のビューから呼び出します。 オーケストレーションのデバッグについては、次を参照してください。[オーケストレーション デバッガーとメッセージ フロー ビューを呼び出す方法](../core/how-to-invoke-the-orchestration-debugger-and-the-message-flow-views.md)します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [オーケストレーション デバッガーのユーザー インターフェイス](../core/orchestration-debugger-user-interface.md)  
  
-   [オーケストレーション デバッガーを使用する際の考慮事項](../core/considerations-when-using-orchestration-debugger.md)  
  
-   [オーケストレーション デバッガー ビューの操作](../core/working-with-the-orchestration-debugger-view.md)