---
title: WCF アダプタのパフォーマンス カウンタ |Microsoft ドキュメント
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
ms.openlocfilehash: 236eaed7401c79540274e0419b99d14d0f128332
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289474"
---
# <a name="wcf-adapters-performance-counters"></a>WCF アダプタのパフォーマンス カウンタ
パフォーマンス カウンタを使用すると、サービスによってサイトまたはシステムで実行されている作業の具体的な側面を監視できます。 パフォーマンス カウンターは、サーバー パフォーマンスに関する問題を特定してトラブルシューティングする際に役立ちます。 WCF アダプタ自体のパフォーマンス カウンタはありません。 しかし、Windows Communication Foundation (WCF) のパフォーマンス カウンタを監視して、WCF 受信場所のパフォーマンスを測定できます。 WCF 受信場所に対して WCF パフォーマンス カウンタを使用するには、受信場所を実行するホスト インスタンスのパフォーマンス カウンタを有効にする必要があります。  
  
> [!NOTE]
>  WCF パフォーマンス カウンタは、WCF 送信ポートでは使用できません。  
  
 インプロセス WCF アダプターの場合、パフォーマンス カウンターは BTSNTSvc.exe.config ファイルを使用して有効にすることができます。 分離 WCF アダプタの場合は、Web.config ファイルを変更してパフォーマンス カウンタを有効にすることができます。 WCF パフォーマンス カウンタの詳細についてにある「WCF Performance Counters」を参照してください。 [http://go.microsoft.com/fwlink/?LinkID=87245](http://go.microsoft.com/fwlink/?LinkID=87245)です。  
  
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
  
-   **すべて**: すべてのカテゴリ カウンタ (**ServiceModelService**、 **ServiceModelEndpoint**、および**ServiceModelOperation**) を有効にします。  
  
-   **ServiceOnly**: のみ**ServiceModelService**カテゴリ カウンターを有効にします。  
  
-   **オフ**: ServiceModel * パフォーマンス カウンターが無効です。 これが既定値です。  
  
 BTSNTSvc.exe.config ファイルを変更した後、インプロセス WCF 受信場所を実行するホスト インスタンスを再起動する必要があります。  
  
## <a name="types-of-performance-counters"></a>パフォーマンス カウンタの種類  
 WCF パフォーマンス カウンタには、サービス、エンドポイント、および操作の 3 つのレベルがあります。  
  
 **サービスのパフォーマンス カウンター**  
  
 サービス パフォーマンス カウンタは、サービス動作全体を測定し、サービス全体のパフォーマンスを診断するために使用できます。 下にある、 **ServiceModelService 3.0.0.0**パフォーマンス オブジェクトとパフォーマンス モニターを使用して表示します。 インスタンスには、次のパターンの名前が付けられています。  
  
```  
biztalkserviceinstance@<URI of a receive location>  
```  
  
 WCF アダプタは受信場所ごとに個別のサービス ホストを作成するので、各受信場所に対して 1 つのパフォーマンス カウンタ インスタンスが作成されます。 WCF を実装するサービス クラスの詳細については、サービス コントラクトを参照してください、 **BizTalkServiceInstance クラス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。 
  
 **エンドポイントのパフォーマンス カウンター**  
  
 エンドポイント パフォーマンス カウンタを使用すると、エンドポイントでのメッセージの受信状況を表すデータを参照できます。 下にある、 **ServiceModelEndpoint 3.0.0.0**パフォーマンス オブジェクトとパフォーマンス モニターを使用して表示します。 インスタンスには、次のパターンの名前が付けられています。  
  
```  
biztalkserviceinstance.<WCF service contract>@<URI of a receive location>  
```  
  
 各受信場所に対して 1 つのパフォーマンス カウンタ インスタンスが作成されます。 上記のパターンでは、WCF サービス コントラクトの名前は、受信場所からメッセージを受信するために WCF アダプタで選択されたサービス コントラクトを表します。 WCF アダプタが使用可能な WCF からサービス コントラクトを選択する方法の詳細については、サービス コントラクトを参照してください**WCF アダプタ サービス コントラクト参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。  
  
 **操作パフォーマンス カウンター**  
  
 操作パフォーマンス カウンターは下にあります、 **ServiceModelOperation 3.0.0.0**パフォーマンス オブジェクトとパフォーマンス モニターを使用して表示します。 各受信場所に対して 2 つのパフォーマンス カウンタ インスタンスが作成されます。 オブジェクト インスタンスの 1 つには、次のパターンを使用した名前が付けられます。  
  
```  
biztalkserviceinstance.<WCF service contract>biztalksubmit@<URI of a receive location>  
```  
  
 上記のパターンでは、WCF サービス コントラクトの名前は、受信場所からメッセージを受信するために WCF アダプタで選択されたサービス コントラクトを表します。 **biztalksubmit**サービス コントラクトで宣言されている操作名であり、メタデータに WSDL 操作を作成するランタイム。  
  
> [!NOTE]
>  WCF アダプタが使用可能な WCF からサービス コントラクトを選択する方法の詳細については、サービス コントラクトを参照してください**WCF アダプタ サービス コントラクト参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。
  
 もう 1 つのオブジェクト インスタンスには、次のパターンを使用した名前が付けられます。  
  
```  
biztalkserviceinstance.<WCF service contract><twowaymethod|onewaymethod>@<URI of a receive location>  
```  
  
 このパフォーマンス カウンタ インスタンスは、受信場所からの受信メッセージの非同期処理を行う操作を表します。 このインスタンスの操作名の部分を指定できます**twowaymethod**または**onewaymethod**受信場所で使用される WCF アダプターの種類によって異なります。 Wcf-netmsmq アダプターを使用する場合、インスタンスを持つ、 **onewaymethod**操作名を作成します。 他のアダプターの**twowaymethod**操作名の部分を使用します。