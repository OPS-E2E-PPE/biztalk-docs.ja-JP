---
title: Windows3 のイベントの追跡の使用 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ETW
- provider
- Receiver Logging Provider
- Transmitter Logging Provider
- controller application
- consumer application
- BTATIBCOEMSTrace command
- Event Tracing for Windows
ms.assetid: 71954431-2015-4d50-b69e-500c883b1e04
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75b2b339c99dcf1b64368c73381d1dbe81e0fb39
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="using-event-tracing-for-windows"></a>Windows イベント トレーシングの使用
Microsoft BizTalk Adapter for TIBCO Enterprise Message Service は、エラー メッセージ、警告メッセージ、および情報メッセージを Windows イベント ビューアーに記録します。 追加のトレーシング メッセージを表示するには、Windows イベント トレーシング (ETW) ツールを使用します。 ETW をアクティブにすると、メッセージ受信用の *.etl ファイルが作成されます。 このファイルはバイナリ形式であり、読み取るには変換する必要があります。 これを行うには、解釈に利用できるコンシューマー アプリケーションが必要、 \*.etl ファイル、tracerpt.exe や tracedmp.exe などです。 たとえば、tracerpt.exe アプリケーションの変換、 \*.etl ファイルを 2 つのテキスト ファイル: summary.txt と dumpfile.csv です。  
  
## <a name="etw-components"></a>ETW コンポーネント  
 Windows イベント トレーシングには 3 つのコンポーネントがあります。  
  
-   **コント ローラー アプリケーション**: をアクティブにし、(たとえば、tracelog.exe や logman.exe) プロバイダーを非アクティブにします。  
  
     PATH 環境変数を、tracelog.exe の場所を指すように設定します。 これにより、BTATIBCO EMSTrace の呼び出しが、システム内の tracelog.exe を検出できることです。 既定では、BTATIBCO EMSTrace は現在のパスを検索します。  
  
    > [!NOTE]
    >  tracelog.exe は Microsoft SDK に含まれており、Microsoft BizTalk Adapter for TIBCO Enterprise Message Service で提供されるコマンドと互換性があります。 logman.exe の使い方については、logman のマニュアルを参照してください。  
  
-   **コンシューマー アプリケーション**: 記録されたイベントの読み取り。  
  
     コンシュマー アプリケーションで etl ファイルのイベントを読み取るには、Event Tracing for Windows によるダンプ処理でファイルを生成する必要があります。 通常、この作業は、コントローラーがトレーシングを非アクティブ化するときに行われます。  
  
     コント ローラーにコンシューマー アプリケーションを使用して、トレースを非アクティブ化せず、リアル タイム オプションを使用してトレースをアクティブ化する必要があります\<リアルタイム\>-rt を = です。  
  
-   **プロバイダー**: イベントを提供します。  
  
     BizTalk Adapter for TIBCO Enterprise Message Service には 3 つの異なるプロバイダーが含まれています。 これらは Windows Management Instrumentation (WMI) に登録されます。 root\WMI\EventTrace パス内で登録プロバイダーを検索するには、WMI CIM Studio などのツールを使用します。  
  
 BizTalk Adapter for TIBCO Enterprise Message Service には、さまざまな種類のメッセージをログに記録することを可能にするプロバイダーがあります。  
  
-   **受信元ログ プロバイダー**:\<トレース要素\>スイッチが**-受信者**です。  
  
     使用 **-受信者** 実行時にアダプターによって受信されたログからすべてのメッセージを取得します。  
  
-   **送信元ログ プロバイダー**:\<トレース要素\>スイッチが**-トランスミッター**です。  
  
     使用 **-送信機**実行時にアダプターによって送信されたログからすべてのメッセージを取得します。  
  
### <a name="btatibcoemstrace-command"></a>BTATIBCOEMSTrace コマンド  
 ETW を使用するには、BizTalk Adapter for TIBCO Enterprise Message Service のコマンド BTATIBCOEMSTrace.cmd を実行します。 このコマンドは次のように使用します。  
  
```  
BTATIBCOEMSTrace <Trace element> -start [-cir <MB>|   
    -seq <MB>] [-rt] logfile  
BTA TIBCOEMSTrace <Trace element> -stop  
```  
  
 各要素の説明は次のとおりです。  
  
-   **\<Trace 要素\>**プロバイダーの種類は、(必須)。  
  
 そのオプションは次のとおりです。  
  
-   **-送信機能**  
  
-   **-受信者**  
  
-   **--start、-stop**: プロバイダーをアクティブまたは非アクティブです。  
  
-   **-cir \<MB\>**: ファイルのサイズおよび種類です。 **-cir** は循環ファイルです。 **\<MB\>**: サイズ (メガバイト単位)。  
  
-   **-seq \<MB\>**: ファイルのサイズおよび種類です。 **-seq** シーケンシャル ファイルです。 **\<MB\>**: サイズ (メガバイト単位)。  
  
-   **-rt**: でリアルタイムに設定します。  
  
-   **ログ ファイル**: ログ ファイルの名前 (既定では c:\rtlog.etl) です。  
  
 例:  
  
```  
BTATIBCOEMSTrace -transmitter -start -cir 10 -rt c:\log\mylog.etl  
BTATIBCOEMSTrace -transmitter -stop  
```  
  
## <a name="see-also"></a>参照  
 [TIBCO Enterprise Message Service のトラブルシューティング](../core/troubleshooting-tibco-enterprise-message-service.md)