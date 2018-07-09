---
title: '手順 3: パブリックおよびプライベート証明書のインポート |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- public certificates
- importing certificates
- private certificates
- double action tutorial, importing certificates
- certificates, importing
ms.assetid: 955bdd69-9fbc-4100-ab8a-8f5dd4a17cbb
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18074fd3b72322d79e10895214352837ccf907bd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002347"
---
# <a name="step-3-importing-public-and-private-certificates"></a>手順 3: パブリックおよびプライベート証明書のインポート
作成した証明書をインポートするこの手順で[手順 2: を作成するパブリックおよびプライベート証明書&#91;RN3&#93; ](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-public-and-private-certificates.md) Contoso と Fabrikam のコンピューターにします。 各コンピュータは独自のプライベート証明書と他の組織のパブリック証明書をインポートします。  
  
> [!NOTE]
>  Fabrikam のプライベート証明書と Contoso のパブリック証明書を Fabrikam のコンピューターに転送して、インポートする必要があります。 ここでは、Fabrikam のコンピューターの C:\Certs フォルダーにこれらの証明書をコピーします。  
  
### <a name="to-import-the-contoso-private-certificates-on-the-contoso-computer"></a>Contoso のコンピューターで Contoso のプライベート証明書をインポートするには  
  
1. Contoso コンピューターでは、次のようにクリックします。**開始**、 をクリック**実行**、型**cmd**、順にクリックします**OK**。  
  
2. コマンド プロンプトに移動します**\<**<em>ドライブ</em>**\>: \Program Files\Microsoft BizTalk\<バージョン\>のアクセラレータ。Rosettanet \sdk**押します**Enter**します。  
  
3. コマンド プロンプトで「 **CertWizard/Privatekey"\<**<em>ドライブ</em>**\>: \Certs\Contoso Private Encryption.pfx"**、し、キーを押します。**入力**します。  
  
4. **証明書ファイルのパスワードを入力してください**プロンプトで「 **mysecret**、キーを押しますと **」と入力**します。  
  
5. **Identity < contoso_machine > \HostSvc のパスワードの入力**と表示されたら、HostSvc アカウント パスワードを入力し、キーを押して**Enter**します。  
  
   > [!NOTE]
   >  BizTalkServerApplication を HostSvc 以外のアカウント名で実行している場合は、プロンプトが異なります。  
  
6. **このホーム証明書が使用される**プロンプトで「 **D**、キーを押しますと **」と入力**します。  
  
    CertWizard は、BizTalkServerApplication ホストと BizTalkServerIsolatedHost ホストの実行に使用しているユーザー アカウントの \Personal\Certificates ストアに、証明書をインポートします。  
  
7. 手順 3 ~ 6」と入力して、署名証明書である Contoso Private Signature.pfx 証明書の指定の**S**で、**このホーム証明書が使用される**手順 6 で書き留めたプロンプト。  
  
### <a name="to-import-the-fabrikam-public-certificates-on-the-contoso-computer"></a>Contoso のコンピュータで Fabrikam のパブリック証明書をインポートするには  
  
1.  Contoso コンピューターでは、次のようにクリックします。**開始**、 をクリック**実行、** 型**cmd**、順にクリックします**ok**します。  
  
2.  コマンド プロンプトに移動します*\<ドライブ\>* * *:\Program files \microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk** と押します **」と入力。**.  
  
3.  コマンド プロンプトで「 **CertWizard/Publickey"***\<ドライブ\>***: \Certs\Fabrikam Public Encryption.cer"**、し、キーを押します**Enter**.  
  
4.  Fabrikam Public Signature.cer 証明書について、手順 3. を繰り返します。  
  
### <a name="to-import-the-fabrikam-private-certificates-on-the-fabrikam-computer"></a>Fabrikam のコンピューターで Fabrikam のプライベート証明書をインポートするには  
  
1.  Contoso のコンピューターから次のファイルをコピー、\<ドライブ\>: \Certs フォルダーに、Fabrikam のコンピューター: Contoso Public Encryption.cer、Contoso Public Signature.cer、Fabrikam Private Encryption.pfx、Fabrikam PrivateSignature.pfx します。  
  
2.  Fabrikum コンピューターでは、次のようにクリックします。**開始**、 をクリック**実行**、型**cmd**、順にクリックします**OK**します。  
  
3.  コマンド プロンプトに移動します*\<ドライブ\>* * *:\Program files \microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk** と押します **」と入力。**.  
  
4.  コマンド プロンプトで「 **CertWizard/Privatekey"***\<ドライブ\>***: \Certs\Fabrikam Private Encryption.pfx"**、およびキーを押します**Enter**.  
  
5.  **証明書ファイルのパスワードを入力してください**プロンプトで「 **mysecret**、キーを押しますと **」と入力**します。  
  
6.  **Identity < fabrikam_machine > \HostSvc のパスワードの入力**と表示されたら、HostSvc アカウント パスワードを入力し、キーを押して**Enter**します。  
  
    > [!NOTE]
    >  BizTalkServerApplication を HostSvc 以外のアカウント名で実行している場合は、プロンプトが異なります。  
  
7.  **このホーム証明書が使用される**プロンプトで「 **D**、キーを押しますと **」と入力**します。  
  
     CertWizard は、BizTalkServerApplication ホストと BizTalkServerIsolatedHost ホストの実行に使用しているユーザー アカウントの \Personal\Certificates ストアに、証明書をインポートします。  
  
8.  手順 4 ~ 7」と入力して、署名証明書である Fabrikam Private Signature.pfx 証明書の指定を**S**で、**このホーム証明書が使用される**手順 6 でダイアログを表示します。  
  
### <a name="to-import-the-contoso-public-certificates-on-the-fabrikam-computer"></a>Fabrikam のコンピューターで Contoso のパブリック証明書をインポートするには  
  
1.  Fabrikum コンピューターでは、次のようにクリックします。**開始**、 をクリック**実行**、型**cmd**、順にクリックします**OK**します。  
  
2.  コマンド プロンプトに移動します*\<ドライブ\>* * *:\Program files \microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk** と押します **」と入力。**.  
  
3.  コマンド プロンプトで「 **CertWizard/Publickey"***\<ドライブ\>***: \Certs\Contoso Public Encryption.cer"**、押します **」と入力**します。  
  
4.  Contoso Public Signature.cer 証明書について、手順 3. を繰り返します。  
  
## <a name="see-also"></a>参照  
 [手順 4: IIS で Secure Sockets Layer の有効化](../../adapters-and-accelerators/accelerator-rosettanet/step-4-enabling-secure-sockets-layer-in-iis.md)