---
title: "応答のないプロセスのメモリ ダンプをキャプチャする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8ad53376-2fab-4dee-8a6a-a44d157390f2
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 520921010a8bbfd73de8c3b305a1270ca8363c46
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-capture-a-memory-dump-of-a-process-that-is-non-responsive"></a>応答のないプロセスのメモリ ダンプを取得する方法
BizTalk プロセス BTSNTSvc.exe として定義されている**ぶら下げ**プロセスが応答を停止するようです。 プロセスのハングに共通する現象は、次のとおりです。  
  
-   オーケストレーションが実行を停止しているように見える。  
  
-   メッセージが処理されていない。  
  
-   全般的なタイムアウトの問題が発生する。  
  
-   BizTalk プロセス BTSNTSvc.exe が非常に大量の CPU サイクルに表示されるを消費する、**プロセス**のタブ**タスク マネージャー**です。  
  
 ハングしている BTSNTSvc.exe プロセスのメモリ ダンプを取得するには、次の手順を実行します。  
  
### <a name="to-configure-the-debug-diagnostics-tool-to-capture-a-hang-dump"></a>ハング ダンプを取得するようデバッグ診断ツールを構成するには  
  
1.  デバッグ診断ツールを起動**開始**、**すべてのプログラム**、 **IIS 診断**、 **Debug Diagnostics Tools**、 **デバッグ診断ツール 1.0**です。  
  
2.  場合、 **Select Rule Type**ルール構成ウィザードのダイアログ ボックスが表示されたら、をクリックして、**キャンセル**ボタンをクリックします。  
  
3.  クリックして、**プロセス**デバッグ診断ツールのタブです。  
  
4.  応答しない BTSNTSvc.exe プロセスを右クリックし、選択**Create Full Userdump**です。 既定では、プロセスのメモリ ダンプは、ローカル コンピューターの \Program Files\IIS Resources\DebugDiag\Logs\Misc ディレクトリに保存されます。  
  
## <a name="see-also"></a>参照  
 [デバッグ診断ツールを使用して、メモリ ダンプを分析する方法](../core/how-to-use-debug-diagnostics-to-analyze-a-memory-dump.md)