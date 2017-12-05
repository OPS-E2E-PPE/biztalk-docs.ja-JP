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
ms.openlocfilehash: 46d087c44cac350df2d58c880303668b5c3e0c24
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="step-3-importing-public-and-private-certificates"></a><span data-ttu-id="3f8b3-102">手順 3: パブリックおよびプライベート証明書のインポート</span><span class="sxs-lookup"><span data-stu-id="3f8b3-102">Step 3: Importing Public and Private Certificates</span></span>
<span data-ttu-id="3f8b3-103">この手順で作成した証明書をインポートする[手順 2: を作成するパブリックおよびプライベート証明書 &#91;RN3 &#93;](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-public-and-private-certificates.md) Contoso と Fabrikam のコンピューターにします。</span><span class="sxs-lookup"><span data-stu-id="3f8b3-103">In this step, you import the certificates you created in [Step 2: Creating Public and Private Certificates &#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-public-and-private-certificates.md) to the Contoso and Fabrikam computers.</span></span> <span data-ttu-id="3f8b3-104">各コンピュータは独自のプライベート証明書と他の組織のパブリック証明書をインポートします。</span><span class="sxs-lookup"><span data-stu-id="3f8b3-104">Each computer imports its own private certificates and imports the public certificates of the other organization.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3f8b3-105">Fabrikam のプライベート証明書と Contoso のパブリック証明書を Fabrikam のコンピューターに転送して、インポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f8b3-105">You have to transfer the Fabrikam private certificates and Contoso public certificates to the Fabrikam computer to import them.</span></span> <span data-ttu-id="3f8b3-106">ここでは、Fabrikam のコンピューターの C:\Certs フォルダーにこれらの証明書をコピーします。</span><span class="sxs-lookup"><span data-stu-id="3f8b3-106">This step assumes that you put these certificates in the C:\Certs folder on the Fabrikam computer.</span></span>  
  
### <a name="to-import-the-contoso-private-certificates-on-the-contoso-computer"></a><span data-ttu-id="3f8b3-107">Contoso のコンピューターで Contoso のプライベート証明書をインポートするには</span><span class="sxs-lookup"><span data-stu-id="3f8b3-107">To import the Contoso private certificates on the Contoso computer</span></span>  
  
1.  <span data-ttu-id="3f8b3-108">Contoso のコンピューターでをクリックして**開始**、 をクリックして**実行**、型**cmd**、クリックして**ok**です。</span><span class="sxs-lookup"><span data-stu-id="3f8b3-108">On the Contoso computer, click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="3f8b3-109">コマンド プロンプトでに移動 **\<** *ドライブ***\>: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator forRosettanet \sdk**キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="3f8b3-109">At the command prompt, move to **\<***drive***\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK** and then press **Enter**.</span></span>  
  
3.  <span data-ttu-id="3f8b3-110">コマンド プロンプトで次のように入力します**CertWizard/Privatekey"\<***ドライブ***\>: \Certs\Contoso Private Encryption.pfx"**、キーを押します。**入力**です。</span><span class="sxs-lookup"><span data-stu-id="3f8b3-110">At the command prompt, type **CertWizard /Privatekey "\<***drive***\>:\Certs\Contoso Private Encryption.pfx"**, and then press **Enter**.</span></span>  
  
4.  <span data-ttu-id="3f8b3-111">**証明書ファイルのパスワードを入力してください**プロンプトで「 **mysecret**、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="3f8b3-111">At the **Please enter the password for the certificate file** prompt, type **mysecret**, and then press **Enter**.</span></span>  
  
5.  <span data-ttu-id="3f8b3-112">**Identity < contoso_machine > \HostSvc のパスワードの入力**プロンプトで HostSvc アカウント パスワードを入力して、、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="3f8b3-112">At the **Enter password for identity <contoso_machine>\HostSvc** prompt, type the HostSvc account password, and then press **Enter**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3f8b3-113">BizTalkServerApplication を HostSvc 以外のアカウント名で実行している場合は、プロンプトが異なります。</span><span class="sxs-lookup"><span data-stu-id="3f8b3-113">If your BizTalkServerApplication runs under an account name other than HostSvc, the prompt must be different.</span></span>  
  
6.  <span data-ttu-id="3f8b3-114">**このホーム証明書が使用する**プロンプトで「 **D**、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="3f8b3-114">At the **This home certificate will be used for** prompt, type **D**, and then press **Enter**.</span></span>  
  
     <span data-ttu-id="3f8b3-115">CertWizard は、BizTalkServerApplication ホストと BizTalkServerIsolatedHost ホストの実行に使用しているユーザー アカウントの \Personal\Certificates ストアに、証明書をインポートします。</span><span class="sxs-lookup"><span data-stu-id="3f8b3-115">The CertWizard imports the certificate into the \Personal\Certificates store for the user accounts that BizTalkServerApplication and BizTalkServerIsolatedHost hosts run under.</span></span>  
  
7.  <span data-ttu-id="3f8b3-116">手順 3 ~ 6」と入力して、署名証明書であることを指定する Contoso Private Signature.pfx 証明書を**S**で、**このホーム証明書が使用する**手順 6 で書き留めたプロンプトです。</span><span class="sxs-lookup"><span data-stu-id="3f8b3-116">Repeat steps 3-6 for the Contoso Private Signature.pfx certificate specifying that it is a signature certificate by typing **S** at the **This home certificate will be used for** prompt noted in step 6.</span></span>  
  
### <a name="to-import-the-fabrikam-public-certificates-on-the-contoso-computer"></a><span data-ttu-id="3f8b3-117">Contoso のコンピュータで Fabrikam のパブリック証明書をインポートするには</span><span class="sxs-lookup"><span data-stu-id="3f8b3-117">To import the Fabrikam public certificates on the Contoso computer</span></span>  
  
1.  <span data-ttu-id="3f8b3-118">Contoso のコンピューターでをクリックして**開始**、 をクリックして**実行、**型**cmd**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="3f8b3-118">On the Contoso computer, click **Start**, click **Run,** type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="3f8b3-119">コマンド プロンプトでに移動*\<ドライブ\>***: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk**し、キーを押して**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="3f8b3-119">At the command prompt, move to *\<drive\>***:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK** and then press **Enter**.</span></span>  
  
3.  <span data-ttu-id="3f8b3-120">コマンド プロンプトで次のように入力します**CertWizard/Publickey"***\<ドライブ\>***: \Certs\Fabrikam Public Encryption.cer"**、キーを押します。**入力**です。</span><span class="sxs-lookup"><span data-stu-id="3f8b3-120">At the command prompt, type **CertWizard /Publickey "***\<drive\>***:\Certs\Fabrikam Public Encryption.cer"**, and then press **Enter**.</span></span>  
  
4.  <span data-ttu-id="3f8b3-121">Fabrikam Public Signature.cer 証明書について、手順 3. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="3f8b3-121">Repeat step 3 for the Fabrikam Public Signature.cer certificate.</span></span>  
  
### <a name="to-import-the-fabrikam-private-certificates-on-the-fabrikam-computer"></a><span data-ttu-id="3f8b3-122">Fabrikam のコンピューターで Fabrikam のプライベート証明書をインポートするには</span><span class="sxs-lookup"><span data-stu-id="3f8b3-122">To import the Fabrikam private certificates on the Fabrikam computer</span></span>  
  
1.  <span data-ttu-id="3f8b3-123">Contoso のコンピューターから次のファイルをコピー、\<ドライブ\>: \Certs フォルダーに、Fabrikam のコンピューター: Contoso Public Encryption.cer、Contoso Public Signature.cer、Fabrikam Private Encryption.pfx、Fabrikam PrivateSignature.pfx です。</span><span class="sxs-lookup"><span data-stu-id="3f8b3-123">Copy the following files from the Contoso computer to the \<drive\>:\Certs folder on the Fabrikam computer: Contoso Public Encryption.cer, Contoso Public Signature.cer, Fabrikam Private Encryption.pfx, and Fabrikam Private Signature.pfx.</span></span>  
  
2.  <span data-ttu-id="3f8b3-124">Fabrikum コンピューターで、をクリックして**開始**、 をクリックして**実行**、型**cmd**、クリックして**ok**です。</span><span class="sxs-lookup"><span data-stu-id="3f8b3-124">On the Fabrikum computer, click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="3f8b3-125">コマンド プロンプトでに移動*\<ドライブ\>***: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk**し、キーを押して**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="3f8b3-125">At the command prompt, move to *\<drive\>***:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK** and then press **Enter**.</span></span>  
  
4.  <span data-ttu-id="3f8b3-126">コマンド プロンプトで次のように入力します**CertWizard/Privatekey"***\<ドライブ\>***: \Certs\Fabrikam Private Encryption.pfx"**、キーを押します。**入力**です。</span><span class="sxs-lookup"><span data-stu-id="3f8b3-126">At the command prompt, type **CertWizard /Privatekey "***\<drive\>***:\Certs\Fabrikam Private Encryption.pfx"**, and then press **Enter**.</span></span>  
  
5.  <span data-ttu-id="3f8b3-127">**証明書ファイルのパスワードを入力してください**プロンプトで「 **mysecret**、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="3f8b3-127">At the **Please enter the password for the certificate file** prompt, type **mysecret**, and then press **Enter**.</span></span>  
  
6.  <span data-ttu-id="3f8b3-128">**Identity < fabrikam_machine > \HostSvc のパスワードの入力**プロンプトで HostSvc アカウント パスワードを入力して、、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="3f8b3-128">At the **Enter password for identity <fabrikam_machine>\HostSvc** prompt, type the HostSvc account password, and then press **Enter**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3f8b3-129">BizTalkServerApplication を HostSvc 以外のアカウント名で実行している場合は、プロンプトが異なります。</span><span class="sxs-lookup"><span data-stu-id="3f8b3-129">If your BizTalkServerApplication runs under an account name other than HostSvc, the prompt must be different.</span></span>  
  
7.  <span data-ttu-id="3f8b3-130">**このホーム証明書が使用する**プロンプトで「 **D**、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="3f8b3-130">At the **This home certificate will be used for** prompt, type **D**, and then press **Enter**.</span></span>  
  
     <span data-ttu-id="3f8b3-131">CertWizard は、BizTalkServerApplication ホストと BizTalkServerIsolatedHost ホストの実行に使用しているユーザー アカウントの \Personal\Certificates ストアに、証明書をインポートします。</span><span class="sxs-lookup"><span data-stu-id="3f8b3-131">The CertWizard imports the certificate into the \Personal\Certificates store for the user accounts that BizTalkServerApplication and BizTalkServerIsolatedHost hosts run under.</span></span>  
  
8.  <span data-ttu-id="3f8b3-132">手順 4 ~ 7」と入力して、署名証明書であることを指定する Fabrikam Private Signature.pfx 証明書を**S**で、**このホーム証明書が使用する**手順 6. でダイアログを表示します。</span><span class="sxs-lookup"><span data-stu-id="3f8b3-132">Repeat steps 4-7 for the Fabrikam Private Signature.pfx certificate specifying that it is a signature certificate by typing **S** at the **This home certificate will be used for** prompt in step 6.</span></span>  
  
### <a name="to-import-the-contoso-public-certificates-on-the-fabrikam-computer"></a><span data-ttu-id="3f8b3-133">Fabrikam のコンピューターで Contoso のパブリック証明書をインポートするには</span><span class="sxs-lookup"><span data-stu-id="3f8b3-133">To import the Contoso public certificates on the Fabrikam computer</span></span>  
  
1.  <span data-ttu-id="3f8b3-134">Fabrikum コンピューターで、をクリックして**開始**、 をクリックして**実行**、型**cmd**、クリックして**ok**です。</span><span class="sxs-lookup"><span data-stu-id="3f8b3-134">On the Fabrikum computer, click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="3f8b3-135">コマンド プロンプトでに移動*\<ドライブ\>***: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk**し、キーを押して**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="3f8b3-135">At the command prompt, move to *\<drive\>***:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK** and then press **Enter**.</span></span>  
  
3.  <span data-ttu-id="3f8b3-136">コマンド プロンプトで次のように入力します**CertWizard/Publickey"***\<ドライブ\>***: \Certs\Contoso Public Encryption.cer"**、キーを押します。**入力**です。</span><span class="sxs-lookup"><span data-stu-id="3f8b3-136">At the command prompt, type **CertWizard /Publickey "***\<drive\>***:\Certs\Contoso Public Encryption.cer"**, and then press **Enter**.</span></span>  
  
4.  <span data-ttu-id="3f8b3-137">Contoso Public Signature.cer 証明書について、手順 3. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="3f8b3-137">Repeat step 3 for the Contoso Public Signature.cer certificate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f8b3-138">参照</span><span class="sxs-lookup"><span data-stu-id="3f8b3-138">See Also</span></span>  
 [<span data-ttu-id="3f8b3-139">手順 4: IIS で Secure Sockets Layer の有効化</span><span class="sxs-lookup"><span data-stu-id="3f8b3-139">Step 4: Enabling Secure Sockets Layer in IIS</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-4-enabling-secure-sockets-layer-in-iis.md)