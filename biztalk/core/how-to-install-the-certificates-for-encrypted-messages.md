---
title: 暗号化されたメッセージの証明書をインストールする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e11fdb81-041c-4ba6-849d-d511ead0e8be
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c24cd9c34fef3c7d984874cc72da13030b167d0f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994099"
---
# <a name="how-to-install-the-certificates-for-encrypted-messages"></a>暗号化されたメッセージ用の証明書をインストールする方法
暗号化されたメッセージを送受信するための証明書をインストールする手順の概要を次に示します。  
  
-   解読に使用する証明書を証明書ストアにインストールするには  
  
-   暗号化に使用する証明書を証明書ストアにインストールするには  
  
-   暗号化されたメッセージを受信するために BizTalk ホストを構成するには  
  
> [!NOTE]
>  署名および解読操作の両方に 1 つの証明書を使用することも、機能ごとに 1 つの証明書を使用することもできます。  
  
### <a name="to-install-the-decryption-certificates-in-the-certificates-store"></a>解読証明書を証明書ストアにインストールするには  
  
1. 組織の管理者が、使用する [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の証明機関 (CA) に対して、暗号化用の公開キーと秘密キーのペアを要求します。  
  
2. 管理者が、パートナー A に暗号化用の公開キーを送信します。  
  
3. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、ハンドラーを実行するホスト インスタンスのサービス アカウントは A. をインストール パートナーからメッセージを受け取ると、ログオン、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]サービス アカウントの個人用ストア内のメッセージを解読するための秘密キー証明書。 次の図に、証明書をインストールする証明書ストアを示します。  
  
    ![セキュリティで保護されたメッセージを受信するために必要な証明書](../core/media/bpi-sp-msgsec-certmgmt-certstores-receive.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Receive")  
  
4. パートナー A で、パートナー A に送信したメッセージを暗号化できるように、適切なストアに [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の公開キー証明書をインストールします  (パートナー A が使用されている場合[!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)]、 [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]、 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]、その他のユーザー ストアに公開キーをインストールします)。  
  
### <a name="to-install-the-encryption-certificates-in-the-certificates-store"></a>暗号化証明書を証明書ストアにインストールするには  
  
1. パートナー A が、CA に対して暗号化のための公開キーと秘密キーのペアを要求します。  
  
2. パートナー A が、メッセージを解読するための秘密キー証明書を適切なストアにインストールします  (パートナー A が [!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)]、[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]、または [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] を使用している場合は、"個人用証明書" ストアに秘密キーをインストールします)。  
  
3. パートナー A に送信したメッセージの暗号化のための公開キーが、パートナー A から送信されます。  
  
4. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で、パートナー A にメッセージを送信するハンドラーを実行中のホスト インスタンスがあるサーバーにログオンします。パートナー A に送信したメッセージの暗号化に使用する、パートナー A の公開キー証明書を "その他のユーザー" ストアにインストールします。 次の図に、証明書をインストールする証明書ストアを示します。  
  
    ![セキュリティで保護されたメッセージを送信するために必要な証明書](../core/media/bpi-sp-msgsec-certmgmt-certstores-send.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Send")  
  
### <a name="to-configure-biztalk-hosts-for-receiving-encrypted-messages"></a>暗号化されたメッセージを受信するために BizTalk ホストを構成するには  
  
1. をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、**プラットフォームの設定**、展開**ホスト**します。  
  
   1.  右側のウィンドウで、暗号化されたメッセージの受信ハンドラーである BizTalk ホストを右クリックし、**プロパティ**します。  
  
   2.  **ホストのプロパティ**ダイアログ ボックスで、をクリックして**証明書**、 をクリックして**参照**します。  
  
   3.  **証明書の選択**ダイアログ ボックスがインストールした解読証明書を選択し、すべてのダイアログ ボックスを閉じます。  
  
       > [!NOTE]
       >  詳細については、[ホスト プロパティを変更する方法](../core/how-to-modify-host-properties.md)を参照してください。  
  
## <a name="next-steps"></a>次の手順  
 暗号化されたメッセージを受信するためのパイプラインを作成する[暗号化されたメッセージの受信用の BizTalk Server を構成する方法](../core/how-to-configure-biztalk-server-for-receiving-encrypted-messages.md)  
  
 暗号化されたメッセージを送信するためのパイプラインを作成する[暗号化されたメッセージの送信用 BizTalk Server を構成する方法](../core/how-to-configure-biztalk-server-for-sending-encrypted-messages.md)  
  
## <a name="see-also"></a>参照  
 [BizTalk Server は、暗号化されたメッセージで使用する証明書](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md)   
 [暗号化されたメッセージの送受信](../core/sending-and-receiving-encrypted-messages.md)