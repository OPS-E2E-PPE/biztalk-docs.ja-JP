---
title: BizTalk プロセスのメモリ ダンプをキャプチャする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8053fcf3-b331-4245-b3c3-21290463e0c0
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3d25ce00dfa48e84f6abc93de31121bdb655f2eb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387040"
---
# <a name="how-to-capture-a-memory-dump-of-a-biztalk-process"></a>BizTalk プロセスのメモリ ダンプをキャプチャする方法
特定の状況で詳細を実行する BizTalk Server で実行されているプロセスのメモリ ダンプをキャプチャするために必要な場合があります、プロセスの分析。 メモリ ダンプの分析が必要な状況を以下に示します。  
  
- プロセスが応答しない場合です。  
  
- プロセスがクラッシュします。  
  
- ときに、プロセスには、メモリ リークが発生します。  
  
  このセクションには、適切な種類のメモリ ダンプをキャプチャする必要がありますの手順が含まれています。  
  
## <a name="installation-of-the-iis-diagnostics-toolkit"></a>IIS 診断ツールキットのインストール  
 このセクションのトピックの使用が必要です、**デバッグ診断ツール**IIS 診断ツールキットのメモリ ダンプを取得します。 インストールする、**デバッグ診断ツール**IIS 診断ツールキットの次の手順に従います。  
  
1.  IIS 診断ツールキットをダウンロード[インターネット インフォメーション サービスの診断ツール](http://go.microsoft.com/fwlink/?LinkId=64426)します。  
  
2.  ダブルクリックして、 **iisdiag.msi**パッケージを IIS 診断ツールキットのセットアップ プログラムを起動して、選択、**カスタム**セットアップの種類。  
  
3.  **カスタム セットアップ**ダイアログ ボックスで、オプションのことを確認、 **Debug Diagnostics Tool 1.0**を有効にし、セットアップ プログラムで手順を完了します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [応答のないプロセスのメモリ ダンプをキャプチャする方法](../core/how-to-capture-a-memory-dump-of-a-process-that-is-non-responsive.md)  
  
-   [クラッシュしたプロセスのメモリ ダンプをキャプチャする方法](../core/how-to-capture-a-memory-dump-of-a-process-that-is-crashing.md)  
  
-   [メモリのリークが発生しているプロセスのメモリ ダンプをキャプチャする方法](../core/how-to-capture-a-memory-dump-of-a-process-that-is-leaking-memory.md)  
  
-   [デバッグ診断ツールを使用してメモリ ダンプを分析する方法](../core/how-to-use-debug-diagnostics-to-analyze-a-memory-dump.md)