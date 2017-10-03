---
title: "Windows4 のイベントの追跡の使用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ETW
- BTAJDEEnterpriseOneTrace command
- Event Tracing for Windows
ms.assetid: 5f07d317-5ae2-4d1e-a343-941f3079dc4b
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c7614ae4f6470427a77815338767b04f07aaa73
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-event-tracing-for-windows"></a>Windows イベント トレーシングの使用
Microsoft BizTalk Adapter for JD Edwards EnterpriseOne は、エラー、警告、および情報メッセージを Windows イベント ビューアーに記録します。 その他のトレース メッセージを表示するには、Event Tracing for Windows (ETW) ツールを使用します。 ETW をアクティブにすると、メッセージ受信用の *.etl ファイルが作成されます。 このファイルはバイナリ形式であり、読み取るには変換する必要があります。 これを行うには、解釈に利用できるコンシューマー アプリケーションが必要、 \*.etl ファイルです。 たとえば、tracerpt.exe や tracedmp.ex です。 Tracept.exe アプリケーションに変換、\*を 2 つのテキスト ファイルに .etl: summary.txt と dumpfile.csv です。  
  
## <a name="etw-components"></a>ETW コンポーネント  
 Windows イベント トレーシングには 3 つのコンポーネントがあります。  
  
-   **コント ローラー アプリケーション**です。 プロバイダー (たとえば、tracelog.exe や logman.exe) のアクティブ化と非アクティブ化を行います。  
  
     PATH 環境変数を、tracelog.exe の場所を指すように設定します。 これにより、BTAJDEEnterpriseOneTrace の呼び出しが、システムの tracelog.exe を見つけることができます。 既定では、BTAJDEEnterpriseOneTrace は現在のパスを検索します。  
  
> [!NOTE]
>  tracelog.exe は Microsoft SDK から使用でき、BizTalk Adapter for JD Edwards EnterpriseOne で提供されているコマンドと互換性があります。 Logman.exe を使用するのには、logman のマニュアルを参照してください。  
  
-   **コンシューマー アプリケーション**です。 記録されたイベントを読み取ります。 コンシュマー アプリケーションで etl ファイルのイベントを読み取るには、Event Tracing for Windows によるダンプ処理でファイルを生成する必要があります。 通常、これはトレースが非アクティブ化されたときに実行されます。  
  
     コント ローラーにコンシューマー アプリケーションを使用して、トレースを非アクティブ化せず、リアルタイムのオプションを使用してトレースをアクティブ化する必要があります**\<リアルタイム > =-rt**です。  
  
-   **プロバイダー**です。 イベントを提供するために使用されます。 BizTalk Adapter for JD Edwards EnterpriseOne には 3 種類のプロバイダーが用意されています。 これらは Windows Management Instrumentation (WMI) に登録されます。 root\WMI\EventTrace パス内で登録プロバイダーを検索するには、WMI CIM Studio などのツールを使用します。  
  
 BizTalk Adapter for JD Edwards EnterpriseOne には 3 つのプロバイダーがあり、異なる種類のメッセージを記録できます。  
  
-   **受信元ログ プロバイダー**:\<トレース要素 > スイッチは**-受信者**です。 使用して**-受信者**を実行時にアダプターによって受信されたログからすべてのメッセージを取得します。  
  
-   **送信元ログ プロバイダー**:\<トレース要素 > スイッチは**-トランスミッター**です。 使用して**-トランスミッター**を実行時にアダプターによって送信されたログからすべてのメッセージを取得します。  
  
-   **管理ログ プロバイダー**:\<トレース要素 > スイッチは**-管理**使用**-管理**参照中に生成されたログからすべてのメッセージを取得するにはサーバー システムです。  
  
### <a name="btajdeenterpriseonetrace-command"></a>BTAJDEEnterpriseOneTrace コマンド  
 ETW を使用して、BizTalk Adapter for JD Edwards EnterpriseOne のコマンドを実行する**BTAJDEEnterpriseOneTrace.cmd**です。 このコマンドは次のように使用します。  
  
```  
BTAJDEEnterpriseOneTrace <Trace element> -start [-cir <MB>|   
-seq <MB>] [-rt] logfile  
BTAJDEEnterpriseOneTrace <Trace element> -stop  
  
```  
  
 場所: **\<トレース要素 >**プロバイダーの種類は、(必須)。  
  
 そのオプションは次のとおりです。  
  
-   **送信機能**  
  
-   **-受信機**  
  
-   **-管理**  
  
-   **-開始、停止**: プロバイダーをアクティブまたは非アクティブです。  
  
-   **-cir \<MB >**: ファイルのサイズおよび種類です。 -cir は循環ファイルです。 \<MB >: サイズはメガ単位です。  
  
-   **-seq \<MB >**: ファイルのサイズおよび種類です。 -seq はシーケンシャル ファイルです。 \<MB >: サイズはメガ単位です。  
  
-   **-rt**: リアル タイム モードに設定します。  
  
-   **Logfile**: ログ ファイルの名前 (既定では c:\rtlog.etl) です。  
  
 例:  
  
```  
BTAJDEEnterpriseOneTrace -transmitter -start -cir 10 -rt c:\log\mylog.etl  
BTAJDEEnterpriseOneTrace -transmitter -stop  
```  
  
## <a name="see-also"></a>参照  
 [JD Edwards EnterpriseOne のトラブルシューティング](../core/troubleshooting-jd-edwards-enterpriseone.md)