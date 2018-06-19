---
title: BAM WCF インターセプタと WF インターセプタに関する既知の問題 |Microsoft ドキュメント
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
ms.openlocfilehash: 42078eb2b1272072016ded9a117e88ddf4fda038
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262026"
---
# <a name="known-issues-with-the-bam-wcf-and-wf-interceptors"></a>BAM WCF インターセプタと WF インターセプタに関する既知の問題
このセクションでは、Windows Workflow Foundation または Windows Communication Foundation の BAM インターセプタを使用する際に発生する可能性がある既知の問題について説明します。  
  
## <a name="intercepting-a-dynamically-generated-wcf-assembly-hosted-in-iis"></a>IIS でホストされている WCF アセンブリ (動的に生成されたもの) を受け取る  
 IIS を使用して埋め込み型の Windows Communication Foundation アプリケーション (たとえば、アセンブリ ソースを指定するサービス ファイルなど) を使用している場合、WCF アセンブリが動的に生成され、任意のファイル名を割り当てられて、asp.net の一時フォルダに配置されます。 インターセプター構成ファイルがマニフェスト情報を必要とするため、およびワイルドカード文字や、マニフェストを指定するための他の動的メソッドはインターセプター構成ファイルで使用可能ではないため、する必要があります、サービスを再コンパイルし、し、ビルドインターセプター構成ファイル、または再展開した後、インターセプター構成ファイルにデプロイを含む asp.net web ページのすべての WCF コードに埋め込まれます。  
  
## <a name="use-of-the-bam-interceptor-for-windows-workflow-foundation-is-not-supported-in-office-and-sharepoint-server"></a>Windows Workflow Foundation の BAM インターセプタが Office および Sharepoint Server でサポートされない  
 Office と Windows Sharepoint Server はいずれも、WF ランタイムを初期化するときにアプリケーション構成ファイルを読み込みません。 WF の BAM インターセプタはアプリケーション用に構成されますが、これらの環境でホストされるときにワークフロー ランタイムに読み込まれません。  
  
## <a name="client-service-locks-when-intiating-a-distributed-transaction"></a>分散トランザクションの開始時にクライアント サービスがロックする  
 クライアントによって開始されたトランザクションにサービス操作が参加しておらず、クライアントがこのサービスをトランザクション スコープのコンテキストから開始したときは、デッドロックが発生することがあります。特に、送信 - 要求の前にクライアントから収集されたデータと、同じアクティビティに関する受信 - 要求によってサービスから収集されたデータが存在する場合は、デッドロックが発生する確率が高くなります。  
  
 このような状況を回避するには、クライアントがトランザクションに参加しないように指定します。これを行うには、次に示すように、クライアントの app.config ファイルで BAM 動作拡張機能に関するクライアントの `ConnectionString` 属性で "Enlist = false" を宣言します。  
  
```  
<behavior name="bamClientBehavior">  
  <bamClientBehaviorExtension ConnectionString="Integrated Security=SSPI;Initial Catalog=BAMPrimaryImport;Data Source=.;  Enlist=false"  PollingIntervalSec="1500" />  
</behavior>  
```  
  
## <a name="open-wcf-channel-before-sending-a-message-when-bam-interceptors-are-used"></a>BAM インターセプターを使用するとメッセージの送信前に WCF チャネルが開く  
 BasicHttp バインドを適用した WCF で BAM インターセプターを有効にすると、プロキシにより proxy.Open() が呼び出され、チャネルが明示的に開きます。 チャネルが明示的に開かない場合、BAM インターセプションに失敗し、例外が発生することがあります。