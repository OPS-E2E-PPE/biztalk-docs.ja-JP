---
title: デジタル署名用証明書をインストールする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 910ccd84-c022-46a5-a9de-b99046a480b8
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3bec4fd58532201efc430855464a90f03a824400
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384906"
---
# <a name="how-to-install-the-certificates-for-digital-signatures"></a>デジタル署名用証明書をインストールする方法
次の手順では、署名付きメッセージの送受信用の証明書をインストールするために従う必要のある手順の概要を示します。  
  
-   署名付きメッセージを受信するための証明書を証明書ストアにインストールするには  
  
-   証明書ストアに署名付きメッセージを送信するための署名証明書をインストールするには  
  
-   署名付きメッセージを送信するための BizTalk グループを構成するには  
  
> [!NOTE]
>  署名および解読操作の両方に 1 つの証明書を使用することも、機能ごとに 1 つの証明書を使用することもできます。  
> 
> [!IMPORTANT]
>  1 つの署名証明書を指定できますのみ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]すべての送信メッセージに署名します。 つまりにメッセージを送信するユーザーによって別の署名証明書を使用することはできません。  
  
### <a name="to-install-the-certificates-in-the-certificates-store-to-receive-signed-messages"></a>署名付きメッセージを受信するための証明書を証明書ストアにインストールするには  
  
1. パートナー A は、証明機関 (CA) にデジタル署名用の公開キーと秘密キーのペアを要求します。  
  
2. パートナー A は、ユーザーにデジタル署名用の公開キーを送信します。  
  
3. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で、パートナー A からのメッセージを受信するハンドラーを実行中のホスト インスタンスを含むサーバーにログオンします。パートナー A の公開キー証明書をインストールして、"その他のユーザー" ストアの署名を検証します。 次の図に、証明書をインストールする証明書ストアを示します。  
  
    ![セキュリティで保護されたメッセージを受信するために必要な証明書](../core/media/bpi-sp-msgsec-certmgmt-certstores-receive.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Receive")  
  
4. パートナー A で、適切なストアでメッセージに署名するためにパートナー A の秘密キー証明書をインストールします  (パートナー A が使用されている場合[!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)]、 [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]、または[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]に送信されるメッセージに署名するアカウントの個人用ストアに秘密キーをインストール[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)])。  
  
### <a name="to-install-the-signing-certificates-for-sending-signed-messages-in-the-certificates-store"></a>証明書ストアに署名付きメッセージを送信するための署名証明書をインストールするには  
  
1. 組織の管理者の CA に対してデジタル署名用の/秘密キー ペアを要求する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を使用します。  
  
2. 管理者は、パートナー A (およびその他のすべてのパートナー) にもデジタル署名の公開キーを送信します。  
  
3. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、A. をインストール パートナーにメッセージを送信するハンドラーを実行するホスト インスタンスのサービス アカウントとしてログオン、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]サービス アカウントの個人用ストア内のメッセージに署名するための秘密キー証明書。 次の図に、証明書をインストールする証明書ストアを示します。  
  
    ![セキュリティで保護されたメッセージを送信するために必要な証明書](../core/media/bpi-sp-msgsec-certmgmt-certstores-send.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Send")  
  
4. パートナー A では、インストール、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]適切なストアでデジタル署名を検証するための公開キー証明書。 (パートナー A が使用されている場合[!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)]、 [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]、または[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]、他のユーザー ストアで公開キーをインストールします)。  
  
### <a name="to-configure-the-biztalk-group-for-sending-signed-messages"></a>署名付きメッセージを送信するための BizTalk グループを構成するには  
  
1. をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. 右クリック**BizTalk グループ**、 をクリックし、**プロパティ**します。  
  
3. **グループのプロパティ**ダイアログ ボックスで、をクリックして**証明書**、 をクリックして**参照**します。  
  
4. **証明書の選択**ダイアログ ボックスがインストールした署名証明書を選択し、すべてのダイアログ ボックスを閉じます。  
  
## <a name="next-steps"></a>次の手順  
 署名付きメッセージを受信するためのパイプラインを作成する[署名付きメッセージの受信用の BizTalk Server を構成する方法](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md)します。  
  
 署名付きメッセージを送信するためのパイプラインを作成する[署名付きメッセージの送信用の BizTalk Server を構成する方法](../core/how-to-configure-biztalk-server-for-sending-signed-messages.md)します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server は、署名付きメッセージで使用する証明書](../core/certificates-that-biztalk-server-uses-for-signed-messages.md)   
 [署名付きメッセージの送受信](../core/sending-and-receiving-signed-messages.md)