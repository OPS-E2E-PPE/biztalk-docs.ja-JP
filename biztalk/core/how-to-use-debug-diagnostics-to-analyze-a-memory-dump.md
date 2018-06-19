---
title: デバッグ診断ツールを使用して、メモリ ダンプを分析する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 986a91a7-feab-4014-bbd5-e8b966b8b841
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ccc0faf72c9123ab7a501af8520f273e8c528b8d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256602"
---
# <a name="how-to-use-debug-diagnostics-to-analyze-a-memory-dump"></a>デバッグ診断ツールを使用してメモリ ダンプを分析する方法
IIS 診断**デバッグ診断ツール**キャプチャされたメモリ ダンプ ファイルの基本分析が可能な機能が含まれています。 メモリ ダンプ ファイルの分析を実行するには、次の手順を実行します。  
  
### <a name="to-analyze-the-dump-file"></a>ダンプ ファイルを分析するには  
  
1.  デバッグ診断ツールを起動**開始**、**プログラム**、 **IIS 診断**、 **Debug Diagnostics Tools**、 **デバッグ診断ツール 1.0**です。  
  
2.  クリックして、**高度な分析**タブです。  
  
3.  **Available Analysis Scripts**をクリックして選択**Analyzers**クラッシュ/ハング ダンプを分析またはをクリックして選択する**Memory Pressure Analysis**メモリを分析するにはメモリ リークの発生が疑われるプロセスのダンプします。  
  
4.  をクリックして、**データ ファイルを追加**生成されたダンプ ファイルを参照し、をクリックするボタン、**開く**ダンプ ファイルを分析するのにはデータ ファイルの可能な一覧に追加するボタンをクリックします。  
  
5.  追加されたダンプ ファイルをクリックして選択します。  
  
6.  クリックして、**分析の開始**ボタンをクリックします。  
  
    > [!NOTE]
    >  ローカル コンピューターにシンボル ファイルがインストールされていない場合、アナライザーは、インターネット経由で適切なシンボル ファイルの検索とダウンロードを試みます。 カスタム コードは、BTSNTSvc.exe プロセスで実行されているが場合、は、更新、**シンボル検索パスのデバッグ**オプションで使用できる、**フォルダーと検索パス**のタブ、**オプション (& a)設定**ダイアログを適切なシンボル ファイルが含まれます。 クリックして、**ツール**メニューを選択**オプションと設定**を表示する、**オプションと設定**ダイアログ。  
  
7.  分析が完了すると、.mht ファイル形式のレポートが生成され、Internet Explorer で表示されます。 既定では、このレポートは、ローカル コンピューターの \Program Files\IIS Resources\DebugDiag\Reports ディレクトリに保存されます。  
  
## <a name="see-also"></a>参照  
 [BizTalk プロセスのメモリ ダンプをキャプチャする方法](../core/how-to-capture-a-memory-dump-of-a-biztalk-process.md)