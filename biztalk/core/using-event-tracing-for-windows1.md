---
redirect_url: /biztalk/core/troubleshooting-tibco-rendezvous/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 7f4b5dfc36e6f32401ffe04f2e72751d285ef493
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65247204"
---
# <a name="using-event-tracing-for-windows"></a>イベント トレーシング Windows の使用
Microsoft BizTalk Adapter for TIBCO Rendezvous は、エラー、警告、および情報メッセージを Windows イベント ビューアーに記録します。 Event Tracing for Windows (ETW) ツールを使用して、その他のトレース メッセージを確認できます。 ETW をアクティブになると、メッセージを受信する *.etl ファイルを作成します。 このファイルはバイナリ形式では、読み取るには変換する必要があります。 これを行うには、解釈に利用できるコンシューマー アプリケーションが必要、 \*.etl ファイル、tracerpt.exe や tracedmp.exe などです。 たとえば、tracerpt.exe アプリケーションは変換、 \*.etl ファイルを 2 つのテキスト ファイル: summary.txt と dumpfile.csv です。  
  
## <a name="etw-components"></a>ETW コンポーネント  
 Windows のイベントのトレースでは、次の 3 つのコンポーネントがあります。  
  
-   **コント ローラー アプリケーション**:アクティブにし、(たとえば、tracelog.exe または logman.exe) のプロバイダーを非アクティブ化されます。  
  
     Tracelog.exe の場所を PATH 環境変数を設定するとします。 これにより、BTATIBCO RendezvousTrace の呼び出しが、システムの tracelog.exe を見つけることができます。 既定では、BTATIBCO RendezvousTrace は現在のパスを検索します。  
  
> [!NOTE]
>  tracelog.exe は Microsoft SDK と Microsoft BizTalk Adapter for TIBCO Rendezvous コマンドと互換性があります。 Logman.exe を使用するには、logman のドキュメントを参照してください。  
  
- **コンシューマー アプリケーション**:読み取りは、イベントを記録します。  
  
   Etl ファイル内のイベントを読み取ることができるコンシューマー アプリケーションで Windows のイベントをトレースする必要がありますにダンプ ファイルにします。 通常、コント ローラーには、トレースが非アクティブ化時にこれを行います。  
  
   コンシューマー アプリケーションを使用して、トレースを非アクティブ化せず、リアルタイム オプションでは、トレースで、コント ローラーによってアクティブ化する必要があります\<リアルタイム\>-rt を = です。  
  
- **プロバイダー**:イベントを提供します。  
  
   BizTalk Adapter for TIBCO Rendezvous には、次の 3 つの異なるプロバイダーが含まれています。 Windows Management Instrumentation (WMI) に登録されています。 Root \wmi\eventtrace パスで登録されているプロバイダーを検索するには、WMI CIM Studio などのツールを使用することができます。  
  
  BizTalk Adapter for TIBCO Rendezvous は、次の 3 つのプロバイダーがあります。 異なる種類のメッセージを記録できます。  
  
- **受信元ロギング プロバイダー**:\<Trace 要素\>スイッチが **-受信者**します。  
  
- 使用 **-受信者**実行時にアダプターで受信されたログからすべてのメッセージを取得します。  
  
- **送信元ログ プロバイダー**: \<Trace 要素\>スイッチが **-送信機**します。  
  
   使用 **-送信機**実行時にアダプターによって送信されたログからすべてのメッセージを取得します。  
  
- <strong>管理ログ プロバイダー —</strong>、 \<Trace 要素\>スイッチが **-管理**します。  
  
   使用 **-管理**サーバー システムの参照中に生成されたログからすべてのメッセージを取得します。  
  
## <a name="btatibcorvtrace-command"></a>BTATIBCORVTrace コマンド  
 ETW を使用するには、BizTalk Adapter for TIBCO Rendezvous コマンド BTATIBCORVTrace.cmd を実行します。 次のように、このコマンドを使用するには。  
  
```  
BTATIBCORVTrace <Trace element> -start [-cir <MB>|   
-seq <MB>] [-rt] logfile  
BTATIBCORVTrace <Trace element> -stop  
```  
  
 各要素の説明は次のとおりです。**\<Trace 要素\>** プロバイダーの種類は、(必須)。  
  
 そのオプションは次のとおりです。  
  
- **-transmitter**  
  
- **-受信機**  
  
- **-management**  
  
- **-start, -stop**:アクティブ化またはプロバイダーを非アクティブ化します。  
  
- **-cir \<MB\>**:サイズとファイルの種類。 **-cir**は循環ファイルです。 **\<MB\>**:サイズ (メガバイト単位)。  
  
- **-seq \<MB\>**:サイズとファイルの種類。 **-seq**はシーケンシャル ファイルです。 **\<MB\>**:サイズ (メガバイト単位)。  
  
- **-rt**:リアルタイムに設定します。  
  
- **ログ ファイル**:ログ ファイルの名前 (既定では c:\rtlog.etl) です。  
  
  例 :  
  
```  
BTATIBCORVTrace -transmitter -start -cir 10 -rt c:\log\mylog.etl  
BTATIBCORVTrace -transmitter -stop  
```  
  
## <a name="see-also"></a>参照  
 [TIBCO Rendezvous のトラブルシューティング](../core/troubleshooting-tibco-rendezvous.md)