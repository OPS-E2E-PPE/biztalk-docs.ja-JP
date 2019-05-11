---
title: MMC を使用して証明書のインポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates, public keys
- certificates, private keys
- importing certificates
- public keys
- private keys
- certificates, importing
ms.assetid: 58fb1711-e295-4aa6-902e-e28e4a2cd921
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d813adad739f7843308bcd3c53aa242ff97520c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283602"
---
# <a name="importing-certificates-using-mmc"></a>MMC を使用して証明書のインポート
このトピックでは、マイクロソフトのデジタル証明書をインポートする方法を説明します[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]を使用して取引先パートナーを認証、受信メッセージの暗号化を解除または暗号化または送信メッセージに署名します。  
  
 この手順では、Microsoft 管理コンソール (MMC) の証明書スナップインで使用します。 この手動プロセスは、証明書の使用を個別に構成することを必要とする証明書ストアに証明書をインポートします。 証明書の使用を自動的に構成する CertWizard ユーティリティを使用して、証明書をインポートすることもできます。  
  
 プライベート証明書をインポートするには、BizTalk ホストを実行するユーザー アカウントを使用する必要があります。  
  
### <a name="to-import-a-public-key-certificate"></a>公開キー証明書をインポートするには  
  
1. 公開キー (.cer) 証明書が証明書のコピー先サーバーのハード ディスク上の場所にファイルをコピーします。  
  
2. をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]、順にクリックします[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理コンソール**.  
  
3. [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)]管理コンソールで、展開**証明書 (ローカル コンピューター)** します。 ログイン ユーザー、コンピューター管理者のアクセス許可が必要です。  
  
4. 右クリック**その他のユーザー**、 をポイント**すべてのタスク**、 をクリックし、**インポート**します。  
  
5. **証明書のインポート ウィザードへようこそ**] ページで [**次**します。  
  
6. **インポートするファイル**] ページで [**参照**証明書ファイルを含むフォルダーを検索します。 クリックして、証明書をインポートするファイルを選択して**オープン**します。  
  
7. **証明書ストア**いずれかを選択 ページで、**証明書の種類に基づく証明書を自動的に選択**または**次のストアに証明書をすべてを配置**. 選択した場合**次のストアに証明書をすべてを配置**、 をクリックして**参照**、証明書ストアを選択**OK**、順にクリックします**次へ**.  
  
8. **[完了]** をクリックします。  
  
### <a name="to-import-a-private-key-certificate"></a>秘密キー証明書をインポートするには  
  
1. 証明書のコピー先サーバーのハード ディスク上の場所にファイルの秘密キー (.pfx) 証明書のコピー。  
  
2. をクリックして**開始**、 をクリックして**実行**、型 **/user として実行:\<サービスをホスト\>mmc**、順にクリックします**OK**します。  
  
   > [!NOTE]
   >  \<*サービスをホスト*\>、インストールしたときに、ホスト サービスに対して自動的に選択されたサービスの名前を入力[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]します。  
  
3. パスワードを入力します\<*サービスをホスト*\>、し、キーを押します**Enter**します。  
  
4. Microsoft 管理コンソールでの**ファイル** メニューのをクリックして**スナップインの追加と削除**します。  
  
5. [スナップインの追加と削除] ダイアログ ボックスで、**追加**します。  
  
6. スタンドアロン スナップインの追加 ダイアログ ボックスで、**証明書**、 をクリックして**追加**、 をクリックして**閉じる**、順にクリックします**OK**します。  
  
7. Microsoft 管理コンソールで **証明書 - 現在のユーザー**を右クリックして**個人**、 をポイント**すべてのタスク**、 をクリックし、**インポート**.  
  
8. **証明書のインポート ウィザードへようこそ**] ページで [**次**します。  
  
9. **インポートするファイル**] ページで [**参照**をインポートする証明書を含む .pfx 証明書ファイルを含むフォルダーを検索します。 適切なファイルを選択し、クリックして**オープン**します。  
  
10. **パスワード**ページで、**パスワード**ボックスに、秘密キー ファイルのパスワードを入力します。  
  
11. 選択**強力な秘密キーの保護を有効にする**または**キーをエクスポート可能としてマーク**、順にクリックします**次**します。  
  
12. **証明書ストア**いずれかを選択 ページで、**証明書の種類に基づく証明書を自動的に選択**または**次のストアに証明書をすべてを配置**. 選択した場合**次のストアに証明書をすべてを配置**、 をクリックして**参照**、ストアの選択**OK**、順にクリックします**次へ**。  
  
13. **証明書のインポート ウィザードの完了**] ページで [**完了**します。  
  
## <a name="see-also"></a>参照  
 [MMC を使用してインポートされた証明書を構成します。](../../adapters-and-accelerators/accelerator-rosettanet/configuring-certificates-imported-using-mmc.md)   
 [CertWizard](../../adapters-and-accelerators/accelerator-rosettanet/certwizard.md)