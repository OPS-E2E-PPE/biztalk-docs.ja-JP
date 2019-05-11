---
title: 応答のないプロセスのメモリ ダンプをキャプチャする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ad53376-2fab-4dee-8a6a-a44d157390f2
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea2310f38c221147efdba5b1e2980a548fabfa86
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387065"
---
# <a name="how-to-capture-a-memory-dump-of-a-process-that-is-non-responsive"></a>応答のないプロセスのメモリ ダンプをキャプチャする方法
BizTalk プロセス BTSNTSvc.exe として定義されている**ぶら下げ**プロセスが応答を停止するようです。 プロセスのハングの一般的な現象は、次のとおりです。  
  
- 実行を停止するオーケストレーションが表示されます。  
  
- メッセージが処理されていません。  
  
- 一般的なタイムアウトの問題が発生します。  
  
- BizTalk プロセス BTSNTSvc.exe が非常に大量の CPU サイクルに表示を使用する、**プロセス**タブ**タスク マネージャー**します。  
  
  ハングしている BTSNTSvc.exe のメモリ ダンプをキャプチャするプロセスは、これらの手順に従います。  
  
### <a name="to-configure-the-debug-diagnostics-tool-to-capture-a-hang-dump"></a>ハング ダンプをキャプチャするデバッグ診断ツールを構成するには  
  
1.  デバッグ診断ツールを起動します**開始**、**すべてのプログラム**、 **IIS 診断**、 **Debug Diagnostics Tools**、 **デバッグ診断ツール 1.0**します。  
  
2.  場合、 **Select Rule Type**ルール構成ウィザードのダイアログが表示されたら、をクリックして、**キャンセル**ボタンをクリックします。  
  
3.  をクリックして、**プロセス**デバッグ診断ツールのタブ。  
  
4.  応答しない BTSNTSvc.exe プロセスを右クリックし、選択**Create Full Userdump**します。 既定では、ローカル コンピューターの \Program Files\IIS \debugdiag\logs\misc ディレクトリにプロセスのメモリ ダンプが保存されます。  
  
## <a name="see-also"></a>参照  
 [デバッグ診断ツールを使用してメモリ ダンプを分析する方法](../core/how-to-use-debug-diagnostics-to-analyze-a-memory-dump.md)