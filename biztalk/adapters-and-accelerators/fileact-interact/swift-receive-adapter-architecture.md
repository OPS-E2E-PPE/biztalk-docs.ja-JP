---
title: "SWIFT 受信アダプターのアーキテクチャ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 16f32689-0b70-4389-8596-991fd776f185
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3aca9b5ef1fd1130feeebad3ec6fdf072d3bf88d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="swift-receive-adapter-architecture"></a>SWIFT 受信アダプターのアーキテクチャ
BizTalk Server では、受信アダプターは、ホストを実行する別のプロセスが作成されたことを意味する独自のメモリ領域内でホストされます。 このホストが SWIFTNet リンク (SNL) 構成では、サブシステムを定義することによって生成されます。  
  
 サーバーの実行可能ファイルは、SNL 構成 (paramfile) サブシステムとして構成され、SWIFTNet Start コマンドを実行することによって生成されます。 SNL サーバー アプリケーションを終了するには、SWIFTNet Stop コマンドを実行します。 SNL は、サーバー実行可能ファイルの有効期間を管理します。  
  
> [!NOTE]
>  サービス局のシナリオでは、独自のセキュリティ コンテキストで実行されている SWIFT メンバーを複数のサービスを提供するアダプターが必要です。 個々 の構成でサポートできるこの受信場所 1 メンバー、およびサーバー実行可能ファイルの複数のインスタンスを起動 — 各いずれか 1 つに専用の受信場所。  
  
 BizTalk Server では、受信アダプターは、BizTalk メッセージング エンジンと対話する次の通信パターンをサポートします。  
  
-   1 つの方法: 遅延モードで、受信アダプター (サーバー) が動作しているときは、このモードが必要です。 遅延のモードでは、アダプターは、受信メッセージの既定の受信確認を送信します。 受信確認の場合、既定値は、アダプターのプロパティで構成できます。 送信アダプターを経由して LOB アプリケーションによって、ビジネス レベルの応答を後で送信できます。  
  
    > [!NOTE]
    >  遅延のモードが発生した場合のすべての値入力してくださいアダプターの構成にアダプターが、応答を構築するため。  
  
-   要求-応答-このモードでは、アダプターは BizTalk に SWIFT からの要求を送信して、応答を待機します。 アダプターであれば、タイムアウト、LOB アプリケーションから応答がありません。 タイムアウト値は、アダプターの構成で構成できます。 既定値は 60 秒です。  
  
     受信アダプターは、1 つのスレッドでのみ、SNL からコールバックを受信できます。 つまり、受信アダプターできますを受け取るさらにメッセージ SNL から最初のメッセージを送信した後のみです。 したがって、既定のバッチ サイズは 1 に設定されます。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [SWIFT 受信アダプター URI](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-uri.md)  
  
-   [SWIFT 受信アダプターの初期化](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-initialization.md)  
  
-   [SWIFT 受信アダプター セキュリティ コンテキスト](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-security-context.md)  
  
-   [SWIFT 受信アダプターの同期および遅延モード](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-synchronous-and-deferred-modes.md)  
  
-   [SWIFT 受信アダプター ストア アンド フォワード](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-store-and-forward.md)