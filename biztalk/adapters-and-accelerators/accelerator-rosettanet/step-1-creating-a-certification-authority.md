---
title: 手順 1:証明機関の作成 |Microsoft Docs
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
ms.openlocfilehash: adbcc42cc358b6aa370f1c7ba0ba62d4caee2d9f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281561"
---
# <a name="step-1-creating-a-certification-authority"></a>手順 1:証明機関の作成
このトピックでは、証明書サービスをインストール[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]コンポーネント。 Contoso と Fabrikam 組織間でセキュリティで保護された通信を昇格するのに必要のある証明書の生成に使用します。 各取引先パートナーは、通信用秘密暗号化証明書と秘密署名証明書を識別するためにがあります。 さらに、パートナーは、3 a 2 PIP Partner Interface Process () を実装するときに、セキュリティで保護された通信を実現する相互の公開キー証明書を共有します。  
  
### <a name="to-install-the-certificate-server"></a>証明書サーバーをインストールするには  
  
1.  をクリックして**開始**、] をポイント**設定**、順にクリックします**コントロール パネルの [** します。 ダブルクリック**を追加または削除プログラム**します。  
  
2.  **プログラム追加と削除**ダイアログ ボックスで、をクリックして**Windows コンポーネントの追加/削除**します。  
  
3.  **Windows コンポーネント ウィザード**ページで、**コンポーネント**セクションで、**証明書サービス**、 をクリックして**はい**、順にクリックします**次**コンポーネントの構成ウィザードを起動します。  
  
    > [!NOTE]
    >  場合、**証明書サービス Windows**コンポーネントが既に選択されている、この手順の残りの部分をスキップします。  
  
4.  **CA の種類の**ことを確認します ページで、**スタンドアロン ルート CA**が選択されているし、をクリックし、 **次へ**します。  
  
5.  **CA 識別情報**] ページの [、**この CA の共通名**ボックスに「 **Contoso-fabrikamca**、順にクリックします**次**します。  
  
6.  **証明書データベースの設定** ページで、既定値のままにしてをクリックし、**次**します。  
  
7.  クリックして**はい**ときに、ウィザードで入力すると、インターネット インフォメーション サービス (IIS) を停止します。  
  
8.  クリックして**はい**場合、**コンポーネントの構成ウィザード**Active Server Pages を有効にするように求められます。  
  
9. クリックして**完了**を閉じる、 **Windows コンポーネント ウィザード**します。  
  
    > [!NOTE]
    >  のみ、証明機関として 1 台のコンピューターを使用する必要があるとします。 2 番目のコンピューターでこの手順を繰り返す必要はありません。 このチュートリアルでは、証明機関として Contoso のコンピューターを使用します。  
  
### <a name="to-install-a-root-certification-authority-ca-for-windows-server-2008"></a>Windows Server 2008 のルート証明機関 (CA) をインストールするには  
  
1.  サーバー マネージャーを開き、**役割の追加**をクリックし、**次**、 をクリック**Active Directory 証明書**サービス チェック ボックス。 クリックして**次**2 回クリックします。  
  
2.  役割サービスの選択 ページで、次のようにクリックします。**証明機関と証明機関 Web 登録**します。 **[次へ]** をクリックします。  
  
3.  セットアップの種類の指定 ページで、次のようにクリックします。**スタンドアロン**します。 **[次へ]** をクリックします。  
  
4.  CA の種類の指定 ページで、ルート CA をクリックします。 **[次へ]** をクリックします。  
  
5.  秘密キーの設定 ページで、新しい秘密キーを作成する をクリックします。 **[次へ]** をクリックします。  
  
6.  CA のページの暗号化を構成します。 **[次へ]** をクリックします。  
  
7.  CA 名の構成 この CA の共通名 Contoso-fabrikamca と入力します。 クリックして**次**します。  
  
8.  有効期間の設定 ページで、次のようにクリックします。**次**します。  
  
9. 証明書データベースの構成 ページで、次のようにクリックします。**次**します。  
  
10. インストール オプションの確認 ページで、次のようにクリックします。**インストール**します。  
  
### <a name="configuring-the-web-site-for-the-ca-to-use-https-authentication"></a>HTTPS 認証を使用する CA の Web サイトを構成します。  
  
1.  証明機関として使用するコンピューターで、[開始] をクリックして、すべてのプログラム]、[管理ツール] をポイントし、し、[インターネット インフォメーション サービス (IIS) マネージャー。  
  
2.  インターネット インフォメーション サービス (IIS) マネージャー] ダイアログ ボックスで、右クリックして**既定の Web サイトと [バインドの編集.** ポップアップ メニュー。  
  
3.  [サイト バインド] ダイアログ ボックス**追加**します。  
  
4.  サイト バインドの追加 ダイアログ ボックスで選択**https** 種類 から証明書を選択します。 **SSL 証明書**ドロップダウンをクリックします**OK**。  
  
5.  クリックして**閉じます**サイト バインドを閉じる. ダイアログ ボックス。  
  
### <a name="to-download-the-ca-certificate"></a>CA 証明書をダウンロードするには  
  
1.  Internet Explorer を http://<contoso_computername>/certsrv/Default.asp を開きます。  
  
2.  Default.asp ページで、次のようにクリックします。 **CA 証明書、証明書チェーン、または CRL のダウンロード**します。  
  
3.  確認します**現在 [Contoso-fabrikamca]** でが選択されている、 **CA 証明書**ボックスの一覧をクリックして**CA 証明書のダウンロード**します。  
  
4.  Contoso と Fabrikam のコンピューターの両方で、証明書を C:\Certs\Contoso-FabrikamCA.cer に保存します。  
  
### <a name="to-import-the-ca-certificate-to-the-trusted-root-certification-authorities-store"></a>信頼されたルート証明機関ストアに CA 証明書をインポートするには  
  
1.  をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。  
  
2.  コマンド プロンプトに移動します**\<ドライブ\>: \Program Files\MicrosoftBizTalk\<バージョン\>Accelerator for rosettanet \sdk**、キーを押しますと **」と入力。**.  
  
3.  コマンド プロンプトで「 **CertWizard/Rootkey"\<ドライブ\>: \Certs\Contoso-FabrikamCA.cer"**、押します **」と入力**します。  
  
    > [!IMPORTANT]
    >  この手順は、Contoso と Fabrikam の両方のコンピューターで実行します。  
  
### <a name="to-enable-automatic-certificate-issuing"></a>証明書の自動発行を有効にするには  
  
1.  証明機関として使用するコンピューターで、次のようにクリックします**開始**、 をポイント**プログラム**、 をポイント**管理ツール**、 をクリックし、  **。証明機関**します。  
  
2.  証明機関 ダイアログ ボックスで右クリックして**Contoso-fabrikamca**、 をクリックし、**プロパティ**します。  
  
3.  Contoso-fabrikamca のプロパティ ダイアログ ボックスで、上、**ポリシー モジュール** タブで **プロパティ**します。  
  
4.  プロパティ ダイアログ ボックスで、次のように選択します。**証明書テンプレートの設定に従う**、順にクリックします**OK**します。  
  
5.  クリックして**OK** Contoso-fabrikamca ダイアログ ボックスを閉じます。  
  
6.  証明機関 ダイアログ ボックスを閉じます。  
  
    > [!NOTE]
    >  自動証明書の発行を有効にすると、証明書サービスには、証明書発行手続きが自動化されます。 この変更を適用する証明書サービスを再起動する必要があります。  
    >   
    >  現在のユーザー \ 信頼されたルート証明機関のルート証明書 Contoso-fabrikamca.cer をインストールする必要があります。  
  
## <a name="see-also"></a>参照  
 [手順 2:パブリックおよびプライベート証明書の作成](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-public-and-private-certificates.md)