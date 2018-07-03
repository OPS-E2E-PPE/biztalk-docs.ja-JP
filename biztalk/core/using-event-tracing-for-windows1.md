---
redirect_url: /biztalk/core/troubleshooting-tibco-rendezvous/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: f394629849f1c06328ca66ec6eb6cc21c574982a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969027"
---
# <a name="using-event-tracing-for-windows"></a>イベント トレーシング Windows の使用
Microsoft BizTalk Adapter for TIBCO Rendezvous は、エラー、警告、および情報メッセージを Windows イベント ビューアーに記録します。 追加のトレーシング メッセージを表示するには、Windows イベント トレーシング (ETW) ツールを使用します。 ETW をアクティブにすると、メッセージ受信用の *.etl ファイルが作成されます。 このファイルはバイナリ形式であり、読み取るには変換する必要があります。 これを行うには、解釈に利用できるコンシューマー アプリケーションが必要、 \*.etl ファイル、tracerpt.exe や tracedmp.exe などです。 たとえば、tracerpt.exe アプリケーションは変換、 \*.etl ファイルを 2 つのテキスト ファイル: summary.txt と dumpfile.csv です。  
  
## <a name="etw-components"></a>ETW コンポーネント  
 Windows イベント トレーシングには 3 つのコンポーネントがあります。  
  
-   **コント ローラー アプリケーション**: をアクティブにし、(たとえば、tracelog.exe または logman.exe) のプロバイダーを非アクティブにします。  
  
     PATH 環境変数を、tracelog.exe の場所を指すように設定します。 これにより、BTATIBCO RendezvousTrace の呼び出しが、システムの tracelog.exe を見つけることができます。 既定では、BTATIBCO RendezvousTrace は現在のパスを検索します。  
  
> [!NOTE]
>  tracelog.exe は Microsoft SDK に含まれており、Microsoft BizTalk Adapter for TIBCO Rendezvous で提供されるコマンドと互換性があります。 logman.exe の使い方については、logman のマニュアルを参照してください。  
  
- **コンシューマー アプリケーション**: 記録されたイベントの読み取り。  
  
   コンシュマー アプリケーションで etl ファイルのイベントを読み取るには、Event Tracing for Windows によるダンプ処理でファイルを生成する必要があります。 通常、この作業は、コントローラーがトレーシングを非アクティブ化するときに行われます。  
  
   コンシューマー アプリケーションを使用して、トレースを非アクティブ化せず、リアルタイム オプションでは、トレースで、コント ローラーによってアクティブ化する必要があります\<リアルタイム\>-rt を = です。  
  
- **プロバイダー**: イベントを提供します。  
  
   BizTalk Adapter for TIBCO Rendezvous には 3 つの異なるプロバイダーが含まれています。 これらは Windows Management Instrumentation (WMI) に登録されます。 root\WMI\EventTrace パス内で登録プロバイダーを検索するには、WMI CIM Studio などのツールを使用します。  
  
  BizTalk Adapter for TIBCO Rendezvous には 3 つのプロバイダーがあります。 そのため、異なる種類のメッセージを記録できます。  
  
- **受信側のログ記録プロバイダー**: \<Trace 要素\>スイッチが **-受信者**します。  
  
- 使用 **-受信者**実行時にアダプターで受信されたログからすべてのメッセージを取得します。  
  
- **送信元ログ プロバイダー**: \<Trace 要素\>スイッチが **-送信機**します。  
  
   使用 **-送信機**実行時にアダプターによって送信されたログからすべてのメッセージを取得します。  
  
- <strong>管理ログ プロバイダー —</strong>、 \<Trace 要素\>スイッチが **-管理**します。  
  
   使用 **-管理**サーバー システムの参照中に生成されたログからすべてのメッセージを取得します。  
  
## <a name="btatibcorvtrace-command"></a>BTATIBCORVTrace コマンド  
 ETW を使用するには、BizTalk Adapter for TIBCO Rendezvous コマンド BTATIBCORVTrace.cmd を実行します。 このコマンドは次のように使用します。  
  
```  
BTATIBCORVTrace <Trace element> -start [-cir <MB>|   
-seq <MB>] [-rt] logfile  
BTATIBCORVTrace <Trace element> -stop  
```  
  
 場所:  **\<Trace 要素\>** プロバイダーの種類は、(必須)。  
  
 そのオプションは次のとおりです。  
  
- **-送信機**  
  
- **-受信機**  
  
- **-管理**  
  
- **-開始、停止**: プロバイダーをアクティブまたは非アクティブです。  
  
- **-cir \<MB\>**: ファイルのサイズおよび種類。 **-cir**は循環ファイルです。 **\<MB\>**: サイズ (メガバイト単位)。  
  
- **-seq \<MB\>**: ファイルのサイズおよび種類。 **-seq**はシーケンシャル ファイルです。 **\<MB\>**: サイズ (メガバイト単位)。  
  
- **-rt**: のリアル タイム モードに設定します。  
  
- **ログ ファイル**: ログ ファイルの名前 (既定では c:\rtlog.etl) です。  
  
  以下に例を示します。  
  
```  
BTATIBCORVTrace -transmitter -start -cir 10 -rt c:\log\mylog.etl  
BTATIBCORVTrace -transmitter -stop  
```  
  
## <a name="see-also"></a>参照  
 [TIBCO Rendezvous のトラブルシューティング](../core/troubleshooting-tibco-rendezvous.md)