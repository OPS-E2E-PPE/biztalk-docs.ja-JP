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
# <a name="step-3-importing-public-and-private-certificates"></a><span data-ttu-id="fbc16-102">手順 3: パブリックおよびプライベート証明書のインポート</span><span class="sxs-lookup"><span data-stu-id="fbc16-102">Step 3: Importing Public and Private Certificates</span></span>
<span data-ttu-id="fbc16-103">この手順で作成した証明書をインポートする[手順 2: を作成するパブリックおよびプライベート証明書 &#91;RN3 &#93;](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-public-and-private-certificates.md) Contoso と Fabrikam のコンピューターにします。</span><span class="sxs-lookup"><span data-stu-id="fbc16-103">In this step, you import the certificates you created in [Step 2: Creating Public and Private Certificates &#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-public-and-private-certificates.md) to the Contoso and Fabrikam computers.</span></span> <span data-ttu-id="fbc16-104">各コンピュータは独自のプライベート証明書と他の組織のパブリック証明書をインポートします。</span><span class="sxs-lookup"><span data-stu-id="fbc16-104">Each computer imports its own private certificates and imports the public certificates of the other organization.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fbc16-105">Fabrikam のプライベート証明書と Contoso のパブリック証明書を Fabrikam のコンピューターに転送して、インポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fbc16-105">You have to transfer the Fabrikam private certificates and Contoso public certificates to the Fabrikam computer to import them.</span></span> <span data-ttu-id="fbc16-106">ここでは、Fabrikam のコンピューターの C:\Certs フォルダーにこれらの証明書をコピーします。</span><span class="sxs-lookup"><span data-stu-id="fbc16-106">This step assumes that you put these certificates in the C:\Certs folder on the Fabrikam computer.</span></span>  
  
### <a name="to-import-the-contoso-private-certificates-on-the-contoso-computer"></a><span data-ttu-id="fbc16-107">Contoso のコンピューターで Contoso のプライベート証明書をインポートするには</span><span class="sxs-lookup"><span data-stu-id="fbc16-107">To import the Contoso private certificates on the Contoso computer</span></span>  
  
1.  <span data-ttu-id="fbc16-108">Contoso のコンピューターでをクリックして**開始**、 をクリックして**実行**、型**cmd**、クリックして**ok**です。</span><span class="sxs-lookup"><span data-stu-id="fbc16-108">On the Contoso computer, click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="fbc16-109">コマンド プロンプトでに移動 **\<** *ドライブ***>: \Program Files\Microsoft BizTalk\<バージョン > Accelerator for rosettanet \sdk**キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="fbc16-109">At the command prompt, move to **\<***drive***>:\Program Files\Microsoft BizTalk \<version> Accelerator for RosettaNet\SDK** and then press **Enter**.</span></span>  
  
3.  <span data-ttu-id="fbc16-110">コマンド プロンプトで次のように入力します**CertWizard/Privatekey"\<***ドライブ***>: \Certs\Contoso Private Encryption.pfx"**、キーを押します**。入力**です。</span><span class="sxs-lookup"><span data-stu-id="fbc16-110">At the command prompt, type **CertWizard /Privatekey "\<***drive***>:\Certs\Contoso Private Encryption.pfx"**, and then press **Enter**.</span></span>  
  
4.  <span data-ttu-id="fbc16-111">**証明書ファイルのパスワードを入力してください**プロンプトで「 **mysecret**、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="fbc16-111">At the **Please enter the password for the certificate file** prompt, type **mysecret**, and then press **Enter**.</span></span>  
  
5.  <span data-ttu-id="fbc16-112">**Identity < contoso_machine > \HostSvc のパスワードの入力**プロンプトで HostSvc アカウント パスワードを入力して、、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="fbc16-112">At the **Enter password for identity <contoso_machine>\HostSvc** prompt, type the HostSvc account password, and then press **Enter**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fbc16-113">BizTalkServerApplication を HostSvc 以外のアカウント名で実行している場合は、プロンプトが異なります。</span><span class="sxs-lookup"><span data-stu-id="fbc16-113">If your BizTalkServerApplication runs under an account name other than HostSvc, the prompt must be different.</span></span>  
  
6.  <span data-ttu-id="fbc16-114">**このホーム証明書が使用する**プロンプトで「 **D**、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="fbc16-114">At the **This home certificate will be used for** prompt, type **D**, and then press **Enter**.</span></span>  
  
     <span data-ttu-id="fbc16-115">CertWizard は、BizTalkServerApplication ホストと BizTalkServerIsolatedHost ホストの実行に使用しているユーザー アカウントの \Personal\Certificates ストアに、証明書をインポートします。</span><span class="sxs-lookup"><span data-stu-id="fbc16-115">The CertWizard imports the certificate into the \Personal\Certificates store for the user accounts that BizTalkServerApplication and BizTalkServerIsolatedHost hosts run under.</span></span>  
  
7.  <span data-ttu-id="fbc16-116">手順 3 ~ 6」と入力して、署名証明書であることを指定する Contoso Private Signature.pfx 証明書を**S**で、**このホーム証明書が使用する**手順 6 で書き留めたプロンプトです。</span><span class="sxs-lookup"><span data-stu-id="fbc16-116">Repeat steps 3-6 for the Contoso Private Signature.pfx certificate specifying that it is a signature certificate by typing **S** at the **This home certificate will be used for** prompt noted in step 6.</span></span>  
  
### <a name="to-import-the-fabrikam-public-certificates-on-the-contoso-computer"></a><span data-ttu-id="fbc16-117">Contoso のコンピュータで Fabrikam のパブリック証明書をインポートするには</span><span class="sxs-lookup"><span data-stu-id="fbc16-117">To import the Fabrikam public certificates on the Contoso computer</span></span>  
  
1.  <span data-ttu-id="fbc16-118">Contoso のコンピューターでをクリックして**開始**、 をクリックして**実行、**型**cmd**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="fbc16-118">On the Contoso computer, click **Start**, click **Run,** type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="fbc16-119">コマンド プロンプトでに移動*\<ドライブ >***: \Program Files\Microsoft BizTalk\<バージョン > Accelerator for rosettanet \sdk**キーを押します**を入力してください**.</span><span class="sxs-lookup"><span data-stu-id="fbc16-119">At the command prompt, move to *\<drive>***:\Program Files\Microsoft BizTalk \<version> Accelerator for RosettaNet\SDK** and then press **Enter**.</span></span>  
  
3.  <span data-ttu-id="fbc16-120">コマンド プロンプトで次のように入力します**CertWizard/Publickey"***\<ドライブ >***: \Certs\Fabrikam Public Encryption.cer"**、キーを押します**。入力**です。</span><span class="sxs-lookup"><span data-stu-id="fbc16-120">At the command prompt, type **CertWizard /Publickey "***\<drive>***:\Certs\Fabrikam Public Encryption.cer"**, and then press **Enter**.</span></span>  
  
4.  <span data-ttu-id="fbc16-121">Fabrikam Public Signature.cer 証明書について、手順 3. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="fbc16-121">Repeat step 3 for the Fabrikam Public Signature.cer certificate.</span></span>  
  
### <a name="to-import-the-fabrikam-private-certificates-on-the-fabrikam-computer"></a><span data-ttu-id="fbc16-122">Fabrikam のコンピューターで Fabrikam のプライベート証明書をインポートするには</span><span class="sxs-lookup"><span data-stu-id="fbc16-122">To import the Fabrikam private certificates on the Fabrikam computer</span></span>  
  
1.  <span data-ttu-id="fbc16-123">Contoso のコンピューターから次のファイルをコピー、\<ドライブ >: \Certs フォルダーに、Fabrikam のコンピューター: Contoso Public Encryption.cer、Contoso Public Signature.cer、Fabrikam Private Encryption.pfx、Fabrikam Private Signature.pfx とします。</span><span class="sxs-lookup"><span data-stu-id="fbc16-123">Copy the following files from the Contoso computer to the \<drive>:\Certs folder on the Fabrikam computer: Contoso Public Encryption.cer, Contoso Public Signature.cer, Fabrikam Private Encryption.pfx, and Fabrikam Private Signature.pfx.</span></span>  
  
2.  <span data-ttu-id="fbc16-124">Fabrikum コンピューターで、をクリックして**開始**、 をクリックして**実行**、型**cmd**、クリックして**ok**です。</span><span class="sxs-lookup"><span data-stu-id="fbc16-124">On the Fabrikum computer, click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="fbc16-125">コマンド プロンプトでに移動*\<ドライブ >***: \Program Files\Microsoft BizTalk\<バージョン > Accelerator for rosettanet \sdk**キーを押します**を入力してください**.</span><span class="sxs-lookup"><span data-stu-id="fbc16-125">At the command prompt, move to *\<drive>***:\Program Files\Microsoft BizTalk \<version> Accelerator for RosettaNet\SDK** and then press **Enter**.</span></span>  
  
4.  <span data-ttu-id="fbc16-126">コマンド プロンプトで次のように入力します**CertWizard/Privatekey"***\<ドライブ >***: \Certs\Fabrikam Private Encryption.pfx"**、キーを押します**。入力**です。</span><span class="sxs-lookup"><span data-stu-id="fbc16-126">At the command prompt, type **CertWizard /Privatekey "***\<drive>***:\Certs\Fabrikam Private Encryption.pfx"**, and then press **Enter**.</span></span>  
  
5.  <span data-ttu-id="fbc16-127">**証明書ファイルのパスワードを入力してください**プロンプトで「 **mysecret**、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="fbc16-127">At the **Please enter the password for the certificate file** prompt, type **mysecret**, and then press **Enter**.</span></span>  
  
6.  <span data-ttu-id="fbc16-128">**Identity < fabrikam_machine > \HostSvc のパスワードの入力**プロンプトで HostSvc アカウント パスワードを入力して、、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="fbc16-128">At the **Enter password for identity <fabrikam_machine>\HostSvc** prompt, type the HostSvc account password, and then press **Enter**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fbc16-129">BizTalkServerApplication を HostSvc 以外のアカウント名で実行している場合は、プロンプトが異なります。</span><span class="sxs-lookup"><span data-stu-id="fbc16-129">If your BizTalkServerApplication runs under an account name other than HostSvc, the prompt must be different.</span></span>  
  
7.  <span data-ttu-id="fbc16-130">**このホーム証明書が使用する**プロンプトで「 **D**、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="fbc16-130">At the **This home certificate will be used for** prompt, type **D**, and then press **Enter**.</span></span>  
  
     <span data-ttu-id="fbc16-131">CertWizard は、BizTalkServerApplication ホストと BizTalkServerIsolatedHost ホストの実行に使用しているユーザー アカウントの \Personal\Certificates ストアに、証明書をインポートします。</span><span class="sxs-lookup"><span data-stu-id="fbc16-131">The CertWizard imports the certificate into the \Personal\Certificates store for the user accounts that BizTalkServerApplication and BizTalkServerIsolatedHost hosts run under.</span></span>  
  
8.  <span data-ttu-id="fbc16-132">手順 4 ~ 7」と入力して、署名証明書であることを指定する Fabrikam Private Signature.pfx 証明書を**S**で、**このホーム証明書が使用する**手順 6. でダイアログを表示します。</span><span class="sxs-lookup"><span data-stu-id="fbc16-132">Repeat steps 4-7 for the Fabrikam Private Signature.pfx certificate specifying that it is a signature certificate by typing **S** at the **This home certificate will be used for** prompt in step 6.</span></span>  
  
### <a name="to-import-the-contoso-public-certificates-on-the-fabrikam-computer"></a><span data-ttu-id="fbc16-133">Fabrikam のコンピューターで Contoso のパブリック証明書をインポートするには</span><span class="sxs-lookup"><span data-stu-id="fbc16-133">To import the Contoso public certificates on the Fabrikam computer</span></span>  
  
1.  <span data-ttu-id="fbc16-134">Fabrikum コンピューターで、をクリックして**開始**、 をクリックして**実行**、型**cmd**、クリックして**ok**です。</span><span class="sxs-lookup"><span data-stu-id="fbc16-134">On the Fabrikum computer, click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="fbc16-135">コマンド プロンプトでに移動*\<ドライブ >***: \Program Files\Microsoft BizTalk\<バージョン > Accelerator for rosettanet \sdk**キーを押します**を入力してください**.</span><span class="sxs-lookup"><span data-stu-id="fbc16-135">At the command prompt, move to *\<drive>***:\Program Files\Microsoft BizTalk \<version> Accelerator for RosettaNet\SDK** and then press **Enter**.</span></span>  
  
3.  <span data-ttu-id="fbc16-136">コマンド プロンプトで次のように入力します**CertWizard/Publickey"***\<ドライブ >***: \Certs\Contoso Public Encryption.cer"**、キーを押します**。入力**です。</span><span class="sxs-lookup"><span data-stu-id="fbc16-136">At the command prompt, type **CertWizard /Publickey "***\<drive>***:\Certs\Contoso Public Encryption.cer"**, and then press **Enter**.</span></span>  
  
4.  <span data-ttu-id="fbc16-137">Contoso Public Signature.cer 証明書について、手順 3. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="fbc16-137">Repeat step 3 for the Contoso Public Signature.cer certificate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbc16-138">参照</span><span class="sxs-lookup"><span data-stu-id="fbc16-138">See Also</span></span>  
 [<span data-ttu-id="fbc16-139">手順 4: IIS でレイヤーをソケット セキュリティで保護を有効にします。</span><span class="sxs-lookup"><span data-stu-id="fbc16-139">Step 4: Enabling Secure Sockets Layer in IIS</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-4-enabling-secure-sockets-layer-in-iis.md)