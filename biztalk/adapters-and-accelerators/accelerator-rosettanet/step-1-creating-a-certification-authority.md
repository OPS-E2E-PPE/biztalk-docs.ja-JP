---
title: "手順 1: 証明機関の作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- certificates, creating
- double action tutorial, creating certificates
- creating, certificates
ms.assetid: b6ecd534-6b03-4336-8337-33ec18a0802a
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3d796608a4cc323ccf5e1a8bdee7420c5bab259
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="step-1-creating-a-certification-authority"></a><span data-ttu-id="c90bb-102">手順 1: 証明機関の作成</span><span class="sxs-lookup"><span data-stu-id="c90bb-102">Step 1: Creating a Certification Authority</span></span>
<span data-ttu-id="c90bb-103">ここでは、証明書サービス [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] コンポーネントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="c90bb-103">In this topic, you install the Certificate Services [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] component.</span></span> <span data-ttu-id="c90bb-104">このコンポーネントを使用して、セキュリティで保護された通信を Contoso 組織と Fabrikam 組織の間で確立するために必要な証明書を生成します。</span><span class="sxs-lookup"><span data-stu-id="c90bb-104">You use it to generate the certificates that you need to promote secure communication between the Contoso and Fabrikam organizations.</span></span> <span data-ttu-id="c90bb-105">各取引先は、通信のための秘密暗号化証明書と、識別のための秘密署名証明書を所有します。</span><span class="sxs-lookup"><span data-stu-id="c90bb-105">Each trading partner will have a private encryption certificate for communication and a private signature certificate for identification purposes.</span></span> <span data-ttu-id="c90bb-106">さらに、パートナーは 3A2 PIP (Partner Interface Process) の実装時に、セキュリティで保護された通信を確立するために公開キー証明書をお互いに共有します。</span><span class="sxs-lookup"><span data-stu-id="c90bb-106">Additionally, the partners will share their public key certificates with each other to promote secure communication when implementing the 3A2 Partner Interface Process (PIP).</span></span>  
  
### <a name="to-install-the-certificate-server"></a><span data-ttu-id="c90bb-107">証明書サーバーをインストールするには</span><span class="sxs-lookup"><span data-stu-id="c90bb-107">To install the certificate server</span></span>  
  
