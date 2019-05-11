---
title: SWIFT 受信アダプターのアーキテクチャ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 16f32689-0b70-4389-8596-991fd776f185
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23deda6ba243e3b6823f5b8b80e560260c45fc7d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364616"
---
# <a name="swift-receive-adapter-architecture"></a>SWIFT 受信アダプターのアーキテクチャ
BizTalk Server で、受信アダプターはホストを実行する別のプロセスが作成されたことを意味する独自のメモリ領域内でホストされます。 SWIFTNet リンク (SNL) 構成では、サブシステムを定義することでこのホストが生成されます。  
  
 サーバーの実行可能ファイルは SNL 構成 (に paramfile) サブシステムとして構成し、SWIFTNet Start コマンドを実行することが生成されます。 SNL サーバー アプリケーションは SWIFTNet 停止コマンドを実行して終了します。 SNL は、サーバー実行可能ファイルの有効期間を管理します。  
  
> [!NOTE]
>  サービスの局シナリオでは、独自のセキュリティ コンテキストで実行されている SWIFT メンバーを複数のサービスを提供するアダプターが必要です。 個人を構成することによってサポートされるこの受信場所ごとのメンバーとサーバーの実行可能ファイルの複数のインスタンスを生成-それぞれ専用の 1 つの受信場所。  
  
 BizTalk Server では、受信アダプターは、BizTalk メッセージング エンジンと対話する次の通信パターンをサポートします。  
  
-   1 つの方法-受信アダプター (サーバー) を遅延モードで動作しているときは、このモードが必要です。 遅延のモードでは、アダプターは、受信メッセージの既定の受信確認を送信します。 受信確認用の既定値は、アダプターのプロパティで構成できます。 送信アダプター経由で LOB アプリケーションで、ビジネス レベルの応答を後で送信できます。  
  
    > [!NOTE]
    >  遅延のモードが発生した場合のすべての値必要がありますを入力するアダプターの構成では、アダプターが、応答を構築するため。  
  
-   要求-応答: このモードでは、アダプターが BizTalk には、SWIFT からの要求を送信して、応答を待機します。 アダプターは、LOB アプリケーションからの応答がない場合、タイムアウトが。 タイムアウト値は、アダプターの構成で構成できます。 既定値は 60 秒です。  
  
     受信アダプターは、1 つのスレッドでのみ、SNL からコールバックを受信できます。 つまり、受信アダプターできます受信さらにメッセージ SNL から最初のメッセージを送信した後のみです。 そのため、既定のバッチ サイズは 1 に設定されます。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [SWIFT 受信アダプターの URI](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-uri.md)  
  
-   [SWIFT 受信アダプターの初期化](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-initialization.md)  
  
-   [SWIFT 受信アダプター セキュリティ コンテキスト](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-security-context.md)  
  
-   [SWIFT 受信アダプターの同期および遅延モード](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-synchronous-and-deferred-modes.md)  
  
-   [SWIFT 受信アダプターのストア アンド フォワード](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-store-and-forward.md)