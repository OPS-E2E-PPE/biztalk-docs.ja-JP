---
title: BizTalk Server で使用される証明書ストア |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- public key certificates
- certificate stores, warnings
- private key certificates
- certificates, private key
- Other People stores [certificates]
- certificate stores, Personal store
- Personal store [certificates]
- certificate stores, Windows stores
- certificates, public key
- certificates, certificate stores
- certificate stores
ms.assetid: 29b65913-be3b-45d9-9865-02e52e4370f4
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 55164b3c96bf0cc5ee5c9eac7d0d70a04b2a9d5e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358019"
---
# <a name="certificate-stores-that-biztalk-server-uses"></a>BizTalk Server で使用される証明書ストア
BizTalk Server では、秘密キーの各ホスト インスタンス サービス アカウントの 2 種類の証明書ストア、公開キーには、その他のユーザー証明書ストアと、個人証明書ストアを使用します。  
  
 **その他のユーザーの証明書ストア。** 公開キー証明書の名前が示すようはパブリックと格納されているコンピューターにアクセス権を持つすべてのユーザーがアクセスできます。 BizTalk Server は、特定のパーティにメッセージを暗号化して、特定のパーティから受信したメッセージのデジタル署名を検証する公開キー証明書を使用します。 Windows では、コンピューター上で使用する公開キー証明書にストアをその他のユーザーの証明書に提供します。 すべてのユーザーが読み取るし、このストアに証明書を使用し、Windows 管理者がこのストアを管理する権限を持っています。  
  
> [!NOTE]
>  ローカル コンピューターの Local machine \other People 証明書ストアに公開キー証明書を保存する必要があります、署名の検証またはリモートのパートナーに送信されるメッセージの暗号化に使用する BizTalk ホスト インスタンスが存在します。  
  
 次の図は、BizTalk Server は公開キー証明書を使用するその他のユーザー証明書ストアを示しています。  
  
 ![他のユーザーの証明書ストア](../core/media/bpi-sp-msgsec-otherpeoplecertstore.gif "BPI_SP_MSGSEC_OTHERPEOPLECERTSTORE")  
  
 **個人証明書ストア。** BizTalk Server では、受信メッセージの解読し、送信メッセージの署名に秘密キー証明書を使用します。 コンピューターで対話型ログオンに有効になっているすべての Windows アカウントが、そのアカウントのみがアクセスできるオペレーティング システムによって格納個人証明書。 BizTalk Server では、各ホスト インスタンス サービス アカウントの個人証明書ストアを使用して、各サービス アカウントにアクセス権の秘密キー証明書にアクセスします。 証明書ストアの所有者のみがアクセスし、個人証明書ストアを管理できます。 つまり、する必要がありますログインする各コンピューターにことはホスト S/MIME デコード パイプラインとして各のホストのサービス アカウント、および証明書スナップインを使用してストアを復号化証明書を個人証明書をインポートします。  
  
 次の図は、秘密キー証明書に BizTalk Server を使用する個人用証明書ストアを示しています。  
  
 ![現在のユーザーの証明書ストア](../core/media/bpi-sp-msgsec-mystore.gif "BPI_SP_MSGSEC_MYSTORE")  
  
> [!IMPORTANT]
>  BizTalk に解読や送信署名証明書を必要とする実行中のホスト インスタンスをされている各コンピューターでは各ホスト インスタンス サービス アカウントの Current user \personal 証明書ストアには、秘密キー証明書を保存する必要があります。メッセージ。  
  
> [!NOTE]
>  秘密キーを使用して送信メッセージに署名するためのサービス アカウントの個人証明書ストアに証明書を追加した後は、BizTalk 管理コンソールでこの署名証明書を指定することも必要があります。 詳細については、次を参照してください。[署名付きメッセージの送信用の BizTalk Server を構成する方法](../core/how-to-configure-biztalk-server-for-sending-signed-messages.md)します。  
  
> [!NOTE]
>  スライドをインポートするスクリプトと証明書のエクスポートなどのプログラムによる操作の際、個人証明書ストアにも、MY 証明書ストアが呼び出されます。  
  
 次の表では、各 Windows 証明書ストアにインストールする必要がある証明書について説明します。  
  
### <a name="table-1-certificates-for-each-windows-certificate-store"></a>表 1 の証明書の各 Windows 証明書ストア  
  
|**証明書の目的**|**証明書の種類**|**証明書ストア**|  
|-----------------------------|--------------------------|---------------------------|  
|署名|独自の秘密キー|MIME/SMIME エンコーダー パイプライン コンポーネントはメッセージに署名するように構成、送信パイプラインに含まれるホスト インスタンスの場合は、各サービス アカウントの個人用ストア (**署名証明書をメッセージに追加**プロパティに設定`True`)。 詳細については、次を参照してください[署名付きメッセージの送信用の BizTalk Server を構成する方法。](../core/how-to-configure-biztalk-server-for-sending-signed-messages.md)|  
|署名の検証|パートナーの公開キー|他のユーザーは、MIME/SMIME デコーダー パイプライン コンポーネントの受信パイプラインに含まれるホスト インスタンスがある各コンピューターに格納します。 詳細については、次を参照してください。[署名付きメッセージの受信用の BizTalk Server を構成する方法](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md)します。|  
|復号化|独自の秘密キー|MIME/SMIME デコーダー パイプライン コンポーネントの受信パイプラインに含まれるホスト インスタンスの場合は、各サービス アカウントの個人用ストア。 詳細については、次を参照してください。[暗号化されたメッセージの受信用の BizTalk Server を構成する方法](../core/how-to-configure-biztalk-server-for-receiving-encrypted-messages.md)します。|  
|暗号化|パートナーの公開キー|その他の"人"ストア MIME/SMIME エンコーダー パイプライン コンポーネントはメッセージを暗号化するように構成、送信パイプラインに含まれるホスト インスタンスがある各コンピューター (**暗号化を有効にする**プロパティに設定`True)`します。 詳細については、次を参照してください。[暗号化されたメッセージの送信用 BizTalk Server を構成する方法](../core/how-to-configure-biztalk-server-for-sending-encrypted-messages.md)します。|  
|パーティの解決|パートナーの公開キー|他のユーザーは、パーティの解決を構成する管理コンピューターに保存します。 詳細については、次を参照してください。[パーティの解決用の証明書を使用して](../core/using-certificates-for-party-resolution.md)します。|  
  
 次の図は、メッセージの受信専用証明書が必要なすべての証明書に格納する BizTalk Server を示します。  
  
 ![セキュリティで保護されたメッセージを受信するために必要な証明書](../core/media/bpi-sp-msgsec-certmgmt-certstores-receive.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Receive")  
  
 次の図は、メッセージを送信する証明書が必要なすべての証明書に格納する BizTalk Server の専用を示します。  
  
 ![セキュリティで保護されたメッセージを送信するために必要な証明書](../core/media/bpi-sp-msgsec-certmgmt-certstores-send.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Send")  
  
 証明書ストアと Microsoft 管理コンソール (MMC) の証明書スナップインの詳細については、Windows のヘルプで「証明書コンソール」を検索します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server は、署名付きメッセージで使用する証明書](../core/certificates-that-biztalk-server-uses-for-signed-messages.md)   
 [BizTalk Server は、暗号化されたメッセージで使用する証明書](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md)   
 [暗号化および署名証明書](../core/encryption-and-signing-certificates.md)   
 [メッセージ セキュリティの実装](../core/implementing-message-security.md)