1.  <span data-ttu-id="c90bb-108">をクリックして**開始**、] をポイント**設定**、順にクリック**コントロール パネルの [**です。</span><span class="sxs-lookup"><span data-stu-id="c90bb-108">Click **Start**, point to **Settings**, and then click **Control Panel**.</span></span> <span data-ttu-id="c90bb-109">ダブルクリックして**追加または削除するプログラム**です。</span><span class="sxs-lookup"><span data-stu-id="c90bb-109">Double-click **Add or Remove Programs**.</span></span>  
  
2.  <span data-ttu-id="c90bb-110">**プログラム追加と削除**ダイアログ ボックスで、をクリックして**Windows コンポーネントの追加/削除**です。</span><span class="sxs-lookup"><span data-stu-id="c90bb-110">In the **Add or Remove Programs** dialog box, click **Add/Remove Windows Components**.</span></span>  
  
3.  <span data-ttu-id="c90bb-111">**Windows コンポーネント ウィザード** ページの 、**コンポーネント**セクションで、**証明書サービス**、 をクリックして**はい**、 をクリックし、**次**コンポーネントの構成ウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="c90bb-111">On the **Windows Components Wizard** page, in the **Components** section, select **Certificate Services**, click **Yes**, and then click **Next** to start the Configuring Components Wizard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c90bb-112">場合、**証明書 ServicesWindows**コンポーネントが既に選択されている、この手順の残りの部分をスキップします。</span><span class="sxs-lookup"><span data-stu-id="c90bb-112">If the **Certificates ServicesWindows** component is already selected, skip the rest of this procedure.</span></span>  
  
4.  <span data-ttu-id="c90bb-113">**CA の種類** ページで、ことを確認して**スタンドアロン ルート CA**を選択して、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="c90bb-113">On the **CA Type** page, make sure that **Stand-alone root CA** is selected, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="c90bb-114">**CA 識別情報**] ページの [、**この CA の共通名**ボックスに、入力**Contoso-fabrikamca**、順にクリック**次**です。</span><span class="sxs-lookup"><span data-stu-id="c90bb-114">On the **CA Identifying Information** page, in the **Common name for this CA** box, type **Contoso-FabrikamCA**, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="c90bb-115">**証明書のデータベース設定** ページで、既定値のままにしてをクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="c90bb-115">On the **Certificate Database Settings** page, leave the defaults, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="c90bb-116">をクリックして**はい**されたら、インターネット インフォメーション サービス (IIS) を停止します。</span><span class="sxs-lookup"><span data-stu-id="c90bb-116">Click **Yes** when the wizard prompts you to stop Internet Information Services (IIS).</span></span>  
  
8.  <span data-ttu-id="c90bb-117">をクリックして**はい**場合、**コンポーネントの構成ウィザード**Active Server Pages を有効にするように求められます。</span><span class="sxs-lookup"><span data-stu-id="c90bb-117">Click **Yes** if the **Configuring Components Wizard** prompts you to enable Active Server Pages.</span></span>  
  
9. <span data-ttu-id="c90bb-118">をクリックして**完了**を閉じる、 **Windows コンポーネント ウィザード**です。</span><span class="sxs-lookup"><span data-stu-id="c90bb-118">Click **Finish** to close the **Windows Components Wizard**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c90bb-119">証明機関として使用するコンピューターは 1 台のみです。</span><span class="sxs-lookup"><span data-stu-id="c90bb-119">You only have to use one computer as the Certification Authority.</span></span> <span data-ttu-id="c90bb-120">2 台目のコンピューターでこの手順を繰り返す必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c90bb-120">You do not have to repeat this step on the second computer.</span></span> <span data-ttu-id="c90bb-121">このチュートリアルでは、証明機関として Contoso のコンピューターを使用しています。</span><span class="sxs-lookup"><span data-stu-id="c90bb-121">This tutorial uses the Contoso computer as the Certification Authority.</span></span>  
  
### <a name="to-install-a-root-certification-authority-ca-for-windows-server-2008"></a><span data-ttu-id="c90bb-122">Windows Server 2008 向けのルート証明機関 (CA) をインストールするには</span><span class="sxs-lookup"><span data-stu-id="c90bb-122">To install a root Certification Authority (CA) for Windows Server 2008</span></span>  
  
1.  <span data-ttu-id="c90bb-123">サーバー マネージャーを開き、**役割の追加**の役割で、をクリックして**次**、 をクリック**Active Directory 証明書**サービス チェック ボックスです。</span><span class="sxs-lookup"><span data-stu-id="c90bb-123">Open Server Manager, click **Add Roles** in Roles, click **Next**, and click **Active Directory Certificate** Services check box.</span></span> <span data-ttu-id="c90bb-124">をクリックして**次**2 回クリックします。</span><span class="sxs-lookup"><span data-stu-id="c90bb-124">Click **Next** twice.</span></span>  
  
2.  <span data-ttu-id="c90bb-125">役割サービスの選択 ページで、**証明機関および証明機関 Web 登録**です。</span><span class="sxs-lookup"><span data-stu-id="c90bb-125">On the Select Role Services page, click **Certification Authority and Certification Authority Web Enrollment**.</span></span> <span data-ttu-id="c90bb-126">**[次へ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c90bb-126">Click **Next**.</span></span>  
  
3.  <span data-ttu-id="c90bb-127">セットアップの種類の指定 ページで、をクリックして**スタンドアロン**です。</span><span class="sxs-lookup"><span data-stu-id="c90bb-127">On the Specify Setup Type page, click **Standalone**.</span></span> <span data-ttu-id="c90bb-128">**[次へ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c90bb-128">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="c90bb-129">[CA の種類の指定] ページで、[ルート CA] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c90bb-129">On the Specify CA Type page, click Root CA.</span></span> <span data-ttu-id="c90bb-130">**[次へ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c90bb-130">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="c90bb-131">[秘密キーの設定] ページで、[新しい秘密キーを作成する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c90bb-131">On the Set Up Private Key page, click Create a new private key.</span></span> <span data-ttu-id="c90bb-132">**[次へ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c90bb-132">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="c90bb-133">[CA の暗号化を構成] ページで、</span><span class="sxs-lookup"><span data-stu-id="c90bb-133">On the Configure Cryptography for CA page.</span></span> <span data-ttu-id="c90bb-134">**[次へ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c90bb-134">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="c90bb-135">CA 名の構成でこの CA の共通名 Contoso-fabrikamca」と入力します。 クリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="c90bb-135">On Configure CA Name, in the Common name for this CA box, type Contoso-FabrikamCA, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="c90bb-136">有効期間の設定 ページで、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="c90bb-136">On the Set Validity Period page, click **Next**.</span></span>  
  
9. <span data-ttu-id="c90bb-137">証明書データベースの構成 ページで、**次**です。</span><span class="sxs-lookup"><span data-stu-id="c90bb-137">On the Configure Certificate Database page, Click **Next**.</span></span>  
  
10. <span data-ttu-id="c90bb-138">インストール オプションの確認 ページで、**インストール**です。</span><span class="sxs-lookup"><span data-stu-id="c90bb-138">On the Confirm Installation Options page, click **Install**.</span></span>  
  
### <a name="configuring-the-web-site-for-the-ca-to-use-https-authentication"></a><span data-ttu-id="c90bb-139">CA 用の Web サイトで HTTPS 認証を使用するための構成</span><span class="sxs-lookup"><span data-stu-id="c90bb-139">Configuring the Web site for the CA to use HTTPS authentication</span></span>  
  
1.  <span data-ttu-id="c90bb-140">証明機関として使用したコンピューターで、[スタート] ボタンをクリックし、[すべてのプログラム] をポイントします。次に、[管理ツール] をポイントし、[インターネット インフォメーション サービス (IIS) マネージャー] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c90bb-140">On the computer you used as the Certification Authority, click Start, point to All Programs, point to Administrative Tools, and then click Internet Information Services (IIS) Manager.</span></span>  
  
2.  <span data-ttu-id="c90bb-141">インターネット インフォメーション サービス (IIS) マネージャー] ダイアログ ボックスで、右クリックして**既定の Web サイトと [バインドの編集.**</span><span class="sxs-lookup"><span data-stu-id="c90bb-141">In the Internet Information Services (IIS) Manager dialog box, right click **Default Web Site and select Edit Bindings…**</span></span> <span data-ttu-id="c90bb-142">ポップアップ メニュー。</span><span class="sxs-lookup"><span data-stu-id="c90bb-142">from the popup menu.</span></span>  
  
3.  <span data-ttu-id="c90bb-143">[サイト バインド] ダイアログ ボックス**追加**です。</span><span class="sxs-lookup"><span data-stu-id="c90bb-143">In Site Bindings dialog box click **Add**.</span></span>  
  
4.  <span data-ttu-id="c90bb-144">サイト バインドの追加 ダイアログ ボックスで選択**https** 種類 から証明書を選択**SSL 証明書**ドロップダウンをクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="c90bb-144">In Add Site Binding dialog box select **https** in Type drop down, select the certificate from **SSL certificate** drop down and click **OK**.</span></span>  
  
5.  <span data-ttu-id="c90bb-145">をクリックして**閉じる**サイト バインドを閉じます.</span><span class="sxs-lookup"><span data-stu-id="c90bb-145">Click **Close** to close the Site Bindings…</span></span> <span data-ttu-id="c90bb-146">ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="c90bb-146">dialog box.</span></span>  
  
### <a name="to-download-the-ca-certificate"></a><span data-ttu-id="c90bb-147">CA 証明書をダウンロードするには</span><span class="sxs-lookup"><span data-stu-id="c90bb-147">To download the CA certificate</span></span>  
  
1.  <span data-ttu-id="c90bb-148">Internet Explorer で、http://<Contoso のコンピュータ名>/certsrv/Default.asp を開きます。</span><span class="sxs-lookup"><span data-stu-id="c90bb-148">In Internet Explorer, locate and open http://<contoso_computername>/certsrv/Default.asp.</span></span>  
  
2.  <span data-ttu-id="c90bb-149">Default.asp ページで、をクリックして**CA 証明書、証明書チェーン、または CRL のダウンロード**です。</span><span class="sxs-lookup"><span data-stu-id="c90bb-149">On the Default.asp page, click **Download a CA certificate, certificate chain, or CRL**.</span></span>  
  
3.  <span data-ttu-id="c90bb-150">確認して**現在 [Contoso-fabrikamca]**でが選択されている、 **CA 証明書**一覧をクリックして**CA 証明書のダウンロード**です。</span><span class="sxs-lookup"><span data-stu-id="c90bb-150">Make sure that **Current[Contoso-FabrikamCA]** is selected in the **CA Certificate** list, and then click **Download CA Certificate**.</span></span>  
  
4.  <span data-ttu-id="c90bb-151">証明書を Contoso および Fabrikam の両方のコンピューターの C:\Certs\Contoso-FabrikamCA.cer に保存します。</span><span class="sxs-lookup"><span data-stu-id="c90bb-151">Save the certificate to C:\Certs\Contoso-FabrikamCA.cer on both the Contoso and the Fabrikam computer.</span></span>  
  
### <a name="to-import-the-ca-certificate-to-the-trusted-root-certification-authorities-store"></a><span data-ttu-id="c90bb-152">信頼されたルート証明機関ストアに CA 証明書をインポートするには</span><span class="sxs-lookup"><span data-stu-id="c90bb-152">To import the CA certificate to the Trusted Root Certification Authorities store</span></span>  
  
1.  <span data-ttu-id="c90bb-153">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="c90bb-153">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="c90bb-154">コマンド プロンプトでに移動**\<ドライブ\>: \Program Files\MicrosoftBizTalk\<バージョン\>Accelerator for rosettanet \sdk**、キーを押します**を入力してください**.</span><span class="sxs-lookup"><span data-stu-id="c90bb-154">At the command prompt, move to **\<drive\>:\Program Files\MicrosoftBizTalk \<version\> Accelerator for RosettaNet\SDK**, and then press **Enter**.</span></span>  
  
3.  <span data-ttu-id="c90bb-155">コマンド プロンプトで次のように入力します。 **CertWizard/Rootkey"\<ドライブ\>: \Certs\Contoso-FabrikamCA.cer"**、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="c90bb-155">At the command prompt, type **CertWizard /Rootkey "\<drive\>:\Certs\Contoso-FabrikamCA.cer"**, and then press **Enter**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="c90bb-156">Contoso のコンピューターと Fabrikam のコンピューターの両方で、この手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c90bb-156">Perform this procedure on both the Contoso and Fabrikam computers.</span></span>  
  
### <a name="to-enable-automatic-certificate-issuing"></a><span data-ttu-id="c90bb-157">証明書の自動発行を有効にするには</span><span class="sxs-lookup"><span data-stu-id="c90bb-157">To enable automatic certificate issuing</span></span>  
  
1.  <span data-ttu-id="c90bb-158">コンピューターで証明機関として使用して、をクリックして**開始**、 をポイント**プログラム**、 をポイント**管理ツール**、クリックして**証明機関**です。</span><span class="sxs-lookup"><span data-stu-id="c90bb-158">On the computer you used as the Certification Authority, click **Start**, point to **Programs**, point to **Administrative Tools**, and then click **Certification Authority**.</span></span>  
  
2.  <span data-ttu-id="c90bb-159">証明機関 ダイアログ ボックスで右クリック**Contoso-fabrikamca**、クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="c90bb-159">In the Certification Authority dialog box, right-click **Contoso-FabrikamCA**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="c90bb-160">Contoso-fabrikamca のプロパティ ダイアログ ボックスで、**ポリシー モジュール** タブで、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="c90bb-160">In the Contoso-FabrikamCA Properties dialog box, on the **Policy Module** tab, click **Properties**.</span></span>  
  
4.  <span data-ttu-id="c90bb-161">プロパティ ダイアログ ボックスで選択**証明書テンプレートの設定に従う**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="c90bb-161">In the Properties dialog box, select **Follow the settings in the certificate template**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="c90bb-162">をクリックして**OK** Contoso-fabrikamca ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="c90bb-162">Click **OK** to close the Contoso-FabrikamCA dialog box.</span></span>  
  
6.  <span data-ttu-id="c90bb-163">[証明機関] ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="c90bb-163">Close the Certification Authority dialog box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c90bb-164">証明書の自動発行を有効にすると、証明書サービスにより証明書発行手続きが自動化されます。</span><span class="sxs-lookup"><span data-stu-id="c90bb-164">By enabling automatic certificate issuing, Certificate Services automates the certificate issuing procedure.</span></span> <span data-ttu-id="c90bb-165">この変更を適用するには、証明書サービスを再開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c90bb-165">You will have to restart Certificate Services to apply this change.</span></span>  
    >   
    >  <span data-ttu-id="c90bb-166">必要に応じて、Root Certificate Contoso-FabrikamCA.cer を "現在のユーザー\信頼されたルート証明機関" にインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="c90bb-166">You may need to install the Root Certificate Contoso-FabrikamCA.cer in the Current User\Trusted Root Certification authorities.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c90bb-167">参照</span><span class="sxs-lookup"><span data-stu-id="c90bb-167">See Also</span></span>  
 [<span data-ttu-id="c90bb-168">手順 2: パブリック証明書とプライベート証明書の作成</span><span class="sxs-lookup"><span data-stu-id="c90bb-168">Step 2: Creating Public and Private Certificates</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-public-and-private-certificates.md)