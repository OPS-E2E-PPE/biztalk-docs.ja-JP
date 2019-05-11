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
ms.openlocfilehash: 04a9aa02d0206f4edb5b50943718b6c62d647966
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395945"
---
# <a name="wcf-adapters-performance-counters"></a>WCF アダプターのパフォーマンス カウンター
パフォーマンス カウンターを使用すると、サービスによってサイトまたはシステムで実行される作業の具体的な側面を監視できます。 パフォーマンス カウンターは、サーバー パフォーマンスに関する問題を特定してトラブルシューティングする際に役立ちます。 WCF アダプタは、独自のパフォーマンス カウンターを提供してください。 ただし、パフォーマンスを監視することが受信場所のカウンターの Windows Communication Foundation (WCF)、WCF のパフォーマンスを測定します。 を、WCF 受信場所に対する WCF パフォーマンス カウンタを使用するには、受信場所を実行するホスト インスタンスのパフォーマンス カウンターを有効にする必要があります。  
  
> [!NOTE]
>  WCF 送信ポートの WCF パフォーマンス カウンタが利用できません。  
  
 インプロセス WCF アダプターの場合、パフォーマンス カウンターは BTSNTSvc.exe.config ファイルを使用して有効にすることができます。 分離 WCF アダプタでは、パフォーマンス カウンターを有効にするために Web.config ファイルを変更できます。 WCF パフォーマンス カウンタの詳細についてを参照してください「WCF Performance Counters」 [ http://go.microsoft.com/fwlink/?LinkID=87245](http://go.microsoft.com/fwlink/?LinkID=87245)します。  
  
## <a name="enabling-the-wcf-performance-counters-for-the-wcf-receive-locations"></a>WCF 受信場所に対して WCF パフォーマンス カウンタを有効にします。  
 インプロセス WCF アダプターの場合、パフォーマンス カウンターは BTSNTSvc.exe.config ファイルを使用して有効にすることができます。  
  
 分離 WCF アダプタでは、Web アプリケーション フォルダーで、BizTalk WCF サービス公開ウィザードを作成する Web.config ファイルを変更して WCF トレースを有効ことができます。  
  
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
  
- **[すべて]**: すべてのカテゴリ カウンター (**ServiceModelService**、 **ServiceModelEndpoint**、および**ServiceModelOperation**) を有効にします。  
  
- **ServiceOnly**:のみ**ServiceModelService**カテゴリのカウンターを有効にします。  
  
- **Off**:ServiceModel * パフォーマンス カウンターが無効です。 これが既定値です。  
  
  BTSNTSvc.exe.config ファイルを変更した後、インプロセス WCF 受信場所を実行するホスト インスタンスを再起動する必要があります。  
  
## <a name="types-of-performance-counters"></a>パフォーマンス カウンターの種類  
 次の 3 つの異なるレベルのスコープは WCF パフォーマンス カウンタ: サービス、エンドポイント、および操作します。  
  
 **サービスのパフォーマンス カウンター**  
  
 サービスのパフォーマンス カウンターは、サービス動作全体を測定し、サービス全体のパフォーマンスの診断に使用できます。 下にある、 **ServiceModelService 3.0.0.0**パフォーマンス モニターで表示するときにパフォーマンス オブジェクトです。 インスタンスの名前には、次のパターンを使用します。  
  
```  
biztalkserviceinstance@<URI of a receive location>  
```  
  
 WCF アダプタは、各受信場所に対して個別のサービス ホストを作成するため、各受信場所に対してにパフォーマンス カウンターのインスタンスが作成されます。 WCF を実装するサービス クラスの詳細については、サービス コントラクトを参照してください、 **BizTalkServiceInstance クラス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。 
  
 **エンドポイントのパフォーマンス カウンター**  
  
 エンドポイントのパフォーマンス カウンターでは、エンドポイントがメッセージを受信する方法を表すデータを確認することができます。 下にある、 **ServiceModelEndpoint 3.0.0.0**パフォーマンス モニターで表示するときにパフォーマンス オブジェクトです。 インスタンスの名前には、次のパターンを使用します。  
  
```  
biztalkserviceinstance.<WCF service contract>@<URI of a receive location>  
```  
  
 各受信場所に対しては、パフォーマンス カウンターのインスタンスが作成されます。 上記のパターンでは、WCF サービス コントラクトの名前は、受信場所からメッセージを受信する WCF アダプターを選択するサービス コントラクトを表します。 WCF アダプターが使用可能な WCF からサービス コントラクトを選択する方法の詳細については、サービス コントラクトを参照してください**WCF アダプタ サービス コントラクト参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。  
  
 **操作パフォーマンス カウンター**  
  
 操作パフォーマンス カウンターは下にあります、 **ServiceModelOperation 3.0.0.0**パフォーマンス モニターで表示するときにパフォーマンス オブジェクトです。 各受信場所に対して、2 つのパフォーマンス カウンターのインスタンスが作成されます。 次のパターンを使用してオブジェクト インスタンスの 1 つの名前は。  
  
```  
biztalkserviceinstance.<WCF service contract>biztalksubmit@<URI of a receive location>  
```  
  
 上記のパターンでは、WCF サービス コントラクトの名前は、受信場所からメッセージを受信する WCF アダプターを選択するサービス コントラクトを表します。 **biztalksubmit**サービス コントラクトで宣言された操作名であり、ランタイムがメタデータに WSDL 操作が作成されます。  
  
> [!NOTE]
>  WCF アダプターが使用可能な WCF からサービス コントラクトを選択する方法の詳細については、サービス コントラクトを参照してください**WCF アダプタ サービス コントラクト参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。
  
 次のパターンを使用して、その他のオブジェクト インスタンスの名前は。  
  
```  
biztalkserviceinstance.<WCF service contract><twowaymethod|onewaymethod>@<URI of a receive location>  
```  
  
 このパフォーマンス カウンター インスタンスは、受信場所を介して受信するメッセージを非同期的に処理する操作を表します。 このインスタンスの操作名の部分を指定できます**twowaymethod**または**onewaymethod**受信場所で使用される WCF アダプターの種類によって異なります。 Wcf-netmsmq アダプターを使用する場合、インスタンスが、 **onewaymethod**操作名が作成されます。 その他のアダプターの**twowaymethod**操作名要素として使用されます。