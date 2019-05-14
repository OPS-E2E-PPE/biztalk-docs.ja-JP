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
# <a name="step-1-creating-a-certification-authority"></a><span data-ttu-id="59f24-102">手順 1:証明機関の作成</span><span class="sxs-lookup"><span data-stu-id="59f24-102">Step 1: Creating a Certification Authority</span></span>
<span data-ttu-id="59f24-103">このトピックでは、証明書サービスをインストール[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="59f24-103">In this topic, you install the Certificate Services [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] component.</span></span> <span data-ttu-id="59f24-104">Contoso と Fabrikam 組織間でセキュリティで保護された通信を昇格するのに必要のある証明書の生成に使用します。</span><span class="sxs-lookup"><span data-stu-id="59f24-104">You use it to generate the certificates that you need to promote secure communication between the Contoso and Fabrikam organizations.</span></span> <span data-ttu-id="59f24-105">各取引先パートナーは、通信用秘密暗号化証明書と秘密署名証明書を識別するためにがあります。</span><span class="sxs-lookup"><span data-stu-id="59f24-105">Each trading partner will have a private encryption certificate for communication and a private signature certificate for identification purposes.</span></span> <span data-ttu-id="59f24-106">さらに、パートナーは、3 a 2 PIP Partner Interface Process () を実装するときに、セキュリティで保護された通信を実現する相互の公開キー証明書を共有します。</span><span class="sxs-lookup"><span data-stu-id="59f24-106">Additionally, the partners will share their public key certificates with each other to promote secure communication when implementing the 3A2 Partner Interface Process (PIP).</span></span>  
  
### <a name="to-install-the-certificate-server"></a><span data-ttu-id="59f24-107">証明書サーバーをインストールするには</span><span class="sxs-lookup"><span data-stu-id="59f24-107">To install the certificate server</span></span>  
  
1.  <span data-ttu-id="59f24-108">をクリックして**開始**、] をポイント**設定**、順にクリックします**コントロール パネルの [** します。</span><span class="sxs-lookup"><span data-stu-id="59f24-108">Click **Start**, point to **Settings**, and then click **Control Panel**.</span></span> <span data-ttu-id="59f24-109">ダブルクリック**を追加または削除プログラム**します。</span><span class="sxs-lookup"><span data-stu-id="59f24-109">Double-click **Add or Remove Programs**.</span></span>  
  
2.  <span data-ttu-id="59f24-110">**プログラム追加と削除**ダイアログ ボックスで、をクリックして**Windows コンポーネントの追加/削除**します。</span><span class="sxs-lookup"><span data-stu-id="59f24-110">In the **Add or Remove Programs** dialog box, click **Add/Remove Windows Components**.</span></span>  
  
3.  <span data-ttu-id="59f24-111">**Windows コンポーネント ウィザード**ページで、**コンポーネント**セクションで、**証明書サービス**、 をクリックして**はい**、順にクリックします**次**コンポーネントの構成ウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="59f24-111">On the **Windows Components Wizard** page, in the **Components** section, select **Certificate Services**, click **Yes**, and then click **Next** to start the Configuring Components Wizard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="59f24-112">場合、**証明書サービス Windows**コンポーネントが既に選択されている、この手順の残りの部分をスキップします。</span><span class="sxs-lookup"><span data-stu-id="59f24-112">If the **Certificates ServicesWindows** component is already selected, skip the rest of this procedure.</span></span>  
  
4.  <span data-ttu-id="59f24-113">**CA の種類の**ことを確認します ページで、**スタンドアロン ルート CA**が選択されているし、をクリックし、 **次へ**します。</span><span class="sxs-lookup"><span data-stu-id="59f24-113">On the **CA Type** page, make sure that **Stand-alone root CA** is selected, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="59f24-114">**CA 識別情報**] ページの [、**この CA の共通名**ボックスに「 **Contoso-fabrikamca**、順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="59f24-114">On the **CA Identifying Information** page, in the **Common name for this CA** box, type **Contoso-FabrikamCA**, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="59f24-115">**証明書データベースの設定** ページで、既定値のままにしてをクリックし、**次**します。</span><span class="sxs-lookup"><span data-stu-id="59f24-115">On the **Certificate Database Settings** page, leave the defaults, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="59f24-116">クリックして**はい**ときに、ウィザードで入力すると、インターネット インフォメーション サービス (IIS) を停止します。</span><span class="sxs-lookup"><span data-stu-id="59f24-116">Click **Yes** when the wizard prompts you to stop Internet Information Services (IIS).</span></span>  
  
8.  <span data-ttu-id="59f24-117">クリックして**はい**場合、**コンポーネントの構成ウィザード**Active Server Pages を有効にするように求められます。</span><span class="sxs-lookup"><span data-stu-id="59f24-117">Click **Yes** if the **Configuring Components Wizard** prompts you to enable Active Server Pages.</span></span>  
  
9. <span data-ttu-id="59f24-118">クリックして**完了**を閉じる、 **Windows コンポーネント ウィザード**します。</span><span class="sxs-lookup"><span data-stu-id="59f24-118">Click **Finish** to close the **Windows Components Wizard**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="59f24-119">のみ、証明機関として 1 台のコンピューターを使用する必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="59f24-119">You only have to use one computer as the Certification Authority.</span></span> <span data-ttu-id="59f24-120">2 番目のコンピューターでこの手順を繰り返す必要はありません。</span><span class="sxs-lookup"><span data-stu-id="59f24-120">You do not have to repeat this step on the second computer.</span></span> <span data-ttu-id="59f24-121">このチュートリアルでは、証明機関として Contoso のコンピューターを使用します。</span><span class="sxs-lookup"><span data-stu-id="59f24-121">This tutorial uses the Contoso computer as the Certification Authority.</span></span>  
  
### <a name="to-install-a-root-certification-authority-ca-for-windows-server-2008"></a><span data-ttu-id="59f24-122">Windows Server 2008 のルート証明機関 (CA) をインストールするには</span><span class="sxs-lookup"><span data-stu-id="59f24-122">To install a root Certification Authority (CA) for Windows Server 2008</span></span>  
  
1.  <span data-ttu-id="59f24-123">サーバー マネージャーを開き、**役割の追加**をクリックし、**次**、 をクリック**Active Directory 証明書**サービス チェック ボックス。</span><span class="sxs-lookup"><span data-stu-id="59f24-123">Open Server Manager, click **Add Roles** in Roles, click **Next**, and click **Active Directory Certificate** Services check box.</span></span> <span data-ttu-id="59f24-124">クリックして**次**2 回クリックします。</span><span class="sxs-lookup"><span data-stu-id="59f24-124">Click **Next** twice.</span></span>  
  
2.  <span data-ttu-id="59f24-125">役割サービスの選択 ページで、次のようにクリックします。**証明機関と証明機関 Web 登録**します。</span><span class="sxs-lookup"><span data-stu-id="59f24-125">On the Select Role Services page, click **Certification Authority and Certification Authority Web Enrollment**.</span></span> <span data-ttu-id="59f24-126">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="59f24-126">Click **Next**.</span></span>  
  
3.  <span data-ttu-id="59f24-127">セットアップの種類の指定 ページで、次のようにクリックします。**スタンドアロン**します。</span><span class="sxs-lookup"><span data-stu-id="59f24-127">On the Specify Setup Type page, click **Standalone**.</span></span> <span data-ttu-id="59f24-128">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="59f24-128">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="59f24-129">CA の種類の指定 ページで、ルート CA をクリックします。</span><span class="sxs-lookup"><span data-stu-id="59f24-129">On the Specify CA Type page, click Root CA.</span></span> <span data-ttu-id="59f24-130">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="59f24-130">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="59f24-131">秘密キーの設定 ページで、新しい秘密キーを作成する をクリックします。</span><span class="sxs-lookup"><span data-stu-id="59f24-131">On the Set Up Private Key page, click Create a new private key.</span></span> <span data-ttu-id="59f24-132">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="59f24-132">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="59f24-133">CA のページの暗号化を構成します。</span><span class="sxs-lookup"><span data-stu-id="59f24-133">On the Configure Cryptography for CA page.</span></span> <span data-ttu-id="59f24-134">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="59f24-134">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="59f24-135">CA 名の構成 この CA の共通名 Contoso-fabrikamca と入力します。 クリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="59f24-135">On Configure CA Name, in the Common name for this CA box, type Contoso-FabrikamCA, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="59f24-136">有効期間の設定 ページで、次のようにクリックします。**次**します。</span><span class="sxs-lookup"><span data-stu-id="59f24-136">On the Set Validity Period page, click **Next**.</span></span>  
  
9. <span data-ttu-id="59f24-137">証明書データベースの構成 ページで、次のようにクリックします。**次**します。</span><span class="sxs-lookup"><span data-stu-id="59f24-137">On the Configure Certificate Database page, Click **Next**.</span></span>  
  
10. <span data-ttu-id="59f24-138">インストール オプションの確認 ページで、次のようにクリックします。**インストール**します。</span><span class="sxs-lookup"><span data-stu-id="59f24-138">On the Confirm Installation Options page, click **Install**.</span></span>  
  
### <a name="configuring-the-web-site-for-the-ca-to-use-https-authentication"></a><span data-ttu-id="59f24-139">HTTPS 認証を使用する CA の Web サイトを構成します。</span><span class="sxs-lookup"><span data-stu-id="59f24-139">Configuring the Web site for the CA to use HTTPS authentication</span></span>  
  
1.  <span data-ttu-id="59f24-140">証明機関として使用するコンピューターで、[開始] をクリックして、すべてのプログラム]、[管理ツール] をポイントし、し、[インターネット インフォメーション サービス (IIS) マネージャー。</span><span class="sxs-lookup"><span data-stu-id="59f24-140">On the computer you used as the Certification Authority, click Start, point to All Programs, point to Administrative Tools, and then click Internet Information Services (IIS) Manager.</span></span>  
  
2.  <span data-ttu-id="59f24-141">インターネット インフォメーション サービス (IIS) マネージャー] ダイアログ ボックスで、右クリックして**既定の Web サイトと [バインドの編集.**</span><span class="sxs-lookup"><span data-stu-id="59f24-141">In the Internet Information Services (IIS) Manager dialog box, right click **Default Web Site and select Edit Bindings…**</span></span> <span data-ttu-id="59f24-142">ポップアップ メニュー。</span><span class="sxs-lookup"><span data-stu-id="59f24-142">from the popup menu.</span></span>  
  
3.  <span data-ttu-id="59f24-143">[サイト バインド] ダイアログ ボックス**追加**します。</span><span class="sxs-lookup"><span data-stu-id="59f24-143">In Site Bindings dialog box click **Add**.</span></span>  
  
4.  <span data-ttu-id="59f24-144">サイト バインドの追加 ダイアログ ボックスで選択**https** 種類 から証明書を選択します。 **SSL 証明書**ドロップダウンをクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="59f24-144">In Add Site Binding dialog box select **https** in Type drop down, select the certificate from **SSL certificate** drop down and click **OK**.</span></span>  
  
5.  <span data-ttu-id="59f24-145">クリックして**閉じます**サイト バインドを閉じる.</span><span class="sxs-lookup"><span data-stu-id="59f24-145">Click **Close** to close the Site Bindings…</span></span> <span data-ttu-id="59f24-146">ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="59f24-146">dialog box.</span></span>  
  
### <a name="to-download-the-ca-certificate"></a><span data-ttu-id="59f24-147">CA 証明書をダウンロードするには</span><span class="sxs-lookup"><span data-stu-id="59f24-147">To download the CA certificate</span></span>  
  
1.  <span data-ttu-id="59f24-148">Internet Explorer を http://<contoso_computername>/certsrv/Default.asp を開きます。</span><span class="sxs-lookup"><span data-stu-id="59f24-148">In Internet Explorer, locate and open http://<contoso_computername>/certsrv/Default.asp.</span></span>  
  
2.  <span data-ttu-id="59f24-149">Default.asp ページで、次のようにクリックします。 **CA 証明書、証明書チェーン、または CRL のダウンロード**します。</span><span class="sxs-lookup"><span data-stu-id="59f24-149">On the Default.asp page, click **Download a CA certificate, certificate chain, or CRL**.</span></span>  
  
3.  <span data-ttu-id="59f24-150">確認します**現在 [Contoso-fabrikamca]** でが選択されている、 **CA 証明書**ボックスの一覧をクリックして**CA 証明書のダウンロード**します。</span><span class="sxs-lookup"><span data-stu-id="59f24-150">Make sure that **Current[Contoso-FabrikamCA]** is selected in the **CA Certificate** list, and then click **Download CA Certificate**.</span></span>  
  
4.  <span data-ttu-id="59f24-151">Contoso と Fabrikam のコンピューターの両方で、証明書を C:\Certs\Contoso-FabrikamCA.cer に保存します。</span><span class="sxs-lookup"><span data-stu-id="59f24-151">Save the certificate to C:\Certs\Contoso-FabrikamCA.cer on both the Contoso and the Fabrikam computer.</span></span>  
  
### <a name="to-import-the-ca-certificate-to-the-trusted-root-certification-authorities-store"></a><span data-ttu-id="59f24-152">信頼されたルート証明機関ストアに CA 証明書をインポートするには</span><span class="sxs-lookup"><span data-stu-id="59f24-152">To import the CA certificate to the Trusted Root Certification Authorities store</span></span>  
  
1.  <span data-ttu-id="59f24-153">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="59f24-153">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="59f24-154">コマンド プロンプトに移動します**\<ドライブ\>: \Program Files\MicrosoftBizTalk\<バージョン\>Accelerator for rosettanet \sdk**、キーを押しますと **」と入力。**.</span><span class="sxs-lookup"><span data-stu-id="59f24-154">At the command prompt, move to **\<drive\>:\Program Files\MicrosoftBizTalk \<version\> Accelerator for RosettaNet\SDK**, and then press **Enter**.</span></span>  
  
3.  <span data-ttu-id="59f24-155">コマンド プロンプトで「 **CertWizard/Rootkey"\<ドライブ\>: \Certs\Contoso-FabrikamCA.cer"**、押します **」と入力**します。</span><span class="sxs-lookup"><span data-stu-id="59f24-155">At the command prompt, type **CertWizard /Rootkey "\<drive\>:\Certs\Contoso-FabrikamCA.cer"**, and then press **Enter**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="59f24-156">この手順は、Contoso と Fabrikam の両方のコンピューターで実行します。</span><span class="sxs-lookup"><span data-stu-id="59f24-156">Perform this procedure on both the Contoso and Fabrikam computers.</span></span>  
  
### <a name="to-enable-automatic-certificate-issuing"></a><span data-ttu-id="59f24-157">証明書の自動発行を有効にするには</span><span class="sxs-lookup"><span data-stu-id="59f24-157">To enable automatic certificate issuing</span></span>  
  
1.  <span data-ttu-id="59f24-158">証明機関として使用するコンピューターで、次のようにクリックします**開始**、 をポイント**プログラム**、 をポイント**管理ツール**、 をクリックし、  **。証明機関**します。</span><span class="sxs-lookup"><span data-stu-id="59f24-158">On the computer you used as the Certification Authority, click **Start**, point to **Programs**, point to **Administrative Tools**, and then click **Certification Authority**.</span></span>  
  
2.  <span data-ttu-id="59f24-159">証明機関 ダイアログ ボックスで右クリックして**Contoso-fabrikamca**、 をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="59f24-159">In the Certification Authority dialog box, right-click **Contoso-FabrikamCA**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="59f24-160">Contoso-fabrikamca のプロパティ ダイアログ ボックスで、上、**ポリシー モジュール** タブで **プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="59f24-160">In the Contoso-FabrikamCA Properties dialog box, on the **Policy Module** tab, click **Properties**.</span></span>  
  
4.  <span data-ttu-id="59f24-161">プロパティ ダイアログ ボックスで、次のように選択します。**証明書テンプレートの設定に従う**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="59f24-161">In the Properties dialog box, select **Follow the settings in the certificate template**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="59f24-162">クリックして**OK** Contoso-fabrikamca ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="59f24-162">Click **OK** to close the Contoso-FabrikamCA dialog box.</span></span>  
  
6.  <span data-ttu-id="59f24-163">証明機関 ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="59f24-163">Close the Certification Authority dialog box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="59f24-164">自動証明書の発行を有効にすると、証明書サービスには、証明書発行手続きが自動化されます。</span><span class="sxs-lookup"><span data-stu-id="59f24-164">By enabling automatic certificate issuing, Certificate Services automates the certificate issuing procedure.</span></span> <span data-ttu-id="59f24-165">この変更を適用する証明書サービスを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="59f24-165">You will have to restart Certificate Services to apply this change.</span></span>  
    >   
    >  <span data-ttu-id="59f24-166">現在のユーザー \ 信頼されたルート証明機関のルート証明書 Contoso-fabrikamca.cer をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="59f24-166">You may need to install the Root Certificate Contoso-FabrikamCA.cer in the Current User\Trusted Root Certification authorities.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59f24-167">参照</span><span class="sxs-lookup"><span data-stu-id="59f24-167">See Also</span></span>  
 [<span data-ttu-id="59f24-168">手順 2:パブリックおよびプライベート証明書の作成</span><span class="sxs-lookup"><span data-stu-id="59f24-168">Step 2: Creating Public and Private Certificates</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-public-and-private-certificates.md)