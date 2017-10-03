---
title: "CertWizard ユーティリティを使用して証明書のインポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- certificates, root keys
- certificates, public keys
- certificates, private keys
- importing certificates
- public keys
- private keys
- CertWizard utility
- certificates, importing
- root keys
ms.assetid: 0c54d7ab-69cf-4f4a-b976-6f740a41280b
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e887811b4aef771a33a1f4e4d8852d5815036a74
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="importing-certificates-using-the-certwizard-utility"></a>CertWizard ユーティリティを使用して証明書のインポート
このトピックで使用できる詳細な手順のコマンド ライン ユーティリティである CertWizard ユーティリティを使用して証明書をインポートする方法について説明、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK。 ここでは、秘密キー、公開キー、またはルート キーのインポートについて説明します。 証明書の構成に使用するスイッチについても説明します。  
  
 CertWizard ユーティリティを使用することにより、[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] 管理コンソール (MMC) を使用して手動で行う必要がある多くの手順を自動化できます。 CertWizard ユーティリティを実行、 **runas**ホスト サービス アカウントとして MMC を開くコマンド。 追加しない場合、 **Useridentity**スイッチが検出され、パスワードの入力を求める、ホスト サービス アカウントを使用します。 証明書が格納および構成されます。  
  
 複数の CertWizard ユーティリティ コマンドでバッチ ファイルを作成することにより、複数の証明書を同時にインポートできます。  
  
### <a name="to-import-a-private-key"></a>秘密キーをインポートするには  
  
1.  をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。  
  
2.  コマンド プロンプトでに移動、 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] MS-DOS を使用して SDK フォルダー **CD**コマンド、たとえば、入力**cd C:\Program files \microsoft BizTalk\<バージョン > Accelerator for rosettanet \sdk** .  
  
    > [!NOTE]
    >  CertWizard ユーティリティを使用してヘルプを参照するには、次のように入力します**CertWizard/しますか?。** コマンド プロンプトで。  
  
3.  コマンド プロンプトで次のように入力します。 **CertWizard/Privatekey\<ファイル名 > .pfx**ここで、 \< *filename*> .pfx プライベート証明書が含まれています。 ファイルのパスワードを指定するには追加**「/filepassword」 \<filepassword >**コマンド。  
  
4.  BizTalk ホストによって使用される特定のアカウントに、証明書をインポートする、追加したい場合**「/useridentity」 \<useridentity >/Password\<パスワード >**コマンド。  
  
5.  .Pfx ファイルには、複数の証明書が含まれている場合に、特定の拇印を指定する、追加したい場合**「/thumbprint」\<拇印 >**コマンド。  
  
6.  証明書の使用法を構成する場合は、追加**/Usage**コマンドと入力し、次の値のいずれかを追加します。  
  
    -   追加**記号**BizTalk グループの署名証明書として証明書の拇印を追加します。 Microsoft のダイアログ ボックスで設定に従って[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]BizTalk 管理コンソールでは (ローカル)。  
  
    -   追加**復号化**プロパティ ページの [証明書] タブで、BizTalk 管理コンソール内の各ホストのセットとして、BizTalk ホストの暗号化解除証明書として証明書の拇印を追加します。  
  
    -   追加**両方**証明書を追加の拇印を両方の BizTalk グループの署名証明書と、BizTalk ホストの暗号化解除証明書。  
  
    -   追加**なし**ときたくない、BizTalk グループまたは BizTalk ホストの構成を設定します。  
  
7.  証明書をエクスポート可能として構成する場合は、追加**/exportable true**です。 証明書をエクスポート不可能として設定する追加**/exportable false**既定の動作です。  
  
8.  **Enter**キーを押します。  
  
9. 必要なパスワードをいずれか 1 つコマンドに入力しないと、ツールが入力を求めます。 パスワードを入力し、キーを押します**Enter**です。  
  
10. ファイルに複数の証明書が含まれる場合は、コマンドに拇印を入力しないと、利用可能な拇印がツールに表示され、いずれか 1 つを選択するように求められます。 クリックし、キーを押しな拇印の番号を入力**Enter**です。  
  
     このツールで指定されたユーザーに対して、\Personal\Certificates ストアに証明書がインポート、 **「/useridentity」**スイッチ。 ユーザーを指定しない場合は、BizTalkServerApplication と BizTalkServerIsolatedHost ホストのユーザー ID が既定のユーザーになります。  
  
### <a name="to-import-a-public-key"></a>公開キーをインポートするには  
  
1.  をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。  
  
2.  コマンド プロンプトでに移動、 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] MS-DOS を使用して、SDK フォルダー **CD**コマンド、たとえば、入力**cd C:\Program files \microsoft BizTalk\<バージョン > Accelerator for rosettanet \sdk**.  
  
3.  コマンド プロンプトで次のように入力します。 **CertWizard/Publickey\<ファイル名 > .cer**ここで、 \< *filename*> .cer に公開証明書が含まれています。  
  
4.  .Cer または .der ファイル内の証明書の拇印を指定する場合は、追加**「/thumbprint」\<拇印 >**コマンド。  
  
     [証明書 (ローカル コンピューター)] \Other People\Certificates ストアに証明書がインポートされ、構成が設定されます。  
  
### <a name="to-import-a-root-key"></a>ルート キーをインポートするには  
  
1.  をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。  
  
2.  コマンド プロンプトでに移動、 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] MS-DOS を使用して、SDK フォルダー **CD**コマンド、たとえば、入力**cd C:\Program files \microsoft BizTalk\<バージョン > Accelerator for rosettanet \sdk**.  
  
3.  コマンド プロンプトで次のように入力します。 **CertWizard/Rootkey\<ファイル名 > .cer**ここで、 \< *filename*> .cer にルート証明書が含まれています。  
  
4.  .Cer または .der ファイル内の証明書の拇印を指定する場合は、追加**「/thumbprint」\<拇印 >**コマンド。  
  
     [証明書 (ローカル コンピューター)] \Trusted Root Certification Authority\Certificates ストアに証明書がインポートされ、構成が設定されます。  
  
## <a name="see-also"></a>参照  
 [CertWizard](../../adapters-and-accelerators/accelerator-rosettanet/certwizard.md)   
 [証明書の管理](../../adapters-and-accelerators/accelerator-rosettanet/managing-certificates1.md)