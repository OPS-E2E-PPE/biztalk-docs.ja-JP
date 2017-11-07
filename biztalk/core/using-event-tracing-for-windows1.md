---
redirect_url: /biztalk/core/troubleshooting-tibco-rendezvous/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: 5c29b21ea36efe3fe0a63c5994b771e36e570ed3
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="using-event-tracing-for-windows"></a>Windows イベント トレーシングの使用
Microsoft BizTalk Adapter for TIBCO Rendezvous は、エラー、警告、および情報メッセージを Windows イベント ビューアーに記録します。 追加のトレーシング メッセージを表示するには、Windows イベント トレーシング (ETW) ツールを使用します。 ETW をアクティブにすると、メッセージ受信用の *.etl ファイルが作成されます。 このファイルはバイナリ形式であり、読み取るには変換する必要があります。 これを行うには、解釈に利用できるコンシューマー アプリケーションが必要、 \*.etl ファイル、tracerpt.exe や tracedmp.exe などです。 たとえば、tracerpt.exe アプリケーションに変換されます、 \*.etl ファイルを 2 つのテキスト ファイル: summary.txt と dumpfile.csv です。  
  
## <a name="etw-components"></a>ETW コンポーネント  
 Windows イベント トレーシングには 3 つのコンポーネントがあります。  
  
-   **コント ローラー アプリケーション**: をアクティブにし、(たとえば、tracelog.exe または logman.exe) プロバイダーが非アクティブ化します。  
  
     PATH 環境変数を、tracelog.exe の場所を指すように設定します。 これにより、BTATIBCO RendezvousTrace の呼び出しが、システムの tracelog.exe を見つけることができます。 既定では、BTATIBCO RendezvousTrace は現在のパスを検索します。  
  
> [!NOTE]
>  tracelog.exe は Microsoft SDK に含まれており、Microsoft BizTalk Adapter for TIBCO Rendezvous で提供されるコマンドと互換性があります。 logman.exe の使い方については、logman のマニュアルを参照してください。  
  
-   **コンシューマー アプリケーション**: 記録されたイベントの読み取り。  
  
     コンシュマー アプリケーションで etl ファイルのイベントを読み取るには、Event Tracing for Windows によるダンプ処理でファイルを生成する必要があります。 通常、この作業は、コントローラーがトレーシングを非アクティブ化するときに行われます。  
  
     コント ローラーにコンシューマー アプリケーションを使用して、トレースを非アクティブ化せず、リアル タイム オプションを使用してトレースをアクティブ化する必要があります\<リアルタイム > =-rt です。  
  
-   **プロバイダー**: イベントを提供します。  
  
     BizTalk Adapter for TIBCO Rendezvous には 3 つの異なるプロバイダーが含まれています。 これらは Windows Management Instrumentation (WMI) に登録されます。 root\WMI\EventTrace パス内で登録プロバイダーを検索するには、WMI CIM Studio などのツールを使用します。  
  
 BizTalk Adapter for TIBCO Rendezvous には 3 つのプロバイダーがあります。 そのため、異なる種類のメッセージを記録できます。  
  
-   **受信元ログ プロバイダー**:\<トレース要素 > スイッチは**-受信者**です。  
  
-   使用して**-受信者**を実行時にアダプターによって受信されたログからすべてのメッセージを取得します。  
  
-   **送信元ログ プロバイダー**:\<トレース要素 > スイッチは**-トランスミッター**です。  
  
     使用して**-トランスミッター**を実行時にアダプターによって送信されたログからすべてのメッセージを取得します。  
  
-   **管理ログ プロバイダー —**、\<トレース要素 > スイッチは**-管理**です。  
  
     使用して**-管理**サーバー システムの参照中に生成されたログからすべてのメッセージを取得します。  
  
## <a name="btatibcorvtrace-command"></a>BTATIBCORVTrace コマンド  
 ETW を使用するには、BizTalk Adapter for TIBCO Rendezvous コマンドである BTATIBCORVTrace.cmd を実行します。 このコマンドは次のように使用します。  
  
```  
BTATIBCORVTrace <Trace element> -start [-cir <MB>|   
-seq <MB>] [-rt] logfile  
BTATIBCORVTrace <Trace element> -stop  
```  
  
 場所: **\<トレース要素 >**プロバイダーの種類は、(必須)。  
  
 そのオプションは次のとおりです。  
  
-   **送信機能**  
  
-   **-受信機**  
  
-   **-管理**  
  
-   **-開始、停止**: プロバイダーをアクティブまたは非アクティブです。  
  
-   **-cir \<MB >**: ファイルのサイズおよび種類です。 **-cir**循環ファイルです。 **\<MB >**: サイズ (メガバイト単位)。  
  
-   **-seq \<MB >**: ファイルのサイズおよび種類です。 **-seq**シーケンシャル ファイルです。 **\<MB >**: サイズ (メガバイト単位)。  
  
-   **-rt**: リアル タイム モードに設定します。  
  
-   **Logfile**: ログ ファイルの名前 (既定では c:\rtlog.etl) です。  
  
 例:  
  
```  
BTATIBCORVTrace -transmitter -start -cir 10 -rt c:\log\mylog.etl  
BTATIBCORVTrace -transmitter -stop  
```  
  
## <a name="see-also"></a>参照  
 [TIBCO Rendezvous のトラブルシューティング](../core/troubleshooting-tibco-rendezvous.md)