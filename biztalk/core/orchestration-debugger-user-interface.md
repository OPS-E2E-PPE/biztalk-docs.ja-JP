---
title: オーケストレーション デバッガーのユーザー インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.hat.orchdebugger
helpviewer_keywords:
- Orchestration Debugger, debug mode
- Orchestration Debugger, Interactive mode
ms.assetid: ca18f1e2-63b7-4177-82ba-4accc3369a2a
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d7c7292a5f6874752b3e10031af93d86063afbc5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262806"
---
# <a name="orchestration-debugger-user-interface"></a>オーケストレーション デバッガーのユーザー インターフェイス
対話型 (デバッグ) モードでは、オーケストレーション デバッガー ビューには、3 つの領域が含まれています。サービス ウィンドウで、追跡したイベント、および オーケストレーション ペイン。 さらに、対話モードでは、変数の一覧および変数のプロパティで、ビューの下部に表示します。  
  
> [!NOTE]
>  表示される場合を除き、オーケストレーション デバッガーは、サービスの実際の状態を表示できません**ブレークポイント**モードがそのインスタンスにアタッチします。  
  
## <a name="service-pane-in-orchestration-debugger"></a>オーケストレーション デバッガーでのサービス ウィンドウ  
 オーケストレーション デバッガー ウィンドウの上部ペインには、次の情報が表示されます。  
  
|Tag|[詳細]|  
|---------|------------|  
|名前|現在のビュー (オーケストレーション デバッガー) を示し、メッセージ フロー ビューに移動することができます。|  
|インスタンスの詳細|サービスの名前と現在のオーケストレーション インスタンスを一意に識別する GUID が表示されます。|  
|モード|デバッグ モード (再生/ライブ)、オーケストレーションの状態 (開始、中断、完了など)、Attached (はいまたは No)、およびブレークポイント モード (でクラスまたはインスタンス上)。|  
|サービスのオプション|ドロップダウン リストのデバッガーとインスタンスの状態に基づいてアクションを実行できます。|  
  
 この情報は、下、オーケストレーション デバッガーには 2 つのペイン: 左側で、追跡したイベント ウィンドウと右側の オーケストレーション ペイン。  
  
## <a name="tracked-events-pane-in-orchestration-debugger"></a>オーケストレーション デバッガーで追跡したイベント ウィンドウ  
 追跡したイベント ウィンドウには、すべてのアクションが開始または完了したかどうかなど、オーケストレーションの実行の状態が一覧表示します。 このペインでそれぞれの行を選択すると、図形が開始され、青の図形の終了時に緑色で強調表示された [オーケストレーション] ペインで対応する図形が表示されます。  
  
 追跡したイベント ウィンドウには、次の列が表示されます。  
  
|オプション|操作|  
|------------|------------|  
|アクションの状態 (左の列)|特定のアクションの状態です。 矢印は、アクションが開始され、終了図形は、完了したことを示しますを示します。|  
|アクション名|オーケストレーションのアクションの名前。|  
|アクションの種類|アクションを表す図形の種類です。 矢印は、アクションが開始され、終了図形は、完了したことを示しますのことを示します。|  
|Time|アクションが実行された時刻。|  
|date|アクションが実行された日付。|  
  
## <a name="orchestration-pane-in-orchestration-debugger"></a>オーケストレーション デバッガー [オーケストレーション] ペイン  
 グループ ハブ ページでの出力を追跡メッセージ イベントとサービス インスタンスの オーケストレーション ペインは、すべての図形をオーケストレーション インスタンスが表示される領域です。 次の表では、[オーケストレーション] ペインのコンテキスト メニューのアクションを示します。  
  
|オプション|操作|  
|------------|------------|  
|クラスでブレークポイントを設定します。|図形を右クリックし、**クラスのブレークポイントを設定**オプション。 ブレークポイントが設定されていることを示す図形に赤い点が表示されます。|  
|インスタンスのブレークポイントの設定|図形を右クリックし、**インスタンスのブレークポイントを設定**オプション。 ブレークポイントが設定されていることを示す図形に赤い点が表示されます。|  
|クラスのブレークポイントを削除します。|図形を右クリックし、**ブレークポイントの削除**オプション。 ブレークポイントが削除されていることを示す図形から赤い点が表示されなくなります。|  
|インスタンスのブレークポイントを削除します。|図形を右クリックし、**インスタンスのブレークポイントを設定**オプション。 ブレークポイントが削除されていることを示す図形から赤い点が表示されなくなります。|  
  
