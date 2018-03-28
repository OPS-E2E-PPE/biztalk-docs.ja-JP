---
title: TIBCO Rendezvous のトラブルシューティング |Microsoft ドキュメント
description: Troubl を Windows イベント トレーシングを使用して BizTalk Server で TIBCO Rendezvous の esdhoot Microsoft BizTalk Adapter を =
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5b7bc3ab-16fa-4e91-8730-9431473b2fb4
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18ae8d599b67a1a572021cae0ebc9bfc64992a9b
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="troubleshoot-tibco-rendezvous"></a>TIBCO Rendezvous をトラブルシューティングします。
  
## <a name="use-event-tracing-for-windows"></a>Windows のイベント トレースを使用します。
Microsoft BizTalk Adapter for TIBCO Rendezvous は、エラー、警告、および情報メッセージを Windows イベント ビューアーに記録します。 追加のトレーシング メッセージを表示するには、Windows イベント トレーシング (ETW) ツールを使用します。 ETW をアクティブにすると、メッセージ受信用の *.etl ファイルが作成されます。 このファイルはバイナリ形式であり、読み取るには変換する必要があります。 これを行うには、解釈に利用できるコンシューマー アプリケーションが必要、 \*.etl ファイル、tracerpt.exe や tracedmp.exe などです。 たとえば、tracerpt.exe アプリケーションは変換、 \*.etl ファイルを 2 つのテキスト ファイル: summary.txt と dumpfile.csv です。  
  
## <a name="etw-components"></a>ETW コンポーネント  
 Windows イベント トレーシングには 3 つのコンポーネントがあります。  
  
-   **コント ローラー アプリケーション**: をアクティブにし、(たとえば、tracelog.exe や logman.exe) プロバイダーを非アクティブにします。  
  
     PATH 環境変数を、tracelog.exe の場所を指すように設定します。 これにより、BTATIBCO RendezvousTrace の呼び出しが、システム内の tracelog.exe を検出できることです。 既定では、BTATIBCO RendezvousTrace は現在のパスを検索します。  
  
> [!NOTE]
>  tracelog.exe は Microsoft SDK に含まれており、Microsoft BizTalk Adapter for TIBCO Rendezvous で提供されるコマンドと互換性があります。 logman.exe の使い方については、logman のマニュアルを参照してください。  
  
-   **コンシューマー アプリケーション**: 記録されたイベントの読み取り。  
  
     コンシュマー アプリケーションで etl ファイルのイベントを読み取るには、Event Tracing for Windows によるダンプ処理でファイルを生成する必要があります。 通常、この作業は、コントローラーがトレーシングを非アクティブ化するときに行われます。  
  
     コント ローラーにコンシューマー アプリケーションを使用して、トレースを非アクティブ化せず、リアル タイム オプションを使用してトレースをアクティブ化する必要があります\<リアルタイム\>-rt を = です。  
  
-   **プロバイダー**: イベントを提供します。  
  
     BizTalk Adapter for TIBCO Rendezvous には 3 つの異なるプロバイダーが含まれています。 これらは Windows Management Instrumentation (WMI) に登録されます。 root\WMI\EventTrace パス内で登録プロバイダーを検索するには、WMI CIM Studio などのツールを使用します。  
  
 BizTalk Adapter for TIBCO Rendezvous には 3 つのプロバイダーがあります。 そのため、異なる種類のメッセージを記録できます。  
  
-   **受信元ログ プロバイダー**:\<トレース要素\>スイッチが**-受信者**です。  
  
-   使用 **-受信者** 実行時にアダプターで受信されたログからメッセージを取得します。  
  
-   **送信元ログ プロバイダー**:\<トレース要素\>スイッチが**-トランスミッター**です。  
  
     使用 **-送信機** 実行時にアダプターによって送信されたログからメッセージを取得します。  
  
-   **管理ログ プロバイダー —**、\<トレース要素\>スイッチが**-管理**です。  
  
     使用 **-管理**サーバー システムの参照中に生成されたログからメッセージを取得します。  
  
## <a name="btatibcorvtrace-command"></a>BTATIBCORVTrace コマンド  
 ETW を使用するには、BizTalk Adapter for TIBCO Rendezvous コマンドである BTATIBCORVTrace.cmd を実行します。 このコマンドは次のように使用します。  
  
```  
BTATIBCORVTrace <Trace element> -start [-cir <MB>|   
-seq <MB>] [-rt] logfile  
BTATIBCORVTrace <Trace element> -stop  
```  
  
 場所: **\<トレース要素\>**プロバイダーの種類は、(必須)。  
  
 そのオプションは次のとおりです。  
  
-   **-送信機能**  
  
-   **-受信者**  
  
-   **管理**  
  
-   **--start、-stop**: プロバイダーをアクティブまたは非アクティブです。  
  
-   **-cir \<MB\>**: ファイルのサイズおよび種類です。 **-cir** は循環ファイルです。 **\<MB\>**: サイズ (メガバイト単位)。  
  
-   **-seq \<MB\>**: ファイルのサイズおよび種類です。 **-seq** シーケンシャル ファイルです。 **\<MB\>**: サイズ (メガバイト単位)。  
  
-   **-rt**: でリアルタイムに設定します。  
  
-   **ログ ファイル**: ログ ファイルの名前 (既定では c:\rtlog.etl) です。  
  
 以下に例を示します。  
  
```  
BTATIBCORVTrace -transmitter -start -cir 10 -rt c:\log\mylog.etl  
BTATIBCORVTrace -transmitter -stop  
```  
## <a name="see-more"></a>詳細を参照してください。
[例外処理](../core/using-biztalk-server-exception-handling4.md)  
[セキュリティ](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md)  
[アーキテクチャ](../core/architecture-of-biztalk-adapter-for-tibco-rendezvous.md)