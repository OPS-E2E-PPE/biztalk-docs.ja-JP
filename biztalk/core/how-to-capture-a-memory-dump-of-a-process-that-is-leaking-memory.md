---
title: メモリのリークが発生しているプロセスのメモリ ダンプをキャプチャする方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67404919-33a6-40ac-b1c4-09841db12fcf
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e1e57a3c4d3c035069c550cdc540de1c88e8880
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969128"
---
# <a name="how-to-capture-a-memory-dump-of-a-process-that-is-leaking-memory"></a>メモリ リークが発生したプロセスのメモリ ダンプを取得する方法
不要になったメモリを BizTalk プロセス BTSNTSvc.exe が解放できず、時間の経過と共に使用可能なメモリ量が減少している場合、このプロセスにメモリ リークが発生していると見なされます。 下の値を表示することによって、プロセスのメモリ使用量を決定できます、**メモリ使用量**の列、**プロセス** タブで使用できる**タスク マネージャー**です。 プロセスが長時間にわたってメモリを解放せずに消費し続けると、全体のシステム パフォーマンスに悪影響が生じます。  
  
 ここでは、ルールの使用か、メモリ ダンプの手動取得によって、メモリ リークの発生が疑われる BizTalk プロセスのメモリ ダンプを取得する手順について説明します。 メモリ リークの発生が予測不可能な場合、メモリ ダンプを手動で取得する方法を使用してください。  
  
### <a name="to-capture-a-memory-dump-of-a-process-that-is-leaking-memory-by-using-a-rule"></a>メモリ リークが発生したプロセスのメモリ ダンプを、ルールを使用して取得するには  
  
1.  デバッグ診断ツールを起動**開始**、**すべてのプログラム**、 **IIS 診断**、 **Debug Diagnostics Tools**、 **デバッグ診断ツール 1.0**です。  
  
2.  場合、 **Select Rule Type**の規則の追加ウィザード ダイアログ ボックスが表示されない場合をクリックして、**ツール** メニューの 選択**ルール アクション**、 をクリック**ルールの追加**を規則の追加ウィザードを表示します。  
  
3.  選択、 **Memory and Handle Leak**オプション、 **Select Rule Type**ダイアログとクリック **[次へ]** です。  
  
4.  メモリおよびクリックをリークの発生が疑われる BTSNTSvc.exe プロセスを選択**次**です。  
  
5.  **Configure Tracking Duration**ダイアログに次の手順します。  
  
    1.  観察対象のプロセス メモリの増加が直ちに発生した場合にオプションをオンに**Start ルールがアクティブにするとすぐに追跡 memory**です。 観察対象のプロセス メモリの増加が直ちに発生しない場合は、適切な数の分を指定します。、 **Warm-up time**メモリ追跡を開始するまでのテキスト ボックス。  
  
        > [!NOTE]
        >  BizTalk オーケストレーションによる外部のコンポーネントの参照時など、特定のコンポーネントがメモリに読み込まれたときにメモリ リークが発生する場合、観察対象のプロセス メモリの増加が直ちに発生しない可能性があります。  
  
    2.  適切な数の分の指定、 **Tracking time**メモリ追跡を停止するまでのテキスト ボックス。 この分数は、メモリ リークの再現に十分な長さにする必要があります。 この期間が経過した後、プロセスのメモリ ダンプが取得されます。  
  
    3.  チェック ボックスをオン**userdump を予期しないプロセスの終了時に取得するルールのクラッシュを自動作成**です。  
  
    4.  **[次へ]** をクリックします。  
  
6.  **選択 Dump Location And Rule Name**ダイアログ **[次へ]** 既定値を入力します。  
  
7.  **Rule Completed**ダイアログ**完了**の既定値を受け入れるように**ルールを今すぐアクティブ化**です。  
  
8.  \Program Files\IIS Resources\DebugDiag\Logs に既定では、プロセスのメモリ ダンプが保存される\\<*クラッシュ ルールの名前*\>時間間隔後に、ローカル コンピューターのディレクトリ指定されている、 **Configure Tracking Duration**ダイアログが経過しました。  
  
### <a name="to-manually-capture-a-memory-dump-of-a-process-that-is-leaking-memory"></a>メモリ リークが発生したプロセスのメモリ ダンプを手動で取得するには  
  
1.  デバッグ診断ツールを起動**開始**、**すべてのプログラム**、 **IIS 診断**、 **Debug Diagnostics Tools**、 **デバッグ診断ツール 1.0**です。  
  
2.  場合、 **Select Rule Type**の規則の追加ウィザード ダイアログ ボックスが表示されたら、をクリックして**キャンセル**です。  
  
3.  クリックして選択、**プロセス**デバッグ診断ツールのタブです。  
  
4.  メモリおよびクリックをリークの発生が疑われる BTSNTSvc.exe プロセスを右クリックして**リークを監視**です。  
  
5.  プロセスのメモリ使用量を監視**タスク マネージャー**を右クリックして、プロセスのメモリ ダンプを手動でキャプチャ プロセスのメモリ使用量、BizTalk コンピューター上で利用できるメモリの 60 ~ 80% に近づくと、プロセスにオプションを選択して**Create Full Userdump**です。  
  
6.  既定では、プロセスのメモリ ダンプは、ローカル コンピューターの \Program Files\IIS Resources\DebugDiag\Logs\Misc\ ディレクトリに保存されます。  
  
## <a name="see-also"></a>参照  
 [デバッグ診断ツールを使用して、メモリ ダンプを分析する方法](../core/how-to-use-debug-diagnostics-to-analyze-a-memory-dump.md)