### <a name="variable-list-and-variable-properties-panes"></a>変数の一覧と変数のプロパティ ウィンドウ  
 これらのウィンドウは、対話形式のデバッグを使用するオーケストレーション ランタイムに接続されている場合にのみ表示されます、**アタッチ**サービス オプション。 画面の下部にあるこれらのペインが表示されます。  
  
 変数リストには、名前、値、および変数の型が表示されます。 値は、変数が Null か、そうでない場合、そのオブジェクトの種類が含まれて かどうかを示します。 型は、 **Assembly.Namespace.Name**のオブジェクト。  
  
 変数のプロパティ ペインには、オブジェクトの種類によって異なります変数のプロパティが表示されます。 たとえば、ポートにはこれが含まれますアドレス、名、スコープ、型、および値。 メッセージが、ショートカットを表示します。メッセージには、各パーツは名前、サイズ、プロパティ、型、および値です。 コンテキスト プロパティなどのコレクションは、ポップアップに表示されます。 値の部分の表示は、ツールヒントとして表示されます。  
  
 ユーザーは、進みブレークポイントからブレークポイントへと、これらの変数の状態を調べます。  
  
 次の表では、変数の一覧については、コンテキスト メニューのアクションを示します。  
  
|オプション|操作|  
|------------|------------|  
|メッセージを保存します。|Null 以外であるメッセージを右クリックしての [変数一覧] ウィンドウで、**メッセージの保存**オプション。 その保存先となるディレクトリを選択するように求めるメッセージが表示されます。|  
  
### <a name="service-options-drop-down-list"></a>サービスのオプションのドロップダウン リスト  
 サービスのオプションのドロップダウン リストでは、インスタンスと、デバッガーの状態に基づいて、有効なアクションを示します。 次の表では、サービスのオプションのドロップダウン リストで使用可能なアクションを示します。  
  
|オプション|操作|  
|------------|------------|  
|サービスを続行します。|サービスを接続した場合、ブレークポイントで停止しているオーケストレーション インスタンスを続行します。|  
|デバッグ モードで再開します|デバッグ モードで中断したオーケストレーション インスタンスを再開します。 これにより、対話モードに、インスタンスにアタッチし、対話的にデバッグすることができます。<br /><br /> 操作ビューとオーケストレーション デバッガーから利用できます。 オーケストレーションにのみ適用されます。|  
|サービスを終了します。|オーケストレーション インスタンスを終了します。|  
|[アタッチ]|オーケストレーション インスタンスにサービスを添付し、現在の状態と変数を取得します|  
|クラスのすべてのブレークポイントを削除します。|オーケストレーション クラス内のすべてのブレークポイントを削除します。 接続されていない場合にのみ使用できます。|  
|すべてのブレークポイントを削除します。|オーケストレーション インスタンス内のすべてのブレークポイントを削除します。 アタッチされている場合にのみ使用できます。|  
|すべてのメッセージを保存します。|すべての受信/送信メッセージを追跡するために選択した場合に限り、オーケストレーション インスタンスに関連付けられているすべてのメッセージを保存します。|  
|ブレークポイントのアクションを表示します。|互換性に影響する前に実行された図形を黄色で最後のアクションの強調表示します。|  
|オーケストレーションを呼び出し元の表示|呼び出しを行ったオーケストレーション インスタンスにビューを返します。 つまり、これに戻ることが、親オーケストレーション。<br /><br /> 呼び出し先オーケストレーションのインスタンスでのみ使用できます。|  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [オーケストレーション デバッガーの報告モード](../core/reporting-mode-in-orchestration-debugger.md)  
  
-   [オーケストレーション デバッガーの対話モード](../core/interactive-mode-in-orchestration-debugger.md)  
  
## <a name="see-also"></a>参照  
 [オーケストレーションのデバッグ](../core/debugging-an-orchestration.md)