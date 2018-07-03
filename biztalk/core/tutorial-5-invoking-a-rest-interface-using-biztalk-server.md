---
title: 'チュートリアル 5: BizTalk Server を使用して REST インターフェイスの呼び出し |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 73871ca3-abd0-45ae-b379-6df76a967a80
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d45daa5f567863fd3531edb1f951ac673628fd6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967571"
---
# <a name="tutorial-5-invoking-a-rest-interface-using-biztalk-server"></a>チュートリアル 5: BizTalk Server を使用して REST インターフェイスの呼び出し
このセクションでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を使用して REST エンドポイントを呼び出す方法の手順を説明します。 このチュートリアルでは、[!INCLUDE[winazure](../includes/winazure-md.md)] Marketplace から入手できる、米国航空会社のフライトの遅延を返す REST エンドポイントを呼び出します。 このチュートリアルは、新しい**Wcf-webhttp**でアダプターが導入された[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]REST エンドポイントを呼び出す。  
  
##  <a name="BKMK_Scenario"></a> このチュートリアルで使用するシナリオ  
 [!INCLUDE[winazure](../includes/winazure-md.md)] Marketplace では、米国航空会社のフライト遅延を取得する次の REST リソース URL が提供されています。  
  
```  
https://api.datamarket.azure.com/oakleaf/US_Air_Carrier_Flight_Delays_Incr/On_Time_Performance  
```  
  
 この URL を Web ブラウザーのアドレス バーに入力すると、リソースにアクセスするための資格情報の入力を求められます。 ログインした後、 [Windows Azure Marketplace](http://go.microsoft.com/fwlink/p/?LinkId=257913)から資格情報を取得することができます、**マイ アカウント**web ページのタブ。 に対して資格情報が一覧表示されます、**顧客 ID** (ユーザー名) と**プライマリ アカウント キー** (パスワード) ラベル。  
  
 このチュートリアルで使用するリソースの URL と資格情報を双方向を構成する**Wcf-webhttp**ポートを送信します。 双方向送信ポートの受信パイプラインは、フライト詳細情報を含む応答メッセージを受信し、メッセージを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] メッセージ ボックス データベースに公開します。 ユーザーは WCF-WebHttp 送信ポートによって公開されたすべてのメッセージをサブスクライブする FILE 送信ポートを構成します。 FILE 送信ポートは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] からのメッセージを取得し、それをファイルの場所にコピーします。  
  
 現実のビジネス シナリオでは、ビジネス アプリケーションからのメッセージを取得する受信場所のようなさらに大きいビジネス プロセスと関連付けることによって、WCF-WebHttp 送信ポートをトリガーできます。 ただし、このチュートリアルの目的は REST インターフェイスを呼び出す方法を示すことなので、ダミー メッセージを受信する簡単な FILE の場所を使用して、送信ポートをトリガーします。  
  
 要約すると、このソリューションを構成するには、次の手順を実行する必要があります。  
  
1.  ファイルを構成する受信場所をダミー要求メッセージを選択します。  
  
2.  REST リソース URL を呼び出して応答を受信するための、双方向 WCF-WebHttp 送信ポートを構成する  
  
3.  フライトの詳細を含む応答メッセージを取得してファイルの場所にコピーするための、一方向の FILE 送信ポートを構成する  
  
## <a name="set-up-your-includewinazureincludeswinazure-mdmd-marketplace-account"></a>[!INCLUDE[winazure](../includes/winazure-md.md)] Marketplace アカウントのセットアップ  
 REST エンドポイントを介して公開されているフライト遅延データにアクセスするには、US Air Carrier Flight Delays サンプル データ フィードをサブスクライブする必要があります。 そのためには、次の手順を実行します。  
  
#### <a name="to-subscribe-to-the-data-feed"></a>データ フィードをサブスクライブするには  
  
1. Microsoft アカウントを使用して [!INCLUDE[winazure](../includes/winazure-md.md)] Marketplace にログインします。  
  
2. **データ** タブを見つけて、クリックして、 **US Air Carrier Flight Delays**サービス。  
  
3. データ サービス ページで、次のようにクリックします。**サインアップ**します。 [サインアップ] ページで、契約の条項に同意し、**サインアップ**もう一度です。  
  
4. **マイ アカウント** タブで、データ サービスにアクセスする資格情報を取得します。 に対して資格情報が一覧表示されます、**顧客 ID** (ユーザー名) と**プライマリ アカウント キー** (パスワード) ラベル。 これらの資格情報を構成するときに必要があります、 **Wcf-webhttp**ポートを送信します。  
  
## <a name="set-up-your-computer"></a>コンピューターのセットアップ  
 このチュートリアルで使用するシナリオを構成するには、コンピューターに [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をインストールして構成する必要があります。 プロビジョニングする場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]にある指示に従って、Windows Azure VM 上のコンピューター [Azure VM での BizTalk Server の構成](http://msdn.microsoft.com/library/azure/jj248689.aspx)します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [手順 1: FILE 受信場所を構成する](../core/step-1-configure-a-file-receive-location.md)  
  
-   [手順 2: 双方向の WCF-WebHttp 送信ポートを構成する](../core/step-2-configure-a-two-way-wcf-webhttp-send-port.md)  
  
-   [手順 3: 一方向の FILE 送信ポートを構成する](../core/step-3-configure-a-one-way-file-send-port.md)  
  
-   [手順 4: ソリューションのテスト](../core/step-4-test-the-solution.md)