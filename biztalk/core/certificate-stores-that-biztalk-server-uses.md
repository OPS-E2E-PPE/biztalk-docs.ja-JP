---
title: BizTalk Server で使用される証明書ストア |Microsoft ドキュメント
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
ms.openlocfilehash: b142ff5b9c9007a86b09acd25f53f8c88796988c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233802"
---
# <a name="certificate-stores-that-biztalk-server-uses"></a>BizTalk Server で使用される証明書ストア
BizTalk Server では、2 種類の証明書ストアが使用されます。公開キーには "ほかの人" 証明書ストアが使用され、秘密キーには各ホスト インスタンス サービス アカウント用の個人証明書ストアが使用されます。  
  
 **その他のユーザーの証明書ストア。** : 公開キー証明書は、その名前が意味するとおり、公開された証明書であり、証明書が保存されているコンピューターへのアクセスが許可されているユーザーであればだれでもアクセスできます。 BizTalk Server では、公開キー証明書を使用して特定のパーティへのメッセージを暗号化したり、特定のパーティからの受信メッセージのデジタル署名を確認します。 "ほかの人" 証明書ストアは Windows で提供され、ストアにはコンピュータで使用される公開キー証明書が保存されます。 このストアにある証明書はすべてのユーザーが読み取りおよび使用できます。このストアを管理する権限は Windows 管理者が持っています。  
  
> [!NOTE]
>  公開キー証明書は、BizTalk ホスト インスタンスが置かれているローカル コンピュータの Local Machine\Other People 証明書ストアに保存する必要があります。ホスト インスタンスは、署名の確認やリモートのパートナーに送信するメッセージの暗号化に使用されます。  
  
 次の図に、BizTalk Server で公開キー証明書に対して使用される "ほかの人" 証明書ストアを示します。  
  
 ![その他のユーザーの証明書ストア](../core/media/bpi-sp-msgsec-otherpeoplecertstore.gif "BPI_SP_MSGSEC_OTHERPEOPLECERTSTORE")  
  
 **個人証明書ストア。** BizTalk Server では、秘密キー証明書を使用して、受信メッセージの解読や送信メッセージの署名を行います。 コンピューターに対話形式でログオンできるすべての Windows アカウントには、オペレーティング システムによって個人証明書ストアが作成されます。証明書ストアには、そのアカウントのみがアクセスできます。 BizTalk Server では、ホスト インスタンス サービス アカウントごとの個人証明書ストアを使用して、各サービス アカウントがアクセスできる秘密キー証明書にアクセスします。 個人証明書ストアにアクセスし、管理できるのはその証明書ストアの所有者のみです。 つまり、ホスト サービス アカウントごとに S/MIME デコード パイプラインをホストする各コンピュータにログオンし、証明書スナップインを使用して解読証明書を個人証明書ストアにインポートする必要があります。  
  
 次の図に、BizTalk Server で秘密キー証明書に対して使用される個人証明書ストアを示します。  
  
 ![現在のユーザーの証明書ストア](../core/media/bpi-sp-msgsec-mystore.gif "BPI_SP_MSGSEC_MYSTORE")  
  
> [!IMPORTANT]
>  秘密キー証明書は、各コンピュータでホスト インスタンス サービス アカウントごとに設定されている Current User\Personal 証明書ストアに保存する必要があります。BizTalk ホスト インスタンスでは解読や送信メッセージの署名の実行にこの証明書が必要です。  
  
> [!NOTE]
>  送信メッセージへの署名に使う秘密キー証明書をサービス アカウントの個人証明書ストアに追加した後は、BizTalk 管理コンソールでこの署名証明書を指定する必要もあります。 詳細については、次を参照してください。[署名付きメッセージを送信する、BizTalk Server を構成する方法](../core/how-to-configure-biztalk-server-for-sending-signed-messages.md)です。  
  
> [!NOTE]
>  個人証明書ストアは、証明書のインポートやエクスポートをスクリプト記述するなどのプログラム操作に使用する場合、MY 証明書ストアとも呼ばれます。  
  
 次の表で、各 Windows 証明書ストアにインストールする必要がある証明書を説明します。  
  
### <a name="table-1-certificates-for-each-windows-certificate-store"></a>表 1 Windows 証明書ストアごとの証明書  
  
|**証明書の目的**|**証明書の種類**|**証明書ストア**|  
|-----------------------------|--------------------------|---------------------------|  
|署名|固有の秘密キー|MIME/SMIME エンコーダー パイプライン コンポーネントはメッセージに署名するように構成、送信パイプラインをあるホスト インスタンスの場合は、各サービス アカウントの個人用ストア (**署名証明書をメッセージの追加**プロパティに設定`True`)。 詳細については、次を参照してください[署名付きメッセージを送信する、BizTalk Server を構成する方法。](../core/how-to-configure-biztalk-server-for-sending-signed-messages.md)|  
|署名の検証|パートナーの公開キー|ホスト インスタンスが置かれている各コンピュータの "ほかの人" ストア。ホスト インスタンスの受信パイプラインには、MIME/SMIME デコーダ パイプライン コンポーネントが含まれます。 詳細については、次を参照してください。[署名付きメッセージの受信、BizTalk Server を構成する方法](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md)です。|  
|解読|固有の秘密キー|ホスト インスタンス サービス アカウントごとの個人用ストア。ホスト インスタンスの受信パイプラインには、MIME/SMIME デコーダ パイプライン コンポーネントが含まれます。 詳細については、次を参照してください。[暗号化されたメッセージの受信、BizTalk Server を構成する方法](../core/how-to-configure-biztalk-server-for-receiving-encrypted-messages.md)です。|  
|暗号化|パートナーの公開キー|ホスト インスタンスを送信パイプラインを持つ MIME/SMIME エンコーダー パイプライン コンポーネントはメッセージを暗号化するように構成されている各コンピューター上の他の"人"ストア (**暗号化を有効にする**プロパティに設定`True)`です。 詳細については、次を参照してください。[暗号化されたメッセージの送信の BizTalk Server を構成する方法](../core/how-to-configure-biztalk-server-for-sending-encrypted-messages.md)です。|  
|パーティの解決|パートナーの公開キー|パーティの解決を構成する管理コンピュータの "ほかの人" ストア。 詳細については、次を参照してください。[パーティの解決用の証明書を使用して](../core/using-certificates-for-party-resolution.md)です。|  
  
 次の図に、メッセージの受信専用の BizTalk Server に設定された各証明書ストアに必要な証明書を示します。  
  
 ![セキュリティで保護されたメッセージの受信に必要な証明書](../core/media/bpi-sp-msgsec-certmgmt-certstores-receive.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Receive")  
  
 次の図に、メッセージの送信専用の BizTalk Server に設定された各証明書ストアに必要な証明書を示します。  
  
 ![セキュリティで保護されたメッセージの送信に必要な証明書](../core/media/bpi-sp-msgsec-certmgmt-certstores-send.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Send")  
  
 証明書ストアと Microsoft 管理コンソール (MMC) の証明書スナップインの詳細については、Windows ヘルプで "証明書コンソール" を検索してください。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server が署名されたメッセージで使用する証明書](../core/certificates-that-biztalk-server-uses-for-signed-messages.md)   
 [BizTalk Server は暗号化されたメッセージを使用する証明書](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md)   
 [暗号化と証明書の署名](../core/encryption-and-signing-certificates.md)   
 [メッセージ セキュリティを実装します。](../core/implementing-message-security.md)