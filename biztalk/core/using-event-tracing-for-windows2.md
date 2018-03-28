---
title: Windows 2 のイベントの追跡の使用 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ETW
- Event Tracing for Windows
ms.assetid: 88b91b74-2b2e-40e0-a3e9-1ebd6367abe8
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c5f610d75048b250fc90aba7f723cee39c4f2e1
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="using-event-tracing-for-windows"></a>Windows イベント トレーシングの使用
Microsoft BizTalk Adapter for JD Edwards OneWorld ではエラー、警告、および情報のメッセージを Windows イベント ビューアーに記録します。 その他のトレース メッセージを表示するには、Event Tracing for Windows (ETW) ツールを使用します。 ETW をアクティブにすると、メッセージ受信用の *.etl ファイルが作成されます。 このファイルはバイナリ形式であり、読み取るには変換する必要があります。 これを行うには、解釈に利用できるコンシューマー アプリケーションが必要、 \*.etl ファイル: tracerpt.exe や tracedmp.exe などです。  
  
## <a name="etw-components"></a>ETW コンポーネント  
 Windows イベント トレーシングには 3 つのコンポーネントがあります。  
  
-   **コント ローラー アプリケーションです。** プロバイダー (たとえば、tracelog.exe や logman.exe) のアクティブ化と非アクティブ化を行います。  
  
     PATH 環境変数を、tracelog.exe の場所を指すように設定します。 これにより、BTAJDEdwardsOneWorldTrace の呼び出しが、システム内 tracelog.exe を見つけることができます。 既定では、BTAJDEdwardsOneWorldTrace は現在のパスを検索します。  
  
    > [!NOTE]
    >  tracelog.exe は Microsoft SDK に含まれており、BizTalk Adapter for JD Edwards OneWorld で提供されるコマンドと互換性があります。 logman.exe を使用するには、logman のドキュメントを参照してください。  
  
-   **コンシューマー アプリケーションです。** 記録されたイベントを読み取ります。  
  
     コンシューマー アプリケーションで .etl ファイル内のイベントを読み取るには、Windows イベント トレーシングでそれらのイベントを .etl ファイルにダンプする必要があります。 通常、これはトレースが非アクティブ化されたときに実行されます。  
  
     コント ローラーにコンシューマー アプリケーションを使用して、トレースを非アクティブ化せず、リアルタイムのオプションを使用してトレースをアクティブ化する必要があります**\<リアルタイム\>=-rt**です。  
  
-   **プロバイダーです。** イベントを提供します。  
  
 BizTalk Adapter for JD Edwards OneWorld には 5 つの異なるプロバイダーがあります。 これらは Windows Management Instrumentation (WMI) に登録されます。 root\WMI\EventTrace パス内で登録プロバイダーを検索するには、WMI CIM Studio などのツールを使用します。  
  
 BizTalk Adapter for JD Edwards OneWorld には 5 つのプロバイダーがあり、さまざまな種類のメッセージを記録できます。  
  
-   **受信側のログ プロバイダーです。** \<トレース要素\>スイッチが**-受信者**です。  
  
-   **受信元 CastDetails プロバイダー。** \<トレース要素\>スイッチが**- castDetailsReceive**です。  
  
-   **送信元ログ プロバイダーです。** \<トレース要素\>スイッチが**-トランスミッター**です。  
  
-   **送信元 CastDetails プロバイダー。** \<トレース要素\>スイッチが**- castDetailsTransmit**です。  
  
-   **管理ログ プロバイダーです。** \<トレース要素\>スイッチが**-管理**です。  
  
 BTAJDEOneWorldTrace コマンド  
  
 ETW を使用するには、BizTalk Adapter for JD Edwards OneWorld のコマンドである BTAJDEOneWorldTrace.cmd を実行します。 このコマンドは次のように使用します。  
  
```  
BTAJDEOneWorldTrace <Trace element> -start [-cir <MB>|   
      -seq <MB>] [-rt] logfile  
BTAJDEOneWorldTrace <Trace element> -stop  
```  
  
 各要素の説明は次のとおりです。  
  
-   **\<Trace 要素\>**プロバイダーの種類は、(必須)。  
  
-   そのオプションがあります。  
  
    -   **-castDetailsTransmit**  
  
    -   **-送信機能**  
  
    -   **-castDetailsReceive**  
  
    -   **-受信者**  
  
    -   **管理**  
  
    -   **--start、-stop**: プロバイダーをアクティブまたは非アクティブです。  
  
    -   **-cir \<MB\>**: ファイルのサイズおよび種類です。 -cir は循環ファイルです。 \<MB\>: サイズはメガ単位です。  
  
    -   **-seq \<MB\>**: ファイルのサイズおよび種類です。 -seq はシーケンシャル ファイルです。 \<MB\>: サイズはメガ単位です。  
  
    -   **-rt**: でリアルタイムに設定します。  
  
    -   **ログ ファイル**: ログ ファイルの名前 (既定では c:\rtlog.etl) です。  
  
 例:  
  
```  
BTAJDEOneWorldTrace -transmitter -start -cir 10 -rt c:\log\mylog.etl  
BTAJDEOneWorldTrace -transmitter -stop  
```  
  
## <a name="see-also"></a>参照  
 [JD Edwards OneWorld のトラブルシューティング](../core/troubleshooting-jd-edwards-oneworld.md)