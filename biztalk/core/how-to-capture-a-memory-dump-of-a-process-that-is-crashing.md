---
title: クラッシュしたプロセスのメモリ ダンプをキャプチャする方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5f436b72-2b6a-4519-acc3-e7ba978651fe
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e87664180b7ad4d5fdcd121542974a08b8634d55
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969568"
---
# <a name="how-to-capture-a-memory-dump-of-a-process-that-is-crashing"></a>クラッシュしたプロセスのメモリ ダンプを取得する方法
BizTalk プロセス BTSNTSvc.exe として定義されている**クラッシュ**プロセスが予期せず Windows によって終了する場合。 クラッシュは通常、プロセス内でアクセス違反やスタック オーバーフローなどの未処理の例外が発生したことが原因で起こります。 これらの状況で、Windows の既定のデバッガー、災害復旧します。ワトソン博士 (drwtsn32.exe) は、例外をキャッチし、プロセスを終了します。  
  
 クラッシュしたプロセスのメモリ ダンプを取得するには、次の手順に従って、未処理の例外をキャッチするようデバッグ診断ツールを構成します。  
  
### <a name="to-configure-the-debug-diagnostics-tool-to-capture-a-crash-dump"></a>クラッシュ ダンプを取得するようデバッグ診断ツールを構成するには  
  
1.  デバッグ診断ツールを起動**開始**、**すべてのプログラム**、 **IIS 診断**、 **Debug Diagnostics Tools**、 **デバッグ診断ツール 1.0**です。  
  
2.  場合、 **Select Rule Type**の規則の追加ウィザード ダイアログ ボックスが表示されない場合をクリックして、**ツール** メニューの 選択**ルール アクション**、 をクリック**ルールの追加**を規則の追加ウィザードを表示します。  
  
3.  選択、**クラッシュ**オプション、 **Select Rule Type**ダイアログとクリック **[次へ]** です。  
  
4.  選択**特定のプロセス**で、 **Select Target Type**ダイアログとクリック **[次へ]** です。  
  
5.  クラッシュしてクリックして、いる BTSNTSvc.exe プロセスを選択**次**です。  
  
6.  **高度な構成**ダイアログ **[次へ]** 既定値を入力します。  
  
7.  **選択 Dump Location And Rule Name**ダイアログ **[次へ]** 既定値を入力します。  
  
8.  **Rule Completed**ダイアログ**完了**の既定値を受け入れるように**ルールを今すぐアクティブ化**です。  
  
9. \Program Files\IIS Resources\DebugDiag\Logs に既定では、プロセスのメモリ ダンプが保存される\\<*クラッシュ ルールの名前*\>れたときに、ローカル コンピューターの次のディレクトリ、プロセスで未処理の例外が発生します。  
  
## <a name="see-also"></a>参照  
 [デバッグ診断ツールを使用して、メモリ ダンプを分析する方法](../core/how-to-use-debug-diagnostics-to-analyze-a-memory-dump.md)