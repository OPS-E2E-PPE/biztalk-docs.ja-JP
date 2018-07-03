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
ms.openlocfilehash: e3643dab17f8d1592f1e5fddce30aa12e537c817
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969139"
---
# <a name="how-to-capture-a-memory-dump-of-a-biztalk-process"></a>BizTalk プロセスのメモリ ダンプを取得する方法
状況によっては、BizTalk Server で実行中のプロセスのメモリ ダンプを取得し、そのプロセスの詳細な分析を実行する必要が生じる場合があります。 メモリ ダンプの分析が必要な状況として、以下のような場合が挙げられます。  
  
- プロセスが応答しない場合  
  
- プロセスがクラッシュしている場合  
  
- プロセスでメモリ リークが発生している場合  
  
  ここでは、適切な種類のメモリ ダンプを取得する手順について説明します。  
  
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