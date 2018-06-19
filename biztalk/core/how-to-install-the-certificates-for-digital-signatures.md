---
title: デジタル署名の証明書をインストールする方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 7a755e59c7c916f3abe037513ddbc9e2a89892fb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255162"
---
# <a name="how-to-install-the-certificates-for-digital-signatures"></a>デジタル署名用の証明書をインストールする方法
署名付きのメッセージを送受信するための証明書をインストールする手順の概要を次に示します。  
  
-   署名付きメッセージを受信するための証明書を証明書ストアにインストールするには  
  
-   署名付きメッセージを送信するための署名証明書を証明書ストアにインストールするには  
  
-   署名付きメッセージを送信できるように BizTalk グループを構成するには  
  
> [!NOTE]
>  署名および解読操作の両方に 1 つの証明書を使用することも、機能ごとに 1 つの証明書を使用することもできます。  
  
> [!IMPORTANT]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] がすべての送信メッセージの署名に使用する署名証明書は 1 つだけ指定できます。 つまり、メッセージの送信先によって異なる署名証明書を使用することはできません。  
  
### <a name="to-install-the-certificates-in-the-certificates-store-to-receive-signed-messages"></a>署名付きメッセージを受信するための証明書を証明書ストアにインストールするには  
  
1.  パートナー A は、証明機関 (CA) にデジタル署名用の公開キーと秘密キーのペアを要求します。  
  
2.  パートナー A は、ユーザーにデジタル署名用の公開キーを送信します。  
  
3.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で、パートナー A からのメッセージを受信するハンドラーを実行中のホスト インスタンスを含むサーバーにログオンします。パートナー A の公開キー証明書をインストールして、"その他のユーザー" ストアの署名を検証します。 次の図に、証明書をインストールする証明書ストアを示します。  
  
     ![セキュリティで保護されたメッセージの受信に必要な証明書](../core/media/bpi-sp-msgsec-certmgmt-certstores-receive.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Receive")  
  
4.  パートナー A で、適切なストアでメッセージに署名するためにパートナー A の秘密キー証明書をインストールします  (パートナー A が [!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)]、[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]、または [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] を使用している場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に送信されるメッセージに署名するアカウントの個人用ストアに秘密キーをインストールします)。  
  
### <a name="to-install-the-signing-certificates-for-sending-signed-messages-in-the-certificates-store"></a>署名付きメッセージを送信するための署名証明書を証明書ストアにインストールするには  
  
1.  組織の管理者は、使用する [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の CA に対してデジタル署名用の公開キーと秘密キーのペアを要求します。  
  
2.  管理者はパートナー A (および他のすべてのパートナー) に、デジタル署名用の公開キーを送信します。  
  
3.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で、パートナー A にメッセージを送信するハンドラーを実行中のホスト インスタンスのサービス アカウントとしてログオンします。サービス アカウントの個人用ストアでメッセージに署名するための [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 秘密キー証明書をインストールします。 次の図に、証明書をインストールする証明書ストアを示します。  
  
     ![セキュリティで保護されたメッセージの送信に必要な証明書](../core/media/bpi-sp-msgsec-certmgmt-certstores-send.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Send")  
  
4.  パートナー A で、適切なストアでデジタル署名を検証するために、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の公開キー証明書をインストールします (パートナー A が [!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)]、[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]、または [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] を使用している場合は、"その他のユーザー" ストアに公開キーをインストールします)。  
  
### <a name="to-configure-the-biztalk-group-for-sending-signed-messages"></a>署名付きメッセージを送信できるように BizTalk グループを構成するには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  右クリック**BizTalk グループ**、クリックして**プロパティ**です。  
  
3.  **グループのプロパティ**ダイアログ ボックスで、をクリックして**証明書**、 をクリックして**参照**です。  
  
4.  **証明書の選択**ダイアログ ボックスは、インストールした署名証明書を選択し、すべてのダイアログ ボックスを閉じます。  
  
## <a name="next-steps"></a>次の手順  
 署名付きメッセージを受信するためのパイプラインを作成する[署名付きメッセージの受信、BizTalk Server を構成する方法](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md)です。  
  
 署名付きメッセージを送信するためのパイプラインを作成する[署名付きメッセージを送信する、BizTalk Server を構成する方法](../core/how-to-configure-biztalk-server-for-sending-signed-messages.md)です。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server が署名されたメッセージで使用する証明書](../core/certificates-that-biztalk-server-uses-for-signed-messages.md)   
 [署名付きメッセージを送受信します。](../core/sending-and-receiving-signed-messages.md)