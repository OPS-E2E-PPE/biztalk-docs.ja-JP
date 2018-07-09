---
title: '手順 3: パブリックおよびプライベート証明書のインポート |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- public certificates
- importing certificates
- private certificates
- double action tutorial, importing certificates
- certificates, importing
ms.assetid: 955bdd69-9fbc-4100-ab8a-8f5dd4a17cbb
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18074fd3b72322d79e10895214352837ccf907bd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002347"
---
# <a name="step-3-importing-public-and-private-certificates"></a><span data-ttu-id="9c7d9-102">手順 3: パブリックおよびプライベート証明書のインポート</span><span class="sxs-lookup"><span data-stu-id="9c7d9-102">Step 3: Importing Public and Private Certificates</span></span>
<span data-ttu-id="9c7d9-103">作成した証明書をインポートするこの手順で[手順 2: を作成するパブリックおよびプライベート証明書&#91;RN3&#93; ](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-public-and-private-certificates.md) Contoso と Fabrikam のコンピューターにします。</span><span class="sxs-lookup"><span data-stu-id="9c7d9-103">In this step, you import the certificates you created in [Step 2: Creating Public and Private Certificates &#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-public-and-private-certificates.md) to the Contoso and Fabrikam computers.</span></span> <span data-ttu-id="9c7d9-104">各コンピュータは独自のプライベート証明書と他の組織のパブリック証明書をインポートします。</span><span class="sxs-lookup"><span data-stu-id="9c7d9-104">Each computer imports its own private certificates and imports the public certificates of the other organization.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9c7d9-105">Fabrikam のプライベート証明書と Contoso のパブリック証明書を Fabrikam のコンピューターに転送して、インポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c7d9-105">You have to transfer the Fabrikam private certificates and Contoso public certificates to the Fabrikam computer to import them.</span></span> <span data-ttu-id="9c7d9-106">ここでは、Fabrikam のコンピューターの C:\Certs フォルダーにこれらの証明書をコピーします。</span><span class="sxs-lookup"><span data-stu-id="9c7d9-106">This step assumes that you put these certificates in the C:\Certs folder on the Fabrikam computer.</span></span>  
  
### <a name="to-import-the-contoso-private-certificates-on-the-contoso-computer"></a><span data-ttu-id="9c7d9-107">Contoso のコンピューターで Contoso のプライベート証明書をインポートするには</span><span class="sxs-lookup"><span data-stu-id="9c7d9-107">To import the Contoso private certificates on the Contoso computer</span></span>  
  
1. <span data-ttu-id="9c7d9-108">Contoso コンピューターでは、次のようにクリックします。**開始**、 をクリック**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="9c7d9-108">On the Contoso computer, click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="9c7d9-109">コマンド プロンプトに移動します**\<**<em>ドライブ</em>**\>: \Program Files\Microsoft BizTalk\<バージョン\>のアクセラレータ。Rosettanet \sdk**押します**Enter**します。</span><span class="sxs-lookup"><span data-stu-id="9c7d9-109">At the command prompt, move to **\<**<em>drive</em>**\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK** and then press **Enter**.</span></span>  
  
3. <span data-ttu-id="9c7d9-110">コマンド プロンプトで「 **CertWizard/Privatekey"\<**<em>ドライブ</em>**\>: \Certs\Contoso Private Encryption.pfx"**、し、キーを押します。**入力**します。</span><span class="sxs-lookup"><span data-stu-id="9c7d9-110">At the command prompt, type **CertWizard /Privatekey "\<**<em>drive</em>**\>:\Certs\Contoso Private Encryption.pfx"**, and then press **Enter**.</span></span>  
  
4. <span data-ttu-id="9c7d9-111">**証明書ファイルのパスワードを入力してください**プロンプトで「 **mysecret**、キーを押しますと **」と入力**します。</span><span class="sxs-lookup"><span data-stu-id="9c7d9-111">At the **Please enter the password for the certificate file** prompt, type **mysecret**, and then press **Enter**.</span></span>  
  
5. <span data-ttu-id="9c7d9-112">**Identity < contoso_machine > \HostSvc のパスワードの入力**と表示されたら、HostSvc アカウント パスワードを入力し、キーを押して**Enter**します。</span><span class="sxs-lookup"><span data-stu-id="9c7d9-112">At the **Enter password for identity <contoso_machine>\HostSvc** prompt, type the HostSvc account password, and then press **Enter**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="9c7d9-113">BizTalkServerApplication を HostSvc 以外のアカウント名で実行している場合は、プロンプトが異なります。</span><span class="sxs-lookup"><span data-stu-id="9c7d9-113">If your BizTalkServerApplication runs under an account name other than HostSvc, the prompt must be different.</span></span>  
  
6. <span data-ttu-id="9c7d9-114">**このホーム証明書が使用される**プロンプトで「 **D**、キーを押しますと **」と入力**します。</span><span class="sxs-lookup"><span data-stu-id="9c7d9-114">At the **This home certificate will be used for** prompt, type **D**, and then press **Enter**.</span></span>  
  
    <span data-ttu-id="9c7d9-115">CertWizard は、BizTalkServerApplication ホストと BizTalkServerIsolatedHost ホストの実行に使用しているユーザー アカウントの \Personal\Certificates ストアに、証明書をインポートします。</span><span class="sxs-lookup"><span data-stu-id="9c7d9-115">The CertWizard imports the certificate into the \Personal\Certificates store for the user accounts that BizTalkServerApplication and BizTalkServerIsolatedHost hosts run under.</span></span>  
  
7. <span data-ttu-id="9c7d9-116">手順 3 ~ 6」と入力して、署名証明書である Contoso Private Signature.pfx 証明書の指定の**S**で、**このホーム証明書が使用される**手順 6 で書き留めたプロンプト。</span><span class="sxs-lookup"><span data-stu-id="9c7d9-116">Repeat steps 3-6 for the Contoso Private Signature.pfx certificate specifying that it is a signature certificate by typing **S** at the **This home certificate will be used for** prompt noted in step 6.</span></span>  
  
### <a name="to-import-the-fabrikam-public-certificates-on-the-contoso-computer"></a><span data-ttu-id="9c7d9-117">Contoso のコンピュータで Fabrikam のパブリック証明書をインポートするには</span><span class="sxs-lookup"><span data-stu-id="9c7d9-117">To import the Fabrikam public certificates on the Contoso computer</span></span>  
  
1.  <span data-ttu-id="9c7d9-118">Contoso コンピューターでは、次のようにクリックします。**開始**、 をクリック**実行、** 型**cmd**、順にクリックします**ok**します。</span><span class="sxs-lookup"><span data-stu-id="9c7d9-118">On the Contoso computer, click **Start**, click **Run,** type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="9c7d9-119">コマンド プロンプトに移動します*\<ドライブ\>* * *:\Program files \microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk** と押します **」と入力。**.</span><span class="sxs-lookup"><span data-stu-id="9c7d9-119">At the command prompt, move to *\<drive\>***:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK** and then press **Enter**.</span></span>  
  
3.  <span data-ttu-id="9c7d9-120">コマンド プロンプトで「 **CertWizard/Publickey"***\<ドライブ\>***: \Certs\Fabrikam Public Encryption.cer"**、し、キーを押します**Enter**.</span><span class="sxs-lookup"><span data-stu-id="9c7d9-120">At the command prompt, type **CertWizard /Publickey "***\<drive\>***:\Certs\Fabrikam Public Encryption.cer"**, and then press **Enter**.</span></span>  
  
4.  <span data-ttu-id="9c7d9-121">Fabrikam Public Signature.cer 証明書について、手順 3. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="9c7d9-121">Repeat step 3 for the Fabrikam Public Signature.cer certificate.</span></span>  
  
### <a name="to-import-the-fabrikam-private-certificates-on-the-fabrikam-computer"></a><span data-ttu-id="9c7d9-122">Fabrikam のコンピューターで Fabrikam のプライベート証明書をインポートするには</span><span class="sxs-lookup"><span data-stu-id="9c7d9-122">To import the Fabrikam private certificates on the Fabrikam computer</span></span>  
  
1.  <span data-ttu-id="9c7d9-123">Contoso のコンピューターから次のファイルをコピー、\<ドライブ\>: \Certs フォルダーに、Fabrikam のコンピューター: Contoso Public Encryption.cer、Contoso Public Signature.cer、Fabrikam Private Encryption.pfx、Fabrikam PrivateSignature.pfx します。</span><span class="sxs-lookup"><span data-stu-id="9c7d9-123">Copy the following files from the Contoso computer to the \<drive\>:\Certs folder on the Fabrikam computer: Contoso Public Encryption.cer, Contoso Public Signature.cer, Fabrikam Private Encryption.pfx, and Fabrikam Private Signature.pfx.</span></span>  
  
2.  <span data-ttu-id="9c7d9-124">Fabrikum コンピューターでは、次のようにクリックします。**開始**、 をクリック**実行**、型**cmd**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="9c7d9-124">On the Fabrikum computer, click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="9c7d9-125">コマンド プロンプトに移動します*\<ドライブ\>* * *:\Program files \microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk** と押します **」と入力。**.</span><span class="sxs-lookup"><span data-stu-id="9c7d9-125">At the command prompt, move to *\<drive\>***:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK** and then press **Enter**.</span></span>  
  
4.  <span data-ttu-id="9c7d9-126">コマンド プロンプトで「 **CertWizard/Privatekey"***\<ドライブ\>***: \Certs\Fabrikam Private Encryption.pfx"**、およびキーを押します**Enter**.</span><span class="sxs-lookup"><span data-stu-id="9c7d9-126">At the command prompt, type **CertWizard /Privatekey "***\<drive\>***:\Certs\Fabrikam Private Encryption.pfx"**, and then press **Enter**.</span></span>  
  
5.  <span data-ttu-id="9c7d9-127">**証明書ファイルのパスワードを入力してください**プロンプトで「 **mysecret**、キーを押しますと **」と入力**します。</span><span class="sxs-lookup"><span data-stu-id="9c7d9-127">At the **Please enter the password for the certificate file** prompt, type **mysecret**, and then press **Enter**.</span></span>  
  
6.  <span data-ttu-id="9c7d9-128">**Identity < fabrikam_machine > \HostSvc のパスワードの入力**と表示されたら、HostSvc アカウント パスワードを入力し、キーを押して**Enter**します。</span><span class="sxs-lookup"><span data-stu-id="9c7d9-128">At the **Enter password for identity <fabrikam_machine>\HostSvc** prompt, type the HostSvc account password, and then press **Enter**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9c7d9-129">BizTalkServerApplication を HostSvc 以外のアカウント名で実行している場合は、プロンプトが異なります。</span><span class="sxs-lookup"><span data-stu-id="9c7d9-129">If your BizTalkServerApplication runs under an account name other than HostSvc, the prompt must be different.</span></span>  
  
7.  <span data-ttu-id="9c7d9-130">**このホーム証明書が使用される**プロンプトで「 **D**、キーを押しますと **」と入力**します。</span><span class="sxs-lookup"><span data-stu-id="9c7d9-130">At the **This home certificate will be used for** prompt, type **D**, and then press **Enter**.</span></span>  
  
     <span data-ttu-id="9c7d9-131">CertWizard は、BizTalkServerApplication ホストと BizTalkServerIsolatedHost ホストの実行に使用しているユーザー アカウントの \Personal\Certificates ストアに、証明書をインポートします。</span><span class="sxs-lookup"><span data-stu-id="9c7d9-131">The CertWizard imports the certificate into the \Personal\Certificates store for the user accounts that BizTalkServerApplication and BizTalkServerIsolatedHost hosts run under.</span></span>  
  
8.  <span data-ttu-id="9c7d9-132">手順 4 ~ 7」と入力して、署名証明書である Fabrikam Private Signature.pfx 証明書の指定を**S**で、**このホーム証明書が使用される**手順 6 でダイアログを表示します。</span><span class="sxs-lookup"><span data-stu-id="9c7d9-132">Repeat steps 4-7 for the Fabrikam Private Signature.pfx certificate specifying that it is a signature certificate by typing **S** at the **This home certificate will be used for** prompt in step 6.</span></span>  
  
### <a name="to-import-the-contoso-public-certificates-on-the-fabrikam-computer"></a><span data-ttu-id="9c7d9-133">Fabrikam のコンピューターで Contoso のパブリック証明書をインポートするには</span><span class="sxs-lookup"><span data-stu-id="9c7d9-133">To import the Contoso public certificates on the Fabrikam computer</span></span>  
  
1.  <span data-ttu-id="9c7d9-134">Fabrikum コンピューターでは、次のようにクリックします。**開始**、 をクリック**実行**、型**cmd**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="9c7d9-134">On the Fabrikum computer, click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="9c7d9-135">コマンド プロンプトに移動します*\<ドライブ\>* * *:\Program files \microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk** と押します **」と入力。**.</span><span class="sxs-lookup"><span data-stu-id="9c7d9-135">At the command prompt, move to *\<drive\>***:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK** and then press **Enter**.</span></span>  
  
3.  <span data-ttu-id="9c7d9-136">コマンド プロンプトで「 **CertWizard/Publickey"***\<ドライブ\>***: \Certs\Contoso Public Encryption.cer"**、押します **」と入力**します。</span><span class="sxs-lookup"><span data-stu-id="9c7d9-136">At the command prompt, type **CertWizard /Publickey "***\<drive\>***:\Certs\Contoso Public Encryption.cer"**, and then press **Enter**.</span></span>  
  
4.  <span data-ttu-id="9c7d9-137">Contoso Public Signature.cer 証明書について、手順 3. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="9c7d9-137">Repeat step 3 for the Contoso Public Signature.cer certificate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c7d9-138">参照</span><span class="sxs-lookup"><span data-stu-id="9c7d9-138">See Also</span></span>  
 [<span data-ttu-id="9c7d9-139">手順 4: IIS で Secure Sockets Layer の有効化</span><span class="sxs-lookup"><span data-stu-id="9c7d9-139">Step 4: Enabling Secure Sockets Layer in IIS</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-4-enabling-secure-sockets-layer-in-iis.md)