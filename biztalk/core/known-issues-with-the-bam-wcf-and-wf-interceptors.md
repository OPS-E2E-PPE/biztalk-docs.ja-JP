---
title: BAM WCF インターセプターと WF インターセプターに関する既知の問題 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2407809-1f71-41a9-b305-722a7f86af5b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b938dff130ae08e75f54fc1b619fad109515a5d4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330066"
---
# <a name="known-issues-with-the-bam-wcf-and-wf-interceptors"></a>BAM WCF インターセプタと WF インターセプタに関する既知の問題
このセクションでは、Windows Workflow Foundation または Windows Communication Foundation の BAM インターセプタを使用する場合に発生する可能性がある既知の問題に関する情報を提供します。  
  
## <a name="intercepting-a-dynamically-generated-wcf-assembly-hosted-in-iis"></a>IIS でホストされる動的に生成された WCF アセンブリをインターセプト  
 IIS を使用して、埋め込みの Windows Communication Foundation アプリケーション (たとえば、アセンブリのソースを指定するサービス ファイル) をホストする場合は、WCF アセンブリが動的に生成、任意のファイル名、および asp.net で配置された割り当てられています。一時フォルダーです。 サービスを再コンパイルし、ビルドする必要があります、インターセプタ構成ファイルには、マニフェスト情報が必要なため、およびワイルドカード文字またはマニフェストを指定するための他の動的メソッドはインターセプター構成ファイルで使用できないため、すべてを含む asp.net web ページの展開した後、インターセプタ構成ファイル、インターセプター構成ファイルや再デプロイには、WCF コードが埋め込まれます。  
  
## <a name="use-of-the-bam-interceptor-for-windows-workflow-foundation-is-not-supported-in-office-and-sharepoint-server"></a>Office および Sharepoint Server for Windows Workflow Foundation BAM インターセプターの使用はサポートされていません  
 Office と Windows Sharepoint のサーバーの両方から読み取りませんアプリケーション構成ファイル、WF ランタイムを初期化するときにします。 その結果、アプリケーションの WF の BAM インターセプタを構成することがありますが、これらの環境でホストされている場合は、ワークフロー ランタイムに読み込まれません。  
  
## <a name="client-service-locks-when-intiating-a-distributed-transaction"></a>クライアント サービスがロックする分散トランザクションの開始時  
 サービス操作がクライアントによって開始されたトランザクションに参加していませんが、クライアントがトランザクション スコープのコンテキストからサービスを呼び出す場合は、デッドロックが発生し、前に、クライアントから収集されるデータがある場合は特に、要求を送信し、同じアクティビティに関する受信-要求によってサービスから。  
  
 このような状況を避けるためには、クライアントが宣言することでのトランザクションに参加しないことを指定する必要があります"Enlist = false"、クライアントで`ConnectionString`次に示すように、クライアントの app.config ファイルで BAM 動作拡張機能の属性します。  
  
```  
<behavior name="bamClientBehavior">  
  <bamClientBehaviorExtension ConnectionString="Integrated Security=SSPI;Initial Catalog=BAMPrimaryImport;Data Source=.;  Enlist=false"  PollingIntervalSec="1500" />  
</behavior>  
```  
  
## <a name="open-wcf-channel-before-sending-a-message-when-bam-interceptors-are-used"></a>BAM インターセプタを使用する場合、WCF チャネルの送信前に、メッセージを開く  
 BasicHttp のバインディングでの WCF に BAM インターセプターが有効な場合、プロキシは、プロキシを呼び出す必要があります。Open() を明示的にチャネルを開きます。 チャネルが明示的に開かれていない、BAM インターセプションは例外で失敗します。