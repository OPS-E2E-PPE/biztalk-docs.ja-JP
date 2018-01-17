---
title: "CertWizard ユーティリティを使用して証明書のインポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64be28927a49a1fc751870785ff3fc3f55a36cb1
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="importing-certificates-using-the-certwizard-utility"></a><span data-ttu-id="4f072-102">CertWizard ユーティリティを使用して証明書のインポート</span><span class="sxs-lookup"><span data-stu-id="4f072-102">Importing Certificates Using the CertWizard Utility</span></span>
<span data-ttu-id="4f072-103">このトピックで使用できる詳細な手順のコマンド ライン ユーティリティである CertWizard ユーティリティを使用して証明書をインポートする方法について説明、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK。</span><span class="sxs-lookup"><span data-stu-id="4f072-103">This topic describes how to import a certificate by using CertWizard utility, a step-by-step command-line utility available in the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK.</span></span> <span data-ttu-id="4f072-104">ここでは、秘密キー、公開キー、またはルート キーのインポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="4f072-104">This topic discusses importing a private, public, or root key.</span></span> <span data-ttu-id="4f072-105">証明書の構成に使用するスイッチについても説明します。</span><span class="sxs-lookup"><span data-stu-id="4f072-105">It describes the switches that you use to configure the certificate.</span></span>  
  
 <span data-ttu-id="4f072-106">CertWizard ユーティリティを使用することにより、[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] 管理コンソール (MMC) を使用して手動で行う必要がある多くの手順を自動化できます。</span><span class="sxs-lookup"><span data-stu-id="4f072-106">The CertWizard utility automates many of the steps that you would have to do manually by using the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Management Console (MMC).</span></span> <span data-ttu-id="4f072-107">CertWizard ユーティリティを実行、 **runas**ホスト サービス アカウントとして MMC を開くコマンド。</span><span class="sxs-lookup"><span data-stu-id="4f072-107">The CertWizard utility performs the **runas** command to open MMC as the host service account.</span></span> <span data-ttu-id="4f072-108">追加しない場合、 **Useridentity**スイッチが検出され、パスワードの入力を求める、ホスト サービス アカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="4f072-108">If you do not add a **Useridentity** switch, it will detect and use the host service account, prompting you for a password.</span></span> <span data-ttu-id="4f072-109">証明書が格納および構成されます。</span><span class="sxs-lookup"><span data-stu-id="4f072-109">It stores and configures the certificate.</span></span>  
  
 <span data-ttu-id="4f072-110">複数の CertWizard ユーティリティ コマンドでバッチ ファイルを作成することにより、複数の証明書を同時にインポートできます。</span><span class="sxs-lookup"><span data-stu-id="4f072-110">You can import multiple certificates at the same time by creating a batch file with multiple CertWizard utility commands.</span></span>  
  
### <a name="to-import-a-private-key"></a><span data-ttu-id="4f072-111">秘密キーをインポートするには</span><span class="sxs-lookup"><span data-stu-id="4f072-111">To import a private key</span></span>  
  
1.  <span data-ttu-id="4f072-112">をクリックして **開始**, 、 をクリックして **実行**, 、型 **cmd**, 、 をクリックし、 **ok**します。</span><span class="sxs-lookup"><span data-stu-id="4f072-112">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="4f072-113">コマンド プロンプトでに移動、 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] MS-DOS を使用して SDK フォルダー **CD**コマンド、たとえば、入力**cd C:\Program files \microsoft BizTalk\<バージョン\>Accelerator forRosettanet \sdk**です。</span><span class="sxs-lookup"><span data-stu-id="4f072-113">At the command prompt, move to the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK folder using the MS-DOS **CD** command, for example, type **cd C:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK** .</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4f072-114">CertWizard ユーティリティを使用してヘルプを参照するには、次のように入力します**CertWizard/しますか?。**</span><span class="sxs-lookup"><span data-stu-id="4f072-114">For help with the CertWizard utility, type **CertWizard /?**</span></span> <span data-ttu-id="4f072-115">コマンド プロンプトで。</span><span class="sxs-lookup"><span data-stu-id="4f072-115">at the command prompt.</span></span>  
  
3.  <span data-ttu-id="4f072-116">コマンド プロンプトで次のように入力します。 **CertWizard/Privatekey \<filename\>.pfx**ここで、 \< *filename*\>.pfx プライベート証明書が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4f072-116">At the command prompt, type **CertWizard /Privatekey \<filename\>.pfx**, where \<*filename*\>.pfx contains the private certificate.</span></span> <span data-ttu-id="4f072-117">ファイルのパスワードを指定するには追加**「/filepassword」 \<filepassword\>** コマンド。</span><span class="sxs-lookup"><span data-stu-id="4f072-117">To provide the password for the file, append **/Filepassword \<filepassword\>** to the command.</span></span>  
  
4.  <span data-ttu-id="4f072-118">BizTalk ホストによって使用される特定のアカウントに、証明書をインポートする、追加したい場合**「/useridentity」 \<useridentity\> /Password\<パスワード\>**コマンド。</span><span class="sxs-lookup"><span data-stu-id="4f072-118">If you want to import the certificate into a specific account used by the BizTalk Host, append **/Useridentity \<useridentity\> /Password \<password\>** to the command.</span></span>  
  
