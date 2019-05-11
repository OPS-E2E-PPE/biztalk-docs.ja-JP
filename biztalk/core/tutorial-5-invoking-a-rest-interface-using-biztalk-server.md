---
title: チュートリアル 5:BizTalk Server を使用して REST インターフェイスの呼び出し |Microsoft Docs
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
ms.openlocfilehash: 4688f550c78a561a85c4ca8288ab8ef6e6d264f8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399173"
---
# <a name="tutorial-5-invoking-a-rest-interface-using-biztalk-server"></a>チュートリアル 5:BizTalk Server を使用して REST インターフェイスの呼び出し
このセクションを使用して REST エンドポイントを呼び出す方法の詳細なチュートリアルを提供する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 このチュートリアルではから利用できる REST エンドポイントを呼び出す、 [!INCLUDE[winazure](../includes/winazure-md.md)] Marketplace を航空会社のフライト米国の遅延を返します。 このチュートリアルは、新しい**Wcf-webhttp**でアダプターが導入された[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]REST エンドポイントを呼び出す。  
  
##  <a name="BKMK_Scenario"></a> このチュートリアルで使用するシナリオ  
 [!INCLUDE[winazure](../includes/winazure-md.md)] Marketplace は、次を提供します米国航空会社のフライトの遅延を取得する REST リソース URL:。  
  
```  
https://api.datamarket.azure.com/oakleaf/US_Air_Carrier_Flight_Delays_Incr/On_Time_Performance  
```  
  
 Web ブラウザーのアドレス バーにこの URL を入力する場合は、リソースへのアクセスの資格情報を求められます。 ログインした後、 [Windows Azure Marketplace](http://go.microsoft.com/fwlink/p/?LinkId=257913)から資格情報を取得することができます、**マイ アカウント**web ページのタブ。 に対して資格情報が表示されている、**顧客 ID** (ユーザー名) と**プライマリ アカウント キー** (パスワード) ラベル。  
  
 このチュートリアルで使用するリソースの URL と資格情報を双方向を構成する**Wcf-webhttp**ポートを送信します。 双方向の送信ポートの受信パイプラインは、フライトの詳細を応答メッセージを受信しは、メッセージを公開、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージ ボックス データベースです。 Wcf-webhttp 送信ポートによって公開されるすべてのメッセージをサブスクライブする FILE 送信ポートを構成するとします。 FILE 送信ポートからメッセージを使用する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]し、ファイルの場所にコピーします。  
  
 実際のビジネス シナリオでは、ビジネス アプリケーションからメッセージを取得する受信場所などの大規模なビジネス プロセスに関連付けることによって、Wcf-webhttp 送信ポートをトリガーできます。 ただし、このチュートリアルでの焦点は、REST インターフェイスを呼び出す方法を示すためすることができますを使用して、送信ポートをトリガーするダミー メッセージを受信する単純なファイルの場所。  
  
 そのため、要約すると、このソリューションを構成するのには、次の手順を実行する必要があります。  
  
1.  ファイルを構成する受信場所をダミー要求メッセージを選択します。  
  
2.  REST リソース URL を呼び出すし、応答を受信する双方向の Wcf-webhttp 送信ポートを構成します。  
  
3.  フライトの詳細を含む応答メッセージを使用し、ファイルの場所にコピーする一方向 FILE 送信ポートを構成します。  
  
## <a name="set-up-your-includewinazureincludeswinazure-mdmd-marketplace-account"></a>セットアップ、 [!INCLUDE[winazure](../includes/winazure-md.md)] Marketplace アカウント  
 REST エンドポイントを介して公開されているフライト遅延データにアクセスするには、まず、US Air Carrier Flight Delays サンプル データ フィードを購読する必要があります。 そのためには、次の手順を実行します。  
  
#### <a name="to-subscribe-to-the-data-feed"></a>データ フィードを購読するには  
  
1. ログイン、 [!INCLUDE[winazure](../includes/winazure-md.md)] Marketplace が Microsoft アカウントを使用します。  
  
2. **データ** タブを見つけて、クリックして、 **US Air Carrier Flight Delays**サービス。  
  
3. データ サービス ページで、次のようにクリックします。**サインアップ**します。 [サインアップ] ページで、契約の条項に同意し、**サインアップ**もう一度です。  
  
4. **マイ アカウント** タブで、データ サービスにアクセスする資格情報を取得します。 に対して資格情報が表示されている、**顧客 ID** (ユーザー名) と**プライマリ アカウント キー** (パスワード) ラベル。 これらの資格情報を構成するときに必要があります、 **Wcf-webhttp**ポートを送信します。  
  
## <a name="set-up-your-computer"></a>コンピューターをセットアップします。  
 このチュートリアルが必要で使用するシナリオを構成する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]お使いのコンピューターにインストールして構成します。 プロビジョニングする場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]にある指示に従って、Windows Azure VM 上のコンピューター [Azure VM での BizTalk Server の構成](http://msdn.microsoft.com/library/azure/jj248689.aspx)します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [ステップ 1: ファイルを構成する受信場所](../core/step-1-configure-a-file-receive-location.md)  
  
-   [手順 2:双方向の Wcf-webhttp 送信ポートを構成します。](../core/step-2-configure-a-two-way-wcf-webhttp-send-port.md)  
  
-   [ステップ 3:一方向 FILE 送信ポートを構成します。](../core/step-3-configure-a-one-way-file-send-port.md)  
  
-   [手順 4:ソリューションをテストします。](../core/step-4-test-the-solution.md)