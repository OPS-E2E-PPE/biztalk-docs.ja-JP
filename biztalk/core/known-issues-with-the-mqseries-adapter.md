---
title: MQSeries アダプターに関する既知の問題 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c36bcabb-e1eb-455c-8384-00d4682464d3
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be120ec58ebf6ecba62b333655373f3e02f8e487
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990241"
---
# <a name="known-issues-with-the-mqseries-adapter"></a>MQSeries アダプターに関する既知の問題
ここでは、エラー回避に役立つ情報を記載します。  
  
## <a name="know-issues"></a>既知の問題点  
  
#### <a name="access-denied-errors-occur-when-attempting-to-send-or-receive-messages"></a>メッセージの送信または受信を試行したときにアクセス拒否エラーが発生する  
  
##### <a name="problem"></a>問題  
 MQSeries アダプターを使用して MQSeries サーバーとの間でメッセージを送信または受信すると、イベント ビューアーのアプリケーション ログに次のようなメッセージが記録されます。  
  
```  
The adapter "MQSeries" raised an error message. Details "The adapter has encountered an 'Access Denied' error while attempting to contact the COM+ object on the MQSeries server. Ensure the BizTalk account is added to the Role on the MQSAgent COM+ application."  
```  
  
```  
The adapter failed to transmit message going to send port "MQS://servername/queuename". It will be retransmitted after the retry interval specified for this Send Port. Details: "The adapter has encountered an 'Access Denied' error while attempting to contact the COM+ object on the MQSeries server. Ensure the BizTalk account is added to the Role on the MQSAgent COM+ application."  
```  
  
> [!NOTE]
>  このエラー メッセージで*servername* 、サーバーの名前を指定し、 *queuename*キューの名前を指定します。  
  
 さらに、BizTalk Adapter for MQSeries を使用する構成で受信場所または送信ポートを作成しようとすると、イベント ビューアーに次の警告メッセージが表示されることがあります。  
  
```  
The adapter "MQSeries" raised an error message. Details "The adapter has encountered an 'Access Denied' error while attempting to contact the COM+ object on the MQSeries server. Ensure the BizTalk account is added to the Role on the MQSAgent COM+ application."  
```  
  
##### <a name="cause"></a>原因  
 この問題は、1 つの場合に発生する可能性があります。 または true は、次の条件の詳細。  
  
- MQSeries アダプターのホスト アカウントに、MQSeries サーバー上の MQSAgent COM+ アプリケーションに必要なアクセス許可がない。  
  
- [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] または [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] ベースのサーバー上で、MQSeries アダプターのホスト アカウントが、MQSeries サーバーの分散 COM ユーザー グループのメンバーになっていない。  
  
##### <a name="resolution"></a>解決策  
 この問題を解決するには、次の方法を使用します。 最初の方法から試し、問題を解決できなかった場合は次の方法を試してください。  
  
 **方法 1: microsoft ネットワーク COM + アクセスを有効にする[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]または[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]-ベースのコンピューター**  
  
 Microsoft でネットワーク COM + アクセスを有効にする[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]または[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]-ベースのコンピューターに記載の手順に従って[Windows Server 2003 でネットワーク COM + アクセスを有効にする方法](http://go.microsoft.com/fwlink/?LinkId=67076)します。  
  
 **方法 2: MSDTC 設定を構成します。**  
  
 手順に従って、**適切な MSDTC セキュリティ構成オプションの設定[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]** のセクション[MSDTC を使用した問題のトラブルシューティング](../core/troubleshooting-problems-with-msdtc.md)MSDTC 設定を構成します。  
  
 **方法 3: ホスト アカウントが MQSAgent COM + アプリケーション ロールに追加されていることを確認します**  
  
 MQSeries アダプターのホスト アカウントが、MQSeries サーバー上の MQSAgent COM+ アプリケーションに作成されたロールに追加されていることを確認します。 これは [コンポーネント サービス] 管理コンソール インターフェイスで確認できます。  
  
 **方法 4: の場合、MQSeries アダプターのホスト アカウントが Distributed COM Users グループのメンバーであることを確認します。**  
  
 Windows [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] または [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] ベースのサーバーで、MQSeries アダプターのホスト アカウントのグループ メンバーシップを確認します。 アカウントがのメンバーであることを確認、 **Distributed COM Users** MQSAgent COM + アプリケーションがインストールされている MQSeries サーバーでグループ化します。  
  
 Microsoft の DCOM セキュリティ強化の詳細については[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]を参照してください[DCOM のセキュリティが強化された](http://go.microsoft.com/fwlink/?LinkId=67077)します。  
  
## <a name="see-also"></a>参照  
 [MQSeries アダプターのトラブルシューティング](../core/troubleshooting-the-mqseries-adapter.md)