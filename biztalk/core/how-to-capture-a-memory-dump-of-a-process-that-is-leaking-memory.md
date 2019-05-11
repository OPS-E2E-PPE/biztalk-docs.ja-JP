---
title: メモリのリークが発生しているプロセスのメモリ ダンプをキャプチャする方法 |Microsoft Docs
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
ms.openlocfilehash: 3df482776809fa9f1685d4466ca0688521c53e4e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342662"
---
# <a name="how-to-capture-a-memory-dump-of-a-process-that-is-leaking-memory"></a>メモリのリークが発生しているプロセスのメモリ ダンプをキャプチャする方法
BizTalk プロセス BTSNTSvc.exe が必要はありません、それによってメモリを解放に失敗した場合は、メモリ リークを持つものとして定義されているは時間の経過と共に使用可能なメモリの量を削減します。 下の値を表示することによって、プロセスのメモリ使用量を決定できます、**メモリ使用量**の列、**プロセス** タブで使用できる**タスク マネージャー**します。 メモリを解放しないまま時間の経過と共にメモリを消費するプロセスが解決しない場合は、システム全体のパフォーマンスに悪影響が。  
  
 このトピックでは、ルールを使用して、または手動でメモリ ダンプをキャプチャすることで、メモリをリークの発生が疑われる BizTalk プロセスのメモリ ダンプをキャプチャするための手順を説明します。 メモリ リークの発生が予測可能でない場合は、メモリ ダンプをキャプチャの手動による方法を使用します。  
  
### <a name="to-capture-a-memory-dump-of-a-process-that-is-leaking-memory-by-using-a-rule"></a>ルールを使用してメモリがリークしているプロセスのメモリ ダンプをキャプチャするには  
  
1.  デバッグ診断ツールを起動します**開始**、**すべてのプログラム**、 **IIS 診断**、 **Debug Diagnostics Tools**、 **デバッグ診断ツール 1.0**します。  
  
2.  場合、 **Select Rule Type**の規則の追加ウィザード ダイアログ ボックスが表示されない場合、をクリックして、**ツール**クリックし、**ルール アクション**、 をクリック**規則の追加**規則の追加ウィザードを表示します。  
  
3.  選択、 **Memory and Handle Leak**オプション、 **Select Rule Type**ダイアログをクリックします**次**。  
  
4.  をクリックし、メモリ リークの発生が疑われる BTSNTSvc.exe プロセスを選択**次**します。  
  
5.  **Configure Tracking Duration**ダイアログに次の手順します。  
  
    1.  観察対象のプロセス メモリの増加が直ちに発生した場合にオプションをオンに**メモリ追跡ルールがアクティブにするとすぐに開始**します。 観察対象のプロセス メモリの増加が直ちに発生しない場合は、適切な数の分を指定、**ウォーム アップ時間**メモリ追跡を開始するまでテキスト ボックス。  
  
        > [!NOTE]
        >  観察対象のプロセス メモリの増加は、特定のコンポーネントを BizTalk オーケストレーションが外部コンポーネントを参照する場合の例については、メモリに読み込む場合は、メモリ リークが原因の場合はすぐに発生しません。  
  
    2.  適切な数の分を指定、**時間を追跡**メモリ追跡を停止するまでテキスト ボックス。 これは、分の数値である必要があります、メモリ リークを再現するのに十分な長さ。 この期間が経過した後、プロセスのメモリ ダンプがキャプチャされます。  
  
    3.  オプションをオンに**userdump を予期しないプロセスの終了時に取得する規則のクラッシュを自動作成**です。  
  
    4.  **[次へ]** をクリックします。  
  
6.  **選択 Dump Location And Rule Name**ダイアログ **[次へ]** 既定値を受け入れます。  
  
7.  **Rule Completed**ダイアログ**完了**の既定値を受け入れるように**ルールを今すぐアクティブ化**します。  
  
8.  既定では、プロセスのメモリ ダンプを \Program Files\IIS Resources\DebugDiag\Logs に保存されます\\<*クラッシュ規則の名前*\>時間間隔後に、ローカル コンピューターのディレクトリ指定されている、 **Configure Tracking Duration**ダイアログが経過しました。  
  
### <a name="to-manually-capture-a-memory-dump-of-a-process-that-is-leaking-memory"></a>手動でメモリをリークしているプロセスのメモリ ダンプをキャプチャするには  
  
1.  デバッグ診断ツールを起動します**開始**、**すべてのプログラム**、 **IIS 診断**、 **Debug Diagnostics Tools**、 **デバッグ診断ツール 1.0**します。  
  
2.  場合、 **Select Rule Type**の規則の追加ウィザード ダイアログ ボックスが表示されたら、クリックして**キャンセル**します。  
  
3.  クリックして選択し、**プロセス**デバッグ診断ツールのタブ。  
  
4.  をクリックし、メモリ リークの発生が疑われる BTSNTSvc.exe プロセスを右クリックして**リークを監視**します。  
  
5.  プロセスのメモリ使用量を監視**タスク マネージャー**を右クリックし、プロセスのメモリ ダンプを手動でキャプチャ プロセスのメモリ使用量が BizTalk コンピューターで使用可能なメモリの 60 ~ 80% に近づくと、プロセスにオプションを選択して**Create Full Userdump**します。  
  
6.  既定では、ローカル コンピューターの \Program Files\IIS \debugdiag\logs\misc\ ディレクトリにプロセスのメモリ ダンプが保存されます。  
  
## <a name="see-also"></a>参照  
 [デバッグ診断ツールを使用してメモリ ダンプを分析する方法](../core/how-to-use-debug-diagnostics-to-analyze-a-memory-dump.md)