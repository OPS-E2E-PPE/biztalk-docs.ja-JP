---
title: CertWizard ユーティリティを使用して証明書のインポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2545da0d4ac9e62e500a24a49c8b3a10dd37adac
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283585"
---
# <a name="importing-certificates-using-the-certwizard-utility"></a>CertWizard ユーティリティを使用して証明書のインポート
このトピックでは、CertWizard ユーティリティでは、Microsoft で使用できるステップ バイ ステップ コマンド ライン ユーティリティを使用して、証明書をインポートする方法を説明します。 [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK。 このトピックでは、private、public、またはルート キーのインポートについて説明します。 これには、証明書を構成するために使用するスイッチについて説明します。  
  
 CertWizard ユーティリティは、Microsoft 管理コンソール (MMC) を使用して手動で行うことになる手順の多くを自動化します。 CertWizard ユーティリティは、実行、 **runas**ホスト サービス アカウントとして MMC を開くコマンド。 追加しない場合、 **Useridentity**スイッチを検出し、パスワードの入力を求める、ホスト サービス アカウントを使用します。 格納し、証明書を構成します。  
  
 同時に複数の証明書をインポートするには、複数の CertWizard ユーティリティ コマンドでバッチ ファイルを作成します。  
  
### <a name="to-import-a-private-key"></a>秘密キーをインポートするには  
  
1. をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。  
  
2. コマンド プロンプトに移動、 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] MS-DOS を使用して、SDK フォルダー **CD**コマンドでは、たとえば、「 **cd C:\Program files \microsoft BizTalk\<バージョン\>のアクセラレータRosettanet \sdk**します。  
  
   > [!NOTE]
   >  CertWizard ユーティリティを使用してヘルプを表示するには、入力**CertWizard/でしょうか。** コマンド プロンプト。  
  
3. コマンド プロンプトで「 **CertWizard/Privatekey \<filename\>.pfx**ここで、 \< *filename*\>.pfx にはにプライベート証明書にはが含まれています。 ファイルのパスワードを指定する追加 **「/filepassword」 \<filepassword\>** コマンド。  
  
4. BizTalk ホストによって使用される特定のアカウントに証明書をインポートするために追加する場合 **「/useridentity」 \<useridentity\> /Password\<パスワード\>** コマンド。  
  
5. .Pfx ファイルには、1 つ以上の証明書が含まれている場合に、特定の拇印を指定する、追加する場合 **「/thumbprint」\<拇印\>** コマンド。  
  
6. 証明書の使用率を構成する場合は、追加 **/Usage**コマンドと入力し、次の値のいずれかを追加します。  
  
   -   追加**サインオン**BizTalk グループの署名証明書として証明書の拇印を追加します。 BizTalk 管理コンソールで Microsoft BizTalk server (ローカル) ダイアログ ボックスで設定されました。  
  
   -   追加**復号化**プロパティ ページの [証明書] タブで、BizTalk 管理コンソール内の各ホストのセットとして、BizTalk ホストの暗号化解除証明書として証明書の拇印を追加します。  
  
   -   追加**両方**証明書の追加の両方の BizTalk グループ用の拇印署名証明書と、BizTalk ホストの暗号化解除証明書。  
  
   -   追加**none** BizTalk グループまたは BizTalk ホストの構成を設定しないとします。  
  
7. 証明書をエクスポート可能として構成する場合は、追加 **/exportable true**します。 証明書をエクスポート不可能として設定するには、追加 **/exportable false**既定の動作です。  
  
8. **Enter**キーを押します。  
  
9. コマンドに必要なパスワードのいずれかを入力して場合、ツールはそのプロンプトします。 パスワードを入力し、キーを押します**Enter**します。  
  
10. ファイルには、複数の証明書が含まれています。 コマンド内の拇印を入力しない場合は、ツールが利用可能な拇印を表示し、いずれかを選択するように求められます。 キーを押します拇印の番号を入力**Enter**します。  
  
     このツールで指定されたユーザーに対して、\Personal\Certificates ストアに証明書がインポート、 **「/useridentity」** スイッチ。 ユーザーを指定しない場合、既定のユーザーは、BizTalkServerApplication と BizTalkServerIsolatedHost ホストのユーザー id です。  
  
### <a name="to-import-a-public-key"></a>公開キーをインポートするには  
  
1. をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。  
  
2. コマンド プロンプトに移動、 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] MS-DOS を使用して、SDK フォルダー **CD**コマンドでは、たとえば、「 **cd C:\Program files \microsoft BizTalk\<バージョン\>Accelerator forRosettanet \sdk**します。  
  
3. コマンド プロンプトで「 **CertWizard/Publickey \<filename\>.cer**ここで、 \< *filename*\>.cer には公開証明書が含まれています。  
  
4. .Cer または .der ファイル内の証明書拇印を指定する場合は、追加 **「/thumbprint」\<拇印\>** コマンド。  
  
    ツールは、証明書 (ローカル コンピューター) \Other People\Certificates ストアに証明書をインポートし、その構成を設定します。  
  
### <a name="to-import-a-root-key"></a>ルート キーをインポートするには  
  
1. をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。  
  
2. コマンド プロンプトに移動、 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] MS-DOS を使用して、SDK フォルダー **CD**コマンドでは、たとえば、「 **cd C:\Program files \microsoft BizTalk\<バージョン\>Accelerator forRosettanet \sdk**します。  
  
3. コマンド プロンプトで「 **CertWizard/Rootkey \<filename\>.cer**ここで、 \< *filename*\>.cer にはルート証明書が含まれています。  
  
4. .Cer または .der ファイル内の証明書拇印を指定する場合は、追加 **「/thumbprint」\<拇印\>** コマンド。  
  
    ツールは、証明書 (ローカル コンピューター) \Trusted Root Certification Authority\Certificates ストアに証明書をインポートし、その構成を設定します。  
  
## <a name="see-also"></a>参照  
 [CertWizard](../../adapters-and-accelerators/accelerator-rosettanet/certwizard.md)   
 [証明書の管理](../../adapters-and-accelerators/accelerator-rosettanet/managing-certificates1.md)