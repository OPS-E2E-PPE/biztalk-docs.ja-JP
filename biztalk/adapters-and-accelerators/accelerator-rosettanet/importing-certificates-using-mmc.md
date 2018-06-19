---
title: MMC を使用して証明書のインポート |Microsoft ドキュメント
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
ms.openlocfilehash: 466917e0656dfa39467a00dfa91285b3cb7cf1a1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25961624"
---
# <a name="importing-certificates-using-mmc"></a>MMC を使用して証明書のインポート
デジタルをインポートする方法を説明する証明書[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]を使用して、取引先の認証、受信メッセージの暗号化を解除または暗号化または送信メッセージに署名します。  
  
 この手順では、[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] 管理コンソール (MMC) の証明書スナップインを使用します。 この手動プロセスでは、証明書ストアに証明書をインポートしますが、証明書の使用法は個別に構成する必要があります。 証明書は CertWizard ユーティリティを使用してインポートすることもできます。この場合、証明書の使用法は自動的に構成されます。  
  
 プライベート証明書をインポートするには、BizTalk ホストを実行するユーザー アカウントを使用する必要があります。  
  
### <a name="to-import-a-public-key-certificate"></a>公開キー証明書をインポートするには  
  
1.  公開キー (.cer) 証明書ファイルを、サーバーのハードディスク上にある証明書のコピー先にコピーします。  
  
2.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]、順にクリック[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理コンソール**.  
  
3.  [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)]管理コンソールで、展開**証明書 (ローカル コンピューター)** です。 ログインするユーザーは、そのコンピューターの管理権限を持っていなければなりません。  
  
4.  右クリック**ほかの人**、 をポイント**すべてのタスク**、クリックして**インポート**です。  
  
5.  **証明書のインポート ウィザードへようこそ**] ページで [**次**です。  
  
6.  **インポートするファイル** ページで、をクリックして**参照**証明書ファイルを含むフォルダーに移動します。 クリックして、証明書をインポートするファイルを選択して**開く**です。  
  
7.  **証明書ストア** ページで、いずれかを選択**証明書の種類に基づいて証明書を自動的に選択**または**次のストアに証明書をすべてを配置**. 選択した場合**次のストアに証明書をすべてを配置**、] をクリックして**参照**証明書ストアを選択してをクリックし、 **[ok]**、順にクリック **[次へ**.  
  
8.  **[完了]** をクリックします。  
  
### <a name="to-import-a-private-key-certificate"></a>秘密キー証明書をインポートするには  
  
1.  秘密キー (.pfx) 証明書ファイルを、サーバーのハードディスク上にある証明書のコピー先にコピーします。  
  
2.  をクリックして**開始**、 をクリックして**実行**、型 **/user として実行:\<サービスをホスト\>mmc**、順にクリック**ok**です。  
  
    > [!NOTE]
    >  \<*サービスをホスト*\>、インストールしたときに、ホスト サービスに対して自動的に選択されたサービスの名前を入力[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]です。  
  
3.  パスワードを入力\<*サービスをホスト*\>、キーを押します**Enter**です。  
  
4.  [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]管理コンソールで、**ファイル** メニューのをクリックして**スナップインの追加と削除**です。  
  
5.  [スナップインの追加と削除] ダイアログ ボックスで、**追加**です。  
  
6.  スタンドアロン スナップインの追加 ダイアログ ボックスで、次のように選択します。**証明書**、 をクリック**追加**、 をクリック**閉じる**、順にクリック**OK**です。  
  
7.  [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]管理コンソールで、展開**証明書 - 現在のユーザー**を右クリックして**個人**、 をポイント**すべてのタスク**、クリックして**インポート**です。  
  
8.  **証明書のインポート ウィザードへようこそ**] ページで [**次**です。  
  
9. **インポートするファイル** ページで、をクリックして**参照**をインポートする証明書を含む .pfx 証明書ファイルを含むフォルダーに移動します。 適切なファイルを選択し、クリックして**開く**です。  
  
10. **パスワード**] ページの [、**パスワード**ボックスに、秘密キー ファイルのパスワードを入力します。  
  
11. 選択**強力な秘密キーの保護を有効にする**または**キーをエクスポート可能としてマーク**、クリックして **[次へ]** です。  
  
12. **証明書ストア** ページで、いずれかを選択**証明書の種類に基づいて証明書を自動的に選択**または**次のストアに証明書をすべてを配置**. 選択した場合**次のストアに証明書をすべてを配置**、 をクリックして**参照**ストアを選択してをクリックし、 **ok**、順にクリック**次へ**です。  
  
13. **証明書のインポート ウィザードの完了**] ページで [**完了**です。  
  
## <a name="see-also"></a>参照  
 [MMC を使用してインポートされた証明書を構成します。](../../adapters-and-accelerators/accelerator-rosettanet/configuring-certificates-imported-using-mmc.md)   
 [CertWizard](../../adapters-and-accelerators/accelerator-rosettanet/certwizard.md)