5.  <span data-ttu-id="4f072-119">.Pfx ファイルには、複数の証明書が含まれている場合に、特定の拇印を指定する、追加したい場合**「/thumbprint」\<拇印\>**コマンド。</span><span class="sxs-lookup"><span data-stu-id="4f072-119">If you want to designate a specific thumbprint in case the .pfx file contains more than one certificate, append **/Thumbprint \<thumbprint\>** to the command.</span></span>  
  
6.  <span data-ttu-id="4f072-120">証明書の使用法を構成する場合は、追加**/Usage**コマンドと入力し、次の値のいずれかを追加します。</span><span class="sxs-lookup"><span data-stu-id="4f072-120">If you want to configure the usage of the certificate, append **/Usage** to the command, and then append one of the following values:</span></span>  
  
    -   <span data-ttu-id="4f072-121">追加**記号**BizTalk グループの署名証明書として証明書の拇印を追加します。</span><span class="sxs-lookup"><span data-stu-id="4f072-121">Append **sign** to add the certificate's thumbprint as the signing certificate for the BizTalk Group.</span></span> <span data-ttu-id="4f072-122">BizTalk 管理コンソールで Microsoft BizTalk server (ローカル) ダイアログ ボックスのセットとして。</span><span class="sxs-lookup"><span data-stu-id="4f072-122">as set on the dialog box for Microsoft BizTalk Server (Local) in the BizTalk Administration Console.</span></span>  
  
    -   <span data-ttu-id="4f072-123">追加**復号化**プロパティ ページの [証明書] タブで、BizTalk 管理コンソール内の各ホストのセットとして、BizTalk ホストの暗号化解除証明書として証明書の拇印を追加します。</span><span class="sxs-lookup"><span data-stu-id="4f072-123">Append **decrypt** to add the certificate's thumbprint as the decryption certificate for the BizTalk Hosts, as set on the certificate tab of the property pages for each host in the BizTalk Administration Console.</span></span>  
  
    -   <span data-ttu-id="4f072-124">追加**両方**証明書を追加の拇印を両方の BizTalk グループの署名証明書と、BizTalk ホストの暗号化解除証明書。</span><span class="sxs-lookup"><span data-stu-id="4f072-124">Append **both** to add the certificate's thumbprint for both the BizTalk Group's signing certificate and the BizTalk Host's decryption certificate.</span></span>  
  
    -   <span data-ttu-id="4f072-125">追加**なし**ときたくない、BizTalk グループまたは BizTalk ホストの構成を設定します。</span><span class="sxs-lookup"><span data-stu-id="4f072-125">Append **none** when you do not want to set the configuration for the BizTalk Group or the BizTalk Hosts.</span></span>  
  
7.  <span data-ttu-id="4f072-126">証明書をエクスポート可能として構成する場合は、追加**/exportable true**です。</span><span class="sxs-lookup"><span data-stu-id="4f072-126">If you want to configure the certificate as exportable, append **/Exportable true**.</span></span> <span data-ttu-id="4f072-127">証明書をエクスポート不可能として設定する追加**/exportable false**既定の動作です。</span><span class="sxs-lookup"><span data-stu-id="4f072-127">To set the certificate as non-exportable, append **/Exportable false**, which is the default behavior.</span></span>  
  
8.  <span data-ttu-id="4f072-128">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="4f072-128">Press **Enter**.</span></span>  
  
9. <span data-ttu-id="4f072-129">必要なパスワードをいずれか 1 つコマンドに入力しないと、ツールが入力を求めます。</span><span class="sxs-lookup"><span data-stu-id="4f072-129">If you did not type one of the passwords required in the command, the tool prompts you for it.</span></span> <span data-ttu-id="4f072-130">パスワードを入力し、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="4f072-130">Type the password, and then press **Enter**.</span></span>  
  
10. <span data-ttu-id="4f072-131">ファイルに複数の証明書が含まれる場合は、コマンドに拇印を入力しないと、利用可能な拇印がツールに表示され、いずれか 1 つを選択するように求められます。</span><span class="sxs-lookup"><span data-stu-id="4f072-131">If the file contains multiple certificates, but you did not type a thumbprint in the command, the tool displays the available thumbprints, and prompts you to select one.</span></span> <span data-ttu-id="4f072-132">クリックし、キーを押しな拇印の番号を入力**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="4f072-132">Type the number of the thumbprint that you want, and then press **Enter**.</span></span>  
  
     <span data-ttu-id="4f072-133">このツールで指定されたユーザーに対して、\Personal\Certificates ストアに証明書がインポート、 **「/useridentity」**スイッチ。</span><span class="sxs-lookup"><span data-stu-id="4f072-133">The tool imports the certificate into the \Personal\Certificates store for the user specified in the **/useridentity** switch.</span></span> <span data-ttu-id="4f072-134">ユーザーを指定しない場合は、BizTalkServerApplication と BizTalkServerIsolatedHost ホストのユーザー ID が既定のユーザーになります。</span><span class="sxs-lookup"><span data-stu-id="4f072-134">If you do not specify a user, the default user is the user identity for the BizTalkServerApplication and BizTalkServerIsolatedHost hosts.</span></span>  
  
### <a name="to-import-a-public-key"></a><span data-ttu-id="4f072-135">公開キーをインポートするには</span><span class="sxs-lookup"><span data-stu-id="4f072-135">To import a public key</span></span>  
  
1.  <span data-ttu-id="4f072-136">をクリックして **開始**, 、 をクリックして **実行**, 、型 **cmd**, 、 をクリックし、 **ok**します。</span><span class="sxs-lookup"><span data-stu-id="4f072-136">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="4f072-137">コマンド プロンプトでに移動、 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] MS-DOS を使用して、SDK フォルダー **CD**コマンド、たとえば、入力**cd C:\Program files \microsoft BizTalk\<バージョン\>Accelerator forRosettanet \sdk**です。</span><span class="sxs-lookup"><span data-stu-id="4f072-137">At the command prompt, move to the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK folder by using the MS-DOS **CD** command, for example, type **cd C:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK**.</span></span>  
  
3.  <span data-ttu-id="4f072-138">コマンド プロンプトで次のように入力します。 **CertWizard/Publickey \<filename\>.cer**ここで、 \< *filename*\>.cer に公開証明書が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4f072-138">At the command prompt, type **CertWizard /Publickey \<filename\>.cer**, where \<*filename*\>.cer contains the public certificate.</span></span>  
  
4.  <span data-ttu-id="4f072-139">.Cer または .der ファイル内の証明書の拇印を指定する場合は、追加**「/thumbprint」\<拇印\>**コマンド。</span><span class="sxs-lookup"><span data-stu-id="4f072-139">If you want to designate a thumbprint for the certificate in the .cer or .der file, append **/Thumbprint \<thumbprint\>** to the command.</span></span>  
  
     <span data-ttu-id="4f072-140">[証明書 (ローカル コンピューター)] \Other People\Certificates ストアに証明書がインポートされ、構成が設定されます。</span><span class="sxs-lookup"><span data-stu-id="4f072-140">The tool imports the certificate into the Certificates (Local Computer)\Other People\Certificates store, and sets its configuration.</span></span>  
  
### <a name="to-import-a-root-key"></a><span data-ttu-id="4f072-141">ルート キーをインポートするには</span><span class="sxs-lookup"><span data-stu-id="4f072-141">To import a root key</span></span>  
  
1.  <span data-ttu-id="4f072-142">をクリックして **開始**, 、 をクリックして **実行**, 、型 **cmd**, 、 をクリックし、 **ok**します。</span><span class="sxs-lookup"><span data-stu-id="4f072-142">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="4f072-143">コマンド プロンプトでに移動、 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] MS-DOS を使用して、SDK フォルダー **CD**コマンド、たとえば、入力**cd C:\Program files \microsoft BizTalk\<バージョン\>Accelerator forRosettanet \sdk**です。</span><span class="sxs-lookup"><span data-stu-id="4f072-143">At the command prompt, move to the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK folder by using the MS-DOS **CD** command, for example, type **cd C:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK**.</span></span>  
  
3.  <span data-ttu-id="4f072-144">コマンド プロンプトで次のように入力します。 **CertWizard/Rootkey \<filename\>.cer**ここで、 \< *filename*\>.cer にルート証明書が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4f072-144">At the command prompt, type **CertWizard /Rootkey \<filename\>.cer**, where \<*filename*\>.cer contains the root certificate.</span></span>  
  
4.  <span data-ttu-id="4f072-145">.Cer または .der ファイル内の証明書の拇印を指定する場合は、追加**「/thumbprint」\<拇印\>**コマンド。</span><span class="sxs-lookup"><span data-stu-id="4f072-145">If you want to designate a thumbprint for the certificate in the .cer or .der file, append **/Thumbprint \<thumbprint\>** to the command.</span></span>  
  
     <span data-ttu-id="4f072-146">[証明書 (ローカル コンピューター)] \Trusted Root Certification Authority\Certificates ストアに証明書がインポートされ、構成が設定されます。</span><span class="sxs-lookup"><span data-stu-id="4f072-146">The tool imports the certificate into the Certificates (Local Computer)\Trusted Root Certification Authority\Certificates store, and sets its configuration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f072-147">参照</span><span class="sxs-lookup"><span data-stu-id="4f072-147">See Also</span></span>  
 <span data-ttu-id="4f072-148">[CertWizard](../../adapters-and-accelerators/accelerator-rosettanet/certwizard.md) </span><span class="sxs-lookup"><span data-stu-id="4f072-148">[CertWizard](../../adapters-and-accelerators/accelerator-rosettanet/certwizard.md) </span></span>  
 [<span data-ttu-id="4f072-149">証明書の管理</span><span class="sxs-lookup"><span data-stu-id="4f072-149">Managing Certificates</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/managing-certificates1.md)