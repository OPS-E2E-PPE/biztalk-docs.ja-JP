---
title: Windows5 のイベント追跡の使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ETW
- events, Event Tracing for Windows
- controller application
- ETW components
- consumer application
- Provider
- Event Tracing for Windows
- Event Tracing for Windows, components
- BTAPeopleSoftTrace command
ms.assetid: 330ef84b-5e2a-4b79-85a9-72271eb489d2
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0fa744d7182f6238d71765afac2411b60974b5c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000035"
---
# <a name="using-event-tracing-for-windows"></a>イベント トレーシング Windows の使用
Microsoft BizTalk Adapter for PeopleSoft Enterprise は、エラー、警告、および情報メッセージを、Windows イベント ビューアーに記録します。 追加のトレーシング メッセージを表示するには、Windows イベント トレーシング (ETW) ツールを使用します。 ETW が有効である場合、このメッセージを受信する *.etl ファイルが作成されます。 ファイルはバイナリ形式では、読み取るには変換する必要があります。 これを行うには解釈に利用できるコンシューマー アプリケーションが必要、 \*.etl ファイル; tracerpt.exe や tracedmp.exe などです。  
  
## <a name="etw-components"></a>ETW コンポーネント  
 Windows イベント トレーシングには 3 つのコンポーネントがあります。  
  
- **コント ローラー アプリケーション**: をアクティブにし、(たとえば、tracelog.exe または logman.exe) のプロバイダーを非アクティブにします。  
  
   PATH 環境変数を、tracelog.exe の場所を指すように設定します。 ため`BTAPeopleSoftTrace`呼び出しは、システムの tracelog.exe を見つけることができます。 既定では、BTAPeopleSoftTrace は現在のパスを検索します。  
  
  > [!NOTE]
  >  tracelog.exe は Microsoft SDK に含まれており、BizTalk Adapter for PeopleSoft Enterprise で提供されるコマンドと互換性があります。 logman.exe の使い方については、logman のマニュアルを参照してください。  
  
- **コンシューマー アプリケーション**: 記録されたイベントの読み取り。  
  
   コンシューマー アプリケーションで .etl ファイル内のイベントを読み取るには、Windows イベント トレーシングでそれらのイベントを .etl ファイルにダンプする必要があります。 通常、この作業は、コントローラーがトレーシングを非アクティブ化するときに行われます。  
  
   コンシューマーを使用して、トレースを非アクティブ化せず、リアルタイム オプションでは、トレースで、コント ローラーによってアクティブ化する必要があります\<リアルタイム\>-rt を = です。  
  
- **プロバイダー:** イベントを提供します。  
  
   BizTalk Adapter for PeopleSoft Enterprise には、5 種類のプロバイダーがあります。 これらは Windows Management Instrumentation (WMI) に登録されます。 登録されているプロバイダーを検索する、 **root \wmi\eventtrace**パス、WMI CIM Studio などのツールを使用することができます。  
  
  BizTalk Adapter for PeopleSoft Enterprise には、5 つのプロバイダーが用意されており、種類の異なるメッセージをログに記録できます。  
  
- **受信側のログ記録プロバイダー**: \<Trace 要素\>スイッチが **-受信者**します。  
  
- **受信元 CastDetails プロバイダー**: \<Trace 要素\>スイッチが **- castDetailsReceive**します。  
  
- **送信元ログ プロバイダー**: \<Trace 要素\>スイッチが **-送信機**します。  
  
- **送信元 CastDetails プロバイダー**: \<Trace 要素\>スイッチが **- castDetailsTransmit**します。  
  
- **管理ログ プロバイダー**: \<Trace 要素\>スイッチが **-管理**します。  
  
## <a name="btapeoplesofttrace-command"></a>BTAPeopleSoftTrace コマンド  
 ETW を使用して、アダプターのコマンドを実行する**BTAPeopleSoftTrace.cmd**します。 このコマンドは次のように使用します。  
  
```  
BTAPeopleSoftTrace <Trace element> -start [-cir <MB>|   
    -seq <MB>] [-rt] logfile  
BTAPeopleSoftTrace <Trace element> -stop  
```  
  
 各要素の説明は次のとおりです。  
  
- \<Trace 要素\>プロバイダーの種類は、(必須)。  
  
   オプションは次のとおりです。  
  
  -   **-castDetailsTransmit**  
  
  -   **-送信機**  
  
  -   **-castDetailsReceive**  
  
  -   **-受信機**  
  
  -   **-管理**  
  
  -   **-開始、停止**: プロバイダーをアクティブまたは非アクティブです。  
  
- **-cir \<MB\>**: ファイルのサイズおよび種類。 -cir は循環ファイルです。 \<MB\>: サイズ (メガバイト単位)。  
  
- **-seq \<MB\>**: ファイルのサイズおよび種類。 -seq はシーケンシャル ファイルです。 \<MB\>: サイズ (メガバイト単位)。  
  
- **-rt**: のリアル タイム モードに設定します。  
  
- **ログ ファイル**: (既定では C:\rtlog.etl) ログ ファイルの名前。  
  
  以下に例を示します。  
  
```  
BTAPeopleSoftTrace -transmitter -start -cir 10 -rt C:\log\mylog.etl  
BTAPeopleSoftTrace -transmitter -stop  
```  
  
## <a name="see-also"></a>参照  
 [PeopleSoft のトラブルシューティング](../core/troubleshooting-peoplesoft.md)