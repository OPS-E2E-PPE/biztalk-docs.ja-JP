---
title: WCF アダプターのパフォーマンス カウンター |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance, WCF adapters
- performance, performance counters
- WCF adapters, performance
ms.assetid: 9feb052f-5674-419f-84ab-9b5d312a04a5
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5b916b6212da18dcf4aa48d4ca941e23413513d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016253"
---
# <a name="wcf-adapters-performance-counters"></a>WCF アダプタのパフォーマンス カウンタ
パフォーマンス カウンタを使用すると、サービスによってサイトまたはシステムで実行されている作業の具体的な側面を監視できます。 パフォーマンス カウンターは、サーバー パフォーマンスに関する問題を特定してトラブルシューティングする際に役立ちます。 WCF アダプタ自体のパフォーマンス カウンタはありません。 しかし、Windows Communication Foundation (WCF) のパフォーマンス カウンタを監視して、WCF 受信場所のパフォーマンスを測定できます。 WCF 受信場所に対して WCF パフォーマンス カウンタを使用するには、受信場所を実行するホスト インスタンスのパフォーマンス カウンタを有効にする必要があります。  
  
> [!NOTE]
>  WCF パフォーマンス カウンタは、WCF 送信ポートでは使用できません。  
  
 インプロセス WCF アダプターの場合、パフォーマンス カウンターは BTSNTSvc.exe.config ファイルを使用して有効にすることができます。 分離 WCF アダプタの場合は、Web.config ファイルを変更してパフォーマンス カウンタを有効にすることができます。 WCF パフォーマンス カウンタの詳細についてを参照してください「WCF Performance Counters」 [ http://go.microsoft.com/fwlink/?LinkID=87245](http://go.microsoft.com/fwlink/?LinkID=87245)します。  
  
## <a name="enabling-the-wcf-performance-counters-for-the-wcf-receive-locations"></a>WCF 受信場所に対する WCF パフォーマンス カウンタの有効化  
 インプロセス WCF アダプターの場合、パフォーマンス カウンターは BTSNTSvc.exe.config ファイルを使用して有効にすることができます。  
  
 分離 WCF アダプタの場合は、BizTalk WCF サービス公開ウィザードによって Web アプリケーション フォルダに作成される Web.config ファイルを変更して、WCF 追跡を有効にすることができます。  
  
 BTSNtSvc.exe.config または Web.config を変更するには、構成ファイルを開き、次の構成例に示すように WCF 追跡を構成します。  
  
> [!NOTE]
>  BTSNTSvc.exe.config ファイルは常に BTSNTSvc.exe ファイルと同じディレクトリ (通常は [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]) に配置されます。  
  
```  
<configuration>  
 <system.serviceModel>  
 <diagnostics performanceCounters="All" />  
 </system.serviceModel>  
 </configuration>  
```  
  
 **PerformanceCounters**パフォーマンス カウンターの特定の種類を有効にする属性を設定することができます。 有効な値は  
  
- **すべて**: すべてのカテゴリ カウンター (**ServiceModelService**、 **ServiceModelEndpoint**、および**ServiceModelOperation**) を有効にします。  
  
- **ServiceOnly**: のみ**ServiceModelService**カテゴリのカウンターを有効にします。  
  
- **オフ**: ServiceModel * パフォーマンス カウンターが無効になっています。 これが既定値です。  
  
  BTSNTSvc.exe.config ファイルを変更した後、インプロセス WCF 受信場所を実行するホスト インスタンスを再起動する必要があります。  
  
## <a name="types-of-performance-counters"></a>パフォーマンス カウンタの種類  
 WCF パフォーマンス カウンタには、サービス、エンドポイント、および操作の 3 つのレベルがあります。  
  
 **サービスのパフォーマンス カウンター**  
  
 サービス パフォーマンス カウンタは、サービス動作全体を測定し、サービス全体のパフォーマンスを診断するために使用できます。 下にある、 **ServiceModelService 3.0.0.0**パフォーマンス モニターで表示するときにパフォーマンス オブジェクトです。 インスタンスには、次のパターンの名前が付けられています。  
  
```  
biztalkserviceinstance@<URI of a receive location>  
```  
  
 WCF アダプタは受信場所ごとに個別のサービス ホストを作成するので、各受信場所に対して 1 つのパフォーマンス カウンタ インスタンスが作成されます。 WCF を実装するサービス クラスの詳細については、サービス コントラクトを参照してください、 **BizTalkServiceInstance クラス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。 
  
 **エンドポイントのパフォーマンス カウンター**  
  
 エンドポイント パフォーマンス カウンタを使用すると、エンドポイントでのメッセージの受信状況を表すデータを参照できます。 下にある、 **ServiceModelEndpoint 3.0.0.0**パフォーマンス モニターで表示するときにパフォーマンス オブジェクトです。 インスタンスには、次のパターンの名前が付けられています。  
  
```  
biztalkserviceinstance.<WCF service contract>@<URI of a receive location>  
```  
  
 各受信場所に対して 1 つのパフォーマンス カウンタ インスタンスが作成されます。 上記のパターンでは、WCF サービス コントラクトの名前は、受信場所からメッセージを受信するために WCF アダプタで選択されたサービス コントラクトを表します。 WCF アダプターが使用可能な WCF からサービス コントラクトを選択する方法の詳細については、サービス コントラクトを参照してください**WCF アダプタ サービス コントラクト参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。  
  
 **操作パフォーマンス カウンター**  
  
 操作パフォーマンス カウンターは下にあります、 **ServiceModelOperation 3.0.0.0**パフォーマンス モニターで表示するときにパフォーマンス オブジェクトです。 各受信場所に対して 2 つのパフォーマンス カウンタ インスタンスが作成されます。 オブジェクト インスタンスの 1 つには、次のパターンを使用した名前が付けられます。  
  
```  
biztalkserviceinstance.<WCF service contract>biztalksubmit@<URI of a receive location>  
```  
  
 上記のパターンでは、WCF サービス コントラクトの名前は、受信場所からメッセージを受信するために WCF アダプタで選択されたサービス コントラクトを表します。 **biztalksubmit**サービス コントラクトで宣言された操作名であり、ランタイムがメタデータに WSDL 操作が作成されます。  
  
> [!NOTE]
>  WCF アダプターが使用可能な WCF からサービス コントラクトを選択する方法の詳細については、サービス コントラクトを参照してください**WCF アダプタ サービス コントラクト参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。
  
 もう 1 つのオブジェクト インスタンスには、次のパターンを使用した名前が付けられます。  
  
```  
biztalkserviceinstance.<WCF service contract><twowaymethod|onewaymethod>@<URI of a receive location>  
```  
  
 このパフォーマンス カウンタ インスタンスは、受信場所からの受信メッセージの非同期処理を行う操作を表します。 このインスタンスの操作名の部分を指定できます**twowaymethod**または**onewaymethod**受信場所で使用される WCF アダプターの種類によって異なります。 Wcf-netmsmq アダプターを使用する場合、インスタンスが、 **onewaymethod**操作名が作成されます。 その他のアダプターの**twowaymethod**操作名要素として使用されます。