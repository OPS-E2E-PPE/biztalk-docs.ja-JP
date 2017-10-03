---
title: "手順 3: パブリックおよびプライベート証明書のインポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- public certificates
- importing certificates
- private certificates
- double action tutorial, importing certificates
- certificates, importing
ms.assetid: 955bdd69-9fbc-4100-ab8a-8f5dd4a17cbb
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c910a72f3e5ef39bb2e07e410f484e8c5cbececa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-importing-public-and-private-certificates"></a>手順 3: パブリックおよびプライベート証明書のインポート
この手順で作成した証明書をインポートする[手順 2: を作成するパブリックおよびプライベート証明書 &#91;RN3 &#93;](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-public-and-private-certificates.md) Contoso と Fabrikam のコンピューターにします。 各コンピュータは独自のプライベート証明書と他の組織のパブリック証明書をインポートします。  
  
> [!NOTE]
>  Fabrikam のプライベート証明書と Contoso のパブリック証明書を Fabrikam のコンピューターに転送して、インポートする必要があります。 ここでは、Fabrikam のコンピューターの C:\Certs フォルダーにこれらの証明書をコピーします。  
  
### <a name="to-import-the-contoso-private-certificates-on-the-contoso-computer"></a>Contoso のコンピューターで Contoso のプライベート証明書をインポートするには  
  
1.  Contoso のコンピューターでをクリックして**開始**、 をクリックして**実行**、型**cmd**、クリックして**ok**です。  
  
2.  コマンド プロンプトでに移動 **\<** *ドライブ***>: \Program Files\Microsoft BizTalk\<バージョン > Accelerator for rosettanet \sdk**キーを押します**Enter**です。  
  
3.  コマンド プロンプトで次のように入力します**CertWizard/Privatekey"\<***ドライブ***>: \Certs\Contoso Private Encryption.pfx"**、キーを押します**。入力**です。  
  
4.  **証明書ファイルのパスワードを入力してください**プロンプトで「 **mysecret**、キーを押します**Enter**です。  
  
5.  **Identity < contoso_machine > \HostSvc のパスワードの入力**プロンプトで HostSvc アカウント パスワードを入力して、、キーを押します**Enter**です。  
  
    > [!NOTE]
    >  BizTalkServerApplication を HostSvc 以外のアカウント名で実行している場合は、プロンプトが異なります。  
  
6.  **このホーム証明書が使用する**プロンプトで「 **D**、キーを押します**Enter**です。  
  
     CertWizard は、BizTalkServerApplication ホストと BizTalkServerIsolatedHost ホストの実行に使用しているユーザー アカウントの \Personal\Certificates ストアに、証明書をインポートします。  
  
7.  手順 3 ~ 6」と入力して、署名証明書であることを指定する Contoso Private Signature.pfx 証明書を**S**で、**このホーム証明書が使用する**手順 6 で書き留めたプロンプトです。  
  
### <a name="to-import-the-fabrikam-public-certificates-on-the-contoso-computer"></a>Contoso のコンピュータで Fabrikam のパブリック証明書をインポートするには  
  
1.  Contoso のコンピューターでをクリックして**開始**、 をクリックして**実行、**型**cmd**、順にクリック**ok**です。  
  
2.  コマンド プロンプトでに移動*\<ドライブ >***: \Program Files\Microsoft BizTalk\<バージョン > Accelerator for rosettanet \sdk**キーを押します**を入力してください**.  
  
3.  コマンド プロンプトで次のように入力します**CertWizard/Publickey"***\<ドライブ >***: \Certs\Fabrikam Public Encryption.cer"**、キーを押します**。入力**です。  
  
4.  Fabrikam Public Signature.cer 証明書について、手順 3. を繰り返します。  
  
### <a name="to-import-the-fabrikam-private-certificates-on-the-fabrikam-computer"></a>Fabrikam のコンピューターで Fabrikam のプライベート証明書をインポートするには  
  
1.  Contoso のコンピューターから次のファイルをコピー、\<ドライブ >: \Certs フォルダーに、Fabrikam のコンピューター: Contoso Public Encryption.cer、Contoso Public Signature.cer、Fabrikam Private Encryption.pfx、Fabrikam Private Signature.pfx とします。  
  
2.  Fabrikum コンピューターで、をクリックして**開始**、 をクリックして**実行**、型**cmd**、クリックして**ok**です。  
  
3.  コマンド プロンプトでに移動*\<ドライブ >***: \Program Files\Microsoft BizTalk\<バージョン > Accelerator for rosettanet \sdk**キーを押します**を入力してください**.  
  
4.  コマンド プロンプトで次のように入力します**CertWizard/Privatekey"***\<ドライブ >***: \Certs\Fabrikam Private Encryption.pfx"**、キーを押します**。入力**です。  
  
5.  **証明書ファイルのパスワードを入力してください**プロンプトで「 **mysecret**、キーを押します**Enter**です。  
  
6.  **Identity < fabrikam_machine > \HostSvc のパスワードの入力**プロンプトで HostSvc アカウント パスワードを入力して、、キーを押します**Enter**です。  
  
    > [!NOTE]
    >  BizTalkServerApplication を HostSvc 以外のアカウント名で実行している場合は、プロンプトが異なります。  
  
7.  **このホーム証明書が使用する**プロンプトで「 **D**、キーを押します**Enter**です。  
  
     CertWizard は、BizTalkServerApplication ホストと BizTalkServerIsolatedHost ホストの実行に使用しているユーザー アカウントの \Personal\Certificates ストアに、証明書をインポートします。  
  
8.  手順 4 ~ 7」と入力して、署名証明書であることを指定する Fabrikam Private Signature.pfx 証明書を**S**で、**このホーム証明書が使用する**手順 6. でダイアログを表示します。  
  
### <a name="to-import-the-contoso-public-certificates-on-the-fabrikam-computer"></a>Fabrikam のコンピューターで Contoso のパブリック証明書をインポートするには  
  
1.  Fabrikum コンピューターで、をクリックして**開始**、 をクリックして**実行**、型**cmd**、クリックして**ok**です。  
  
2.  コマンド プロンプトでに移動*\<ドライブ >***: \Program Files\Microsoft BizTalk\<バージョン > Accelerator for rosettanet \sdk**キーを押します**を入力してください**.  
  
3.  コマンド プロンプトで次のように入力します**CertWizard/Publickey"***\<ドライブ >***: \Certs\Contoso Public Encryption.cer"**、キーを押します**。入力**です。  
  
4.  Contoso Public Signature.cer 証明書について、手順 3. を繰り返します。  
  
## <a name="see-also"></a>参照  
 [手順 4: IIS でレイヤーをソケット セキュリティで保護を有効にします。](../../adapters-and-accelerators/accelerator-rosettanet/step-4-enabling-secure-sockets-layer-in-iis.md)