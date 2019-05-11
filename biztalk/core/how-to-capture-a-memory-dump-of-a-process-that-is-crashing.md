---
title: クラッシュしたプロセスのメモリ ダンプをキャプチャする方法 |Microsoft Docs
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
ms.openlocfilehash: a425b3ca166c3de1726633b06193b2569dba34cd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387038"
---
# <a name="how-to-capture-a-memory-dump-of-a-process-that-is-crashing"></a>クラッシュしたプロセスのメモリ ダンプをキャプチャする方法
BizTalk プロセス BTSNTSvc.exe として定義されている**クラッシュ**プロセスが Windows によって強制終了された場合。 クラッシュは通常、アクセス違反やスタック オーバーフローなどのプロセスで未処理の例外によって発生します。 このような場合は、Windows には、デバッガー、Dr が既定値します。ワトソン博士 (drwtsn32.exe) では、例外をキャッチし、プロセスを終了します。  
  
 クラッシュしたプロセスのメモリ ダンプをキャプチャするには、次の手順に従って、未処理の例外をキャッチするデバッグ診断ツールを構成します。  
  
### <a name="to-configure-the-debug-diagnostics-tool-to-capture-a-crash-dump"></a>クラッシュ ダンプをキャプチャするデバッグ診断ツールを構成するには  
  
1.  デバッグ診断ツールを起動します**開始**、**すべてのプログラム**、 **IIS 診断**、 **Debug Diagnostics Tools**、 **デバッグ診断ツール 1.0**します。  
  
2.  場合、 **Select Rule Type**の規則の追加ウィザード ダイアログ ボックスが表示されない場合、をクリックして、**ツール**クリックし、**ルール アクション**、 をクリック**規則の追加**規則の追加ウィザードを表示します。  
  
3.  選択、**クラッシュ**オプション、 **Select Rule Type**ダイアログをクリックします**次**。  
  
4.  選択**特定のプロセス**で、 **Select Target Type**ダイアログをクリックします **[次へ]** します。  
  
5.  BTSNTSvc.exe プロセスがクラッシュし、クリックを選択**次**します。  
  
6.  **Advanced Configuration**ダイアログ **[次へ]** 既定値を受け入れます。  
  
7.  **選択 Dump Location And Rule Name**ダイアログ **[次へ]** 既定値を受け入れます。  
  
8.  **Rule Completed**ダイアログ**完了**の既定値を受け入れるように**ルールを今すぐアクティブ化**します。  
  
9. 既定では、プロセスのメモリ ダンプを \Program Files\IIS Resources\DebugDiag\Logs に保存されます\\<*クラッシュ規則の名前*\>ローカル コンピューターの次のディレクトリの時間をプロセスでハンドルされない例外が発生します。  
  
## <a name="see-also"></a>参照  
 [デバッグ診断ツールを使用してメモリ ダンプを分析する方法](../core/how-to-use-debug-diagnostics-to-analyze-a-memory-dump.md)