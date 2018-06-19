---
title: MMC を使用してインポートされた証明書の構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- decryption certificates
- certificates, decryption certificates
- certificates, signing certificates
- importing certificates
- signing certificates
- certificates, importing
ms.assetid: 64dbfbcf-6026-4c68-a93a-f483ec52deac
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d8896691557f48a8e85e67e09e35d20e1d606d0
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25961672"
---
# <a name="configuring-certificates-imported-using-mmc"></a>MMC を使用してインポートされた証明書を構成します。
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] 管理コンソール (MMC) の証明書スナップインを使用して証明書をインポートしたら、それらの使用法を構成する必要があります。 そのためには、BizTalk グループ、BizTalk ホストと分離ホスト サービス アカウント、PIP (Partner Interface Processes)、取引先アグリーメント、およびパートナーを構成します。 次の手順を実行する必要があります。  
  
> [!NOTE]
>  CertWizard ユーティリティを使用して証明書をインポートおよび構成する場合は、これらの手動の手順を実行する必要はありません。  
  
-   ホーム組織について署名証明書の使用法を構成します。 つまり、秘密キーを使用して、送信メッセージのホーム組織を識別します。 これを行うには、BizTalk グループに対して署名証明書を構成します。  
  
-   ホーム組織について暗号化解除証明書の使用法を構成します。 つまり、パートナーの公開キーに対応する秘密キーを使用して、着信メッセージの暗号化を解除します。 これを行うには、BizTalk ホストと BizTalk 分離ホストのサービス アカウントごとに暗号化解除証明書を構成します。 ホストと分離ホストの両方のサービス アカウントに、同じ暗号化解除証明書を入力してください。[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] では、これらに同じアカウントを設定する必要があります。  
  
    > [!NOTE]
    >  BizTalk ホストと BizTalk 分離ホストは、暗号化された同じ着信メッセージの暗号化を解除できるように、同じ暗号化解除証明書を持つ必要があります。 HTTP アダプターを実行する BizTalk 分離ホストは、ホスト証明書にアクセスできないため、メッセージを受信する証明書を持つ必要があります。 BizTalk ホストも、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] がメッセージを受信した後でそのメッセージを処理する証明書を持つ必要があります。  
  
-   各パートナーに対して暗号化証明書および署名証明書を構成します。 これを行うには、証明書を入力する、**全般**のタブ、**パートナー**プロパティ ページで、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] ([!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]) 管理コンソールです。 証明書には、パートナーへの送信メッセージを暗号化する公開キー暗号化証明書、および着信メッセージに記されたパートナーの ID を確認する公開キー署名証明書があります。 詳細については、次を参照してください。[を作成または編集パートナー](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-partner.md)です。  
  
-   ホーム組織と取引先の間における暗号化ポリシーを構成します。 これを行うでの取引先アグリーメントを構成する、**プロトコル**のタブ、**アグリーメントのプロパティ** ページで、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]管理コンソールです。 詳細については、次を参照してください。[を作成するか、契約の編集](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)です。  
  
### <a name="to-configure-the-signing-certificate-for-a-biztalk-group-or-the-decryption-certificate-for-a-biztalk-host"></a>BizTalk グループの署名証明書または BizTalk ホストの暗号化解除証明書を構成するには  
  
1.  をクリックして**開始**、 をクリックして**実行**、型**runas/user:\<サービスをホスト\>mmc**、順にクリック**ok**です。  
  
    > [!NOTE]
    >  \<*サービスをホスト*\>、インストールしたときに、ホスト サービスに関連付けられたサービスの名前を入力[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]です。  
  
2.  パスワードを入力\<*サービスをホスト*\>、ENTER キーを押します。  
  
3.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]、順にクリック[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理コンソール**です。  
  
4.  展開**証明書 - 現在のユーザー**、展開**個人**、クリックして**証明書**です。  
  
5.  右側のペインで、プライベート証明書をダブルクリックします。  
  
6.  証明書 ウィンドウで、**詳細** タブで、をクリックして**拇印**、表示ウィンドウで、16 進数の識別番号を選択します。 Ctrl + C キーを押してコピーします。  
  
7.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
8.  BizTalk グループに対して署名証明書を構成するには、右**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **(ローカル)**、順にクリック**プロパティ**です。 右側にテキスト ボックス内をクリックして**拇印**をクリックして、テキスト ボックスに拇印番号を貼り付けるには、CTRL + V キーを押します**OK**です。  
  
9. BizTalk ホストの暗号化解除証明書を構成するには展開**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **(ローカル)**、展開**ホスト**、するホストを右クリックして構成、およびクリックして**プロパティ**です。  
  
10. **証明書** タブの右側にテキスト ボックス内をクリックして**拇印**をクリックして、テキスト ボックスに拇印番号を貼り付けるには、CTRL + V キーを押します**OK**です。  
  
    > [!NOTE]
    >  暗号化解除証明書は、BizTalk ホスト (BizTalkServerApplication) と BizTalk 分離ホスト (BizTalkServerIsolatedHost) の両方に対して構成する必要があります。  
  
## <a name="see-also"></a>参照  
 [証明書の管理](../../adapters-and-accelerators/accelerator-rosettanet/managing-certificates1.md)