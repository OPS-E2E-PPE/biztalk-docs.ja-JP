---
title: Windows4 のイベント追跡の使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ETW
- BTAJDEEnterpriseOneTrace command
- Event Tracing for Windows
ms.assetid: 5f07d317-5ae2-4d1e-a343-941f3079dc4b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75f5a62f2ae243c6fd3eabc5d40f99136471ad30
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752328"
---
# <a name="using-event-tracing-for-windows"></a>イベント トレーシング Windows の使用
Microsoft BizTalk Adapter for JD Edwards EnterpriseOne は、エラー、警告、および情報メッセージを Windows イベント ビューアーに記録します。 その他のトレース メッセージを表示するには、Event Tracing for Windows (ETW) ツールを使用します。 ETW をアクティブになると作成、 \*.etl ファイル メッセージを受信します。 このファイルはバイナリ形式であり、読み取るには変換する必要があります。 これを行うには、解釈に利用できるコンシューマー アプリケーションが必要、 \*.etl ファイル。 たとえば、tracerpt.exe や tracedmp.ex します。 Tracept.exe アプリケーションに変換、\*を 2 つのテキスト ファイルに .etl: summary.txt と dumpfile.csv です。  
  
## <a name="etw-components"></a>ETW コンポーネント  
 Windows イベント トレーシングには 3 つのコンポーネントがあります。  
  
-   **コント ローラー アプリケーション**します。 プロバイダー (たとえば、tracelog.exe や logman.exe) のアクティブ化と非アクティブ化を行います。  
  
     PATH 環境変数を、tracelog.exe の場所を指すように設定します。 これにより、BTAJDEEnterpriseOneTrace の呼び出しが、システムの tracelog.exe を見つけることができます。 既定では、BTAJDEEnterpriseOneTrace は現在のパスを検索します。  
  
> [!NOTE]
>  tracelog.exe は Microsoft SDK から使用でき、BizTalk Adapter for JD Edwards EnterpriseOne で提供されているコマンドと互換性があります。 Logman.exe を使用するには、logman のマニュアルを参照してください。  
  
- **コンシューマー アプリケーション**します。 記録されたイベントを読み取ります。 コンシュマー アプリケーションで etl ファイルのイベントを読み取るには、Event Tracing for Windows によるダンプ処理でファイルを生成する必要があります。 通常、これはトレースが非アクティブ化されたときに実行されます。  
  
   コント ローラーに、コンシューマー アプリケーションを使用して、トレースを非アクティブ化せず、リアルタイムのオプションを使用してトレースをアクティブ化する必要があります**\<リアルタイム\>=-rt**します。  
  
- **プロバイダー**します。 イベントを提供するために使用されます。 BizTalk Adapter for JD Edwards EnterpriseOne には 3 種類のプロバイダーが用意されています。 これらは Windows Management Instrumentation (WMI) に登録されます。 root\WMI\EventTrace パス内で登録プロバイダーを検索するには、WMI CIM Studio などのツールを使用します。  
  
  BizTalk Adapter for JD Edwards EnterpriseOne には 3 つのプロバイダーがあり、異なる種類のメッセージを記録できます。  
  
- **受信側のログ記録プロバイダー**: \<Trace 要素\>スイッチが **-受信者**します。 使用 **-受信者**実行時に、アダプターで受信されたログからすべてのメッセージを取得します。  
  
- **送信元ログ プロバイダー**: \<Trace 要素\>スイッチが **-送信機**します。 使用 **-送信機**実行時にアダプターによって送信されたログからすべてのメッセージを取得します。  
  
- **管理ログ プロバイダー**: \<Trace 要素\>スイッチが **-管理**使用 **-管理**生成されたログからすべてのメッセージを取得するにはサーバー システムの参照中には。  
  
### <a name="btajdeenterpriseonetrace-command"></a>BTAJDEEnterpriseOneTrace コマンド  
 ETW を使用して、BizTalk Adapter for JD Edwards EnterpriseOne のコマンドを実行する**BTAJDEEnterpriseOneTrace.cmd**します。 このコマンドは次のように使用します。  
  
```  
BTAJDEEnterpriseOneTrace <Trace element> -start [-cir <MB>|   
-seq <MB>] [-rt] logfile  
BTAJDEEnterpriseOneTrace <Trace element> -stop  
  
```  
  
 場所:  **\<Trace 要素\>** プロバイダーの種類は、(必須)。  
  
 そのオプションがあります。  
  
- **-送信機**  
  
- **-受信機**  
  
- **-管理**  
  
- **-開始、停止**: プロバイダーをアクティブまたは非アクティブです。  
  
- **-cir \<MB\>**: ファイルのサイズおよび種類。 -cir は循環ファイルです。 \<MB\>: サイズはメガ単位です。  
  
- **-seq \<MB\>**: ファイルのサイズおよび種類。 -seq はシーケンシャル ファイルです。 \<MB\>: サイズはメガ単位です。  
  
- **-rt**: のリアル タイム モードに設定します。  
  
- **ログ ファイル**: ログ ファイルの名前 (既定では c:\rtlog.etl) です。  
  
  以下に例を示します。  
  
```  
BTAJDEEnterpriseOneTrace -transmitter -start -cir 10 -rt c:\log\mylog.etl  
BTAJDEEnterpriseOneTrace -transmitter -stop  
```  
  
## <a name="see-also"></a>参照  
 [JD Edwards EnterpriseOne のトラブルシューティング](../core/troubleshooting-jd-edwards-enterpriseone.md)