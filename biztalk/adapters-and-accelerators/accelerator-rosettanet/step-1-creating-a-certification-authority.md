---
title: '手順 1: 証明機関の作成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates, creating
- double action tutorial, creating certificates
- creating, certificates
ms.assetid: b6ecd534-6b03-4336-8337-33ec18a0802a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3d796608a4cc323ccf5e1a8bdee7420c5bab259
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25966232"
---
# <a name="step-1-creating-a-certification-authority"></a>手順 1: 証明機関の作成
ここでは、証明書サービス [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] コンポーネントをインストールします。 このコンポーネントを使用して、セキュリティで保護された通信を Contoso 組織と Fabrikam 組織の間で確立するために必要な証明書を生成します。 各取引先は、通信のための秘密暗号化証明書と、識別のための秘密署名証明書を所有します。 さらに、パートナーは 3A2 PIP (Partner Interface Process) の実装時に、セキュリティで保護された通信を確立するために公開キー証明書をお互いに共有します。  
  
### <a name="to-install-the-certificate-server"></a>証明書サーバーをインストールするには  
  
1.  をクリックして**開始**、] をポイント**設定**、順にクリック**コントロール パネルの [** です。 ダブルクリックして**追加または削除するプログラム**です。  
  
2.  **プログラム追加と削除**ダイアログ ボックスで、をクリックして**Windows コンポーネントの追加/削除**です。  
  
3.  **Windows コンポーネント ウィザード** ページの 、**コンポーネント**セクションで、**証明書サービス**、 をクリックして**はい**、 をクリックし、**次**コンポーネントの構成ウィザードを開始します。  
  
    > [!NOTE]
    >  場合、**証明書 ServicesWindows**コンポーネントが既に選択されている、この手順の残りの部分をスキップします。  
  
4.  **CA の種類** ページで、ことを確認して**スタンドアロン ルート CA**を選択して、をクリックして**次**です。  
  
5.  **CA 識別情報**] ページの [、**この CA の共通名**ボックスに、入力**Contoso-fabrikamca**、順にクリック**次**です。  
  
6.  **証明書のデータベース設定** ページで、既定値のままにしてをクリックして**次**です。  
  
7.  をクリックして**はい**されたら、インターネット インフォメーション サービス (IIS) を停止します。  
  
8.  をクリックして**はい**場合、**コンポーネントの構成ウィザード**Active Server Pages を有効にするように求められます。  
  
9. をクリックして**完了**を閉じる、 **Windows コンポーネント ウィザード**です。  
  
    > [!NOTE]
    >  証明機関として使用するコンピューターは 1 台のみです。 2 台目のコンピューターでこの手順を繰り返す必要はありません。 このチュートリアルでは、証明機関として Contoso のコンピューターを使用しています。  
  
### <a name="to-install-a-root-certification-authority-ca-for-windows-server-2008"></a>Windows Server 2008 向けのルート証明機関 (CA) をインストールするには  
  
1.  サーバー マネージャーを開き、**役割の追加**の役割で、をクリックして**次**、 をクリック**Active Directory 証明書**サービス チェック ボックスです。 をクリックして**次**2 回クリックします。  
  
2.  役割サービスの選択 ページで、**証明機関および証明機関 Web 登録**です。 **[次へ]** をクリックします。  
  
3.  セットアップの種類の指定 ページで、をクリックして**スタンドアロン**です。 **[次へ]** をクリックします。  
  
4.  [CA の種類の指定] ページで、[ルート CA] をクリックします。 **[次へ]** をクリックします。  
  
5.  [秘密キーの設定] ページで、[新しい秘密キーを作成する] をクリックします。 **[次へ]** をクリックします。  
  
6.  [CA の暗号化を構成] ページで、 **[次へ]** をクリックします。  
  
7.  CA 名の構成でこの CA の共通名 Contoso-fabrikamca」と入力します。 クリックして**次**です。  
  
8.  有効期間の設定 ページで、をクリックして**次**です。  
  
9. 証明書データベースの構成 ページで、**次**です。  
  
10. インストール オプションの確認 ページで、**インストール**です。  
  
### <a name="configuring-the-web-site-for-the-ca-to-use-https-authentication"></a>CA 用の Web サイトで HTTPS 認証を使用するための構成  
  
1.  証明機関として使用したコンピューターで、[スタート] ボタンをクリックし、[すべてのプログラム] をポイントします。次に、[管理ツール] をポイントし、[インターネット インフォメーション サービス (IIS) マネージャー] をクリックします。  
  
2.  インターネット インフォメーション サービス (IIS) マネージャー] ダイアログ ボックスで、右クリックして**既定の Web サイトと [バインドの編集.** ポップアップ メニュー。  
  
3.  [サイト バインド] ダイアログ ボックス**追加**です。  
  
4.  サイト バインドの追加 ダイアログ ボックスで選択**https** 種類 から証明書を選択**SSL 証明書**ドロップダウンをクリックして**OK**です。  
  
5.  をクリックして**閉じる**サイト バインドを閉じます. ダイアログ ボックス。  
  
### <a name="to-download-the-ca-certificate"></a>CA 証明書をダウンロードするには  
  
1.  Internet Explorer で、http://<Contoso のコンピュータ名>/certsrv/Default.asp を開きます。  
  
2.  Default.asp ページで、をクリックして**CA 証明書、証明書チェーン、または CRL のダウンロード**です。  
  
3.  確認して**現在 [Contoso-fabrikamca]** でが選択されている、 **CA 証明書**一覧をクリックして**CA 証明書のダウンロード**です。  
  
4.  証明書を Contoso および Fabrikam の両方のコンピューターの C:\Certs\Contoso-FabrikamCA.cer に保存します。  
  
### <a name="to-import-the-ca-certificate-to-the-trusted-root-certification-authorities-store"></a>信頼されたルート証明機関ストアに CA 証明書をインポートするには  
  
1.  をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。  
  
2.  コマンド プロンプトでに移動**\<ドライブ\>: \Program Files\MicrosoftBizTalk\<バージョン\>Accelerator for rosettanet \sdk**、キーを押します**を入力してください**.  
  
3.  コマンド プロンプトで次のように入力します。 **CertWizard/Rootkey"\<ドライブ\>: \Certs\Contoso-FabrikamCA.cer"**、キーを押します**Enter**です。  
  
    > [!IMPORTANT]
    >  Contoso のコンピューターと Fabrikam のコンピューターの両方で、この手順を実行します。  
  
### <a name="to-enable-automatic-certificate-issuing"></a>証明書の自動発行を有効にするには  
  
1.  コンピューターで証明機関として使用して、をクリックして**開始**、 をポイント**プログラム**、 をポイント**管理ツール**、クリックして**証明機関**です。  
  
2.  証明機関 ダイアログ ボックスで右クリック**Contoso-fabrikamca**、クリックして**プロパティ**です。  
  
3.  Contoso-fabrikamca のプロパティ ダイアログ ボックスで、**ポリシー モジュール** タブで、をクリックして**プロパティ**です。  
  
4.  プロパティ ダイアログ ボックスで選択**証明書テンプレートの設定に従う**、順にクリック**OK**です。  
  
5.  をクリックして**OK** Contoso-fabrikamca ダイアログ ボックスを閉じます。  
  
6.  [証明機関] ダイアログ ボックスを閉じます。  
  
    > [!NOTE]
    >  証明書の自動発行を有効にすると、証明書サービスにより証明書発行手続きが自動化されます。 この変更を適用するには、証明書サービスを再開する必要があります。  
    >   
    >  必要に応じて、Root Certificate Contoso-FabrikamCA.cer を "現在のユーザー\信頼されたルート証明機関" にインストールしてください。  
  
## <a name="see-also"></a>参照  
 [手順 2: パブリック証明書とプライベート証明書の作成](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-public-and-private-certificates.md)