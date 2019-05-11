---
title: デバッグ診断ツールを使用してメモリ ダンプを分析する方法 |Microsoft Docs
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
ms.openlocfilehash: 47b8818979a9d278323d97dae2d1436c1d169829
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383413"
---
# <a name="how-to-use-debug-diagnostics-to-analyze-a-memory-dump"></a>デバッグ診断ツールを使用してメモリ ダンプを分析する方法
IIS 診断**デバッグ診断ツール**キャプチャされたメモリ ダンプ ファイルの基本的な分析を提供できる機能が含まれています。 実行するには、メモリ ダンプ ファイルの分析は次の手順に従います。  
  
### <a name="to-analyze-the-dump-file"></a>ダンプ ファイルを分析するには  
  
1.  デバッグ診断ツールを起動します**開始**、**プログラム**、 **IIS 診断**、 **Debug Diagnostics Tools**、 **デバッグ診断ツール 1.0**します。  
  
2.  をクリックして、**高度な分析**タブ。  
  
3.  **Available Analysis Scripts**をクリックして選択**クラッシュ/ハング アナライザー**クラッシュ/ハング ダンプを分析したり、クリックして選択する**Memory Pressure Analysis**メモリを分析するにはメモリ リークが発生している疑いがあるプロセスのダンプします。  
  
4.  をクリックして、**データ ファイルの追加**生成されたダンプ ファイルを参照し、をクリックするボタン、**オープン**ダンプ ファイルを分析するデータ ファイルの可能な一覧に追加するボタンをクリックします。  
  
5.  追加されたダンプ ファイルを選択する をクリックします。  
  
6.  をクリックして、**分析の開始**ボタンをクリックします。  
  
    > [!NOTE]
    >  アナライザーは、検索して、シンボル ファイルがローカル コンピューターにインストールされていない場合は、適切なシンボル ファイルをインターネットからダウンロードを試行します。 カスタム コードは、BTSNTSvc.exe プロセスで実行されているが場合、は、更新、**シンボル検索パスのデバッグ**オプションで使用できる、**フォルダーと検索パス**のタブ、**オプション (& a)設定**ダイアログを適切なシンボル ファイルが含まれます。 をクリックして、**ツール**メニュー選択し、**オプションと設定**を表示する、**オプションと設定**ダイアログ。  
  
7.  分析が完了すると、レポートが .mht ファイル形式で生成され、Internet Explorer で表示されます。 既定では、このレポートは、ローカル コンピューターの \Program Files\IIS \debugdiag\reports ディレクトリに保存されます。  
  
## <a name="see-also"></a>参照  
 [BizTalk プロセスのメモリ ダンプをキャプチャする方法](../core/how-to-capture-a-memory-dump-of-a-biztalk-process.md)