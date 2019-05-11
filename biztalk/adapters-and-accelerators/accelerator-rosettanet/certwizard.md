---
title: CertWizard |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates, CertWizard utility
- CertWizard utility
- certificates, importing
ms.assetid: beeab3c0-d7b1-4bb9-8b19-f79b049d5aa1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b028deda4ef180a4983e1c58fa7a9487804a0232
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65284779"
---
# <a name="certwizard"></a><span data-ttu-id="bbf98-102">CertWizard</span><span class="sxs-lookup"><span data-stu-id="bbf98-102">CertWizard</span></span>
<span data-ttu-id="bbf98-103">CertWizard ユーティリティを使用して Microsoft® で使用するためのプライベートまたはパブリック ストアに .pfx または .cer ファイルから証明書をインポートする[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="bbf98-103">You use the CertWizard utility to import a certificate from a .pfx or .cer file into a private or public store for use with Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].</span></span>  
  
## <a name="location-in-sdk"></a><span data-ttu-id="bbf98-104">SDK でのパス</span><span class="sxs-lookup"><span data-stu-id="bbf98-104">Location in SDK</span></span>  
 <span data-ttu-id="bbf98-105">\<*drive*\>\Program Files (x86)\\Microsoft  BizTalk \<version\> Accelerator for RosettaNet\SDK\\</span><span class="sxs-lookup"><span data-stu-id="bbf98-105">\<*drive*\>\Program Files (x86)\\Microsoft  BizTalk \<version\> Accelerator for RosettaNet\SDK\\</span></span>  
  
## <a name="running-certwizard"></a><span data-ttu-id="bbf98-106">CertWizard の実行</span><span class="sxs-lookup"><span data-stu-id="bbf98-106">Running CertWizard</span></span>  
  
#### <a name="to-run-certwizard"></a><span data-ttu-id="bbf98-107">CertWizard を実行するには</span><span class="sxs-lookup"><span data-stu-id="bbf98-107">To run CertWizard</span></span>  
  
1. <span data-ttu-id="bbf98-108">コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="bbf98-108">Open a command prompt.</span></span>  
  
2. <span data-ttu-id="bbf98-109">移動\<*ドライブ*\>\ Program Files (x86)\\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\\します。</span><span class="sxs-lookup"><span data-stu-id="bbf98-109">Move to \<*drive*\>\ Program Files (x86)\\Microsoft  BizTalk \<version\> Accelerator for RosettaNet\SDK\\.</span></span>  
  
3. <span data-ttu-id="bbf98-110">コマンド プロンプトで「 **CertWizard**と、必須および適切なスイッチを入力し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="bbf98-110">At the command prompt, type **CertWizard**, type the required and appropriate switches, and then press ENTER.</span></span>  
  
## <a name="syntax-for-certwizard"></a><span data-ttu-id="bbf98-111">CertWizard の構文</span><span class="sxs-lookup"><span data-stu-id="bbf98-111">Syntax for CertWizard</span></span>  
 <span data-ttu-id="bbf98-112">次に、このコマンドライン ユーティリティを起動するために使用する構文を示します。</span><span class="sxs-lookup"><span data-stu-id="bbf98-112">The following shows the syntax that you use to start this command-line utility:</span></span>  
  
### <a name="syntax-for-importing-a-private-key"></a><span data-ttu-id="bbf98-113">秘密キーをインポートするための構文</span><span class="sxs-lookup"><span data-stu-id="bbf98-113">Syntax for Importing a Private Key</span></span>  
  
```  
CertWizard /Privatekey <filename>.pfx [/Filepassword <filepassword>] [/Useridentity <useridentity>] [/Password <password>] [/Thumbprint <thumbprint>] [/Usage sign|decrypt|both|none] [/Exportable true|false]  
```  
  
### <a name="syntax-for-importing-a-public-key"></a><span data-ttu-id="bbf98-114">公開キーをインポートするための構文</span><span class="sxs-lookup"><span data-stu-id="bbf98-114">Syntax for Importing a Public Key</span></span>  
  
```  
CertWizard /Publickey <filename>.cer [/Thumbprint <thumbprint>]  
```  
  
### <a name="syntax-for-importing-a-root-key"></a><span data-ttu-id="bbf98-115">ルート キーをインポートするための構文</span><span class="sxs-lookup"><span data-stu-id="bbf98-115">Syntax for Importing a Root Key</span></span>  
  
```  
CertWizard /Rootkey <filename>.cer [/Thumbprint <thumbprint>]  
```  
  
### <a name="syntax-description"></a><span data-ttu-id="bbf98-116">構文の説明</span><span class="sxs-lookup"><span data-stu-id="bbf98-116">Syntax Description</span></span>  
 <span data-ttu-id="bbf98-117">次の表では、CertWizard ユーティリティを使用する構文の各部について説明します。</span><span class="sxs-lookup"><span data-stu-id="bbf98-117">The following table describes each part of the syntax that the CertWizard utility uses.</span></span>  
  
|<span data-ttu-id="bbf98-118">**構文**</span><span class="sxs-lookup"><span data-stu-id="bbf98-118">**Syntax**</span></span>|<span data-ttu-id="bbf98-119">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="bbf98-119">**Description**</span></span>|  
|----------------|---------------------|  
|<span data-ttu-id="bbf98-120">**プライベート キー**</span><span class="sxs-lookup"><span data-stu-id="bbf98-120">**Privatekey**</span></span>|<span data-ttu-id="bbf98-121">秘密キーをインポートするために使用します。</span><span class="sxs-lookup"><span data-stu-id="bbf98-121">Used to import a private key.</span></span>|  
|<span data-ttu-id="bbf98-122">**公開鍵**</span><span class="sxs-lookup"><span data-stu-id="bbf98-122">**Publickey**</span></span>|<span data-ttu-id="bbf98-123">公開キーをインポートするために使用します。</span><span class="sxs-lookup"><span data-stu-id="bbf98-123">Used to import a public key.</span></span>|  
|<span data-ttu-id="bbf98-124">**Rootkey**</span><span class="sxs-lookup"><span data-stu-id="bbf98-124">**Rootkey**</span></span>|<span data-ttu-id="bbf98-125">ルート キーのインポートに使用される、証明機関から。</span><span class="sxs-lookup"><span data-stu-id="bbf98-125">Used to import a root key—from a certification authority.</span></span>|  
|<span data-ttu-id="bbf98-126">**filename.pfx (または .cer)**</span><span class="sxs-lookup"><span data-stu-id="bbf98-126">**filename.pfx (or .cer)**</span></span>|<span data-ttu-id="bbf98-127">.Pfx (秘密キー) または .cer (公開キー) ファイルの完全パス。</span><span class="sxs-lookup"><span data-stu-id="bbf98-127">Full path for the .pfx (private keys) or .cer (public keys) file.</span></span>|  
|<span data-ttu-id="bbf98-128">**Filepassword**</span><span class="sxs-lookup"><span data-stu-id="bbf98-128">**Filepassword**</span></span>|<span data-ttu-id="bbf98-129">.Pfx ファイルのロック解除に必要なパスワード。</span><span class="sxs-lookup"><span data-stu-id="bbf98-129">The password required to unlock the .pfx file.</span></span>|  
|<span data-ttu-id="bbf98-130">**割り当てられていません**</span><span class="sxs-lookup"><span data-stu-id="bbf98-130">**Useridentity**</span></span>|<span data-ttu-id="bbf98-131">1 つまたは複数の BizTalk ホストを使用するサービス id を指定します。</span><span class="sxs-lookup"><span data-stu-id="bbf98-131">A service identity that one or more BizTalk Hosts uses.</span></span> <span data-ttu-id="bbf98-132">ホストを指定したくないが、ユーザー アカウントで証明書をインポートする場合は、ユーザー アカウントを入力します。</span><span class="sxs-lookup"><span data-stu-id="bbf98-132">Enter a user account if you do not want to specify the host, but want to import a certificate under a user account.</span></span> <span data-ttu-id="bbf98-133">**注:** 追加しない場合、 **Useridentity**切り替えるには、このユーティリティをインポートし、すべてのユーザーの証明書を設定します。</span><span class="sxs-lookup"><span data-stu-id="bbf98-133">**Note:**  If you do not add the **Useridentity** switch, the utility imports and set the certificate for all users.</span></span> <span data-ttu-id="bbf98-134">**注:** 追加する場合、 **Useridentity**切り替えるが、値を入力しない WMI は、ユーザー id を自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="bbf98-134">**Note:**  If you add the **Useridentity** switch, but do not enter a value, WMI automatically generates the user identity.</span></span>|  
|<span data-ttu-id="bbf98-135">**Password**</span><span class="sxs-lookup"><span data-stu-id="bbf98-135">**Password**</span></span>|<span data-ttu-id="bbf98-136">サービス id ユーザーのパスワード。</span><span class="sxs-lookup"><span data-stu-id="bbf98-136">The password for the service identity user.</span></span>|  
|<span data-ttu-id="bbf98-137">**拇印**</span><span class="sxs-lookup"><span data-stu-id="bbf98-137">**Thumbprint**</span></span>|<span data-ttu-id="bbf98-138">ファイルの場合も、特定の証明書の拇印には、1 つ以上の証明書が含まれています。</span><span class="sxs-lookup"><span data-stu-id="bbf98-138">The thumbprint of a specific certificate, in case the file contains more than one certificate.</span></span> <span data-ttu-id="bbf98-139">**注:** 公開証明書ファイルの場合、ファイルには、1 つ以上の証明書が含まれていて、拇印を指定しない場合、ユーティリティは、ファイル内のすべての証明書をインポートします。</span><span class="sxs-lookup"><span data-stu-id="bbf98-139">**Note:**  For a public certificate file, if the file contains more than one certificate and you do not specify the thumbprint, the utility imports all certificates in the file.</span></span> <span data-ttu-id="bbf98-140">プライベート証明書ファイルの場合、ユーティリティにインポートする証明書を選択するように求められます。</span><span class="sxs-lookup"><span data-stu-id="bbf98-140">For a private certificate file, the utility prompts you to select the certificate to import.</span></span>|  
|<span data-ttu-id="bbf98-141">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="bbf98-141">**Usage**</span></span>|<span data-ttu-id="bbf98-142">インポートしたプライベート証明書の用途。</span><span class="sxs-lookup"><span data-stu-id="bbf98-142">The intended usage of the imported private certificate.</span></span> <span data-ttu-id="bbf98-143">Sign (署名証明書の場合)、decrypt (暗号化解除証明書)、両方 (証明書の署名証明書と暗号化解除証明書の両方である)、または none (も証明書は署名証明書と暗号化解除証明書の両方を指定できます。).</span><span class="sxs-lookup"><span data-stu-id="bbf98-143">Can be sign (for a signing certificate), decrypt (for a decryption certificate), both (for a certificate that is both a signing certificate and a decryption certificate), or none (also for a certificate that is both a signing certificate and a decryption certificate).</span></span> <span data-ttu-id="bbf98-144">**注:** 設定した場合、 **/Usage**スイッチを none に、ウィザードでは、BizTalk ホストと BizTalk グループに証明書の拇印は設定しません。</span><span class="sxs-lookup"><span data-stu-id="bbf98-144">**Note:**  If you set the **/Usage** switch to none, the wizard will not set the thumbprint for the certificate on the BizTalk Hosts or the BizTalk Group.</span></span>|  
|<span data-ttu-id="bbf98-145">**エクスポート可能**</span><span class="sxs-lookup"><span data-stu-id="bbf98-145">**Exportable**</span></span>|<span data-ttu-id="bbf98-146">`True`または`False`します。</span><span class="sxs-lookup"><span data-stu-id="bbf98-146">Can be `True` or `False`.</span></span> <span data-ttu-id="bbf98-147">場合`True`、秘密キーを再エクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="bbf98-147">If `True`, the private key can be re-exported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bbf98-148">コメント</span><span class="sxs-lookup"><span data-stu-id="bbf98-148">Remarks</span></span>  
 <span data-ttu-id="bbf98-149">CertWizard は、個人用ストアに秘密キーを .pfx ファイルからインポートし、.cer ファイルから公開キーをパブリック ストアにインポートします。</span><span class="sxs-lookup"><span data-stu-id="bbf98-149">CertWizard imports a private key from a .pfx file into the personal store, and imports a public key from a .cer file into a public store.</span></span> <span data-ttu-id="bbf98-150">秘密キーをインポートするときに、証明書は受信メッセージの復号化証明書または送信メッセージの署名証明書を指定できます。</span><span class="sxs-lookup"><span data-stu-id="bbf98-150">When importing a private key, the certificate can be a decryption certificate for incoming messages or a signing certificate for outgoing messages.</span></span>  
  
 <span data-ttu-id="bbf98-151">CertWizard は、コマンド プロンプトで完全なコマンドを指定しないと、必要な値を指定することが求められます。</span><span class="sxs-lookup"><span data-stu-id="bbf98-151">If you do not give the full command at the command prompt, CertWizard will prompt you to provide the required values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbf98-152">参照</span><span class="sxs-lookup"><span data-stu-id="bbf98-152">See Also</span></span>  
 <span data-ttu-id="bbf98-153">[ユーティリティ](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md) </span><span class="sxs-lookup"><span data-stu-id="bbf98-153">[Utilities](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md) </span></span>  
 [<span data-ttu-id="bbf98-154">CertWizard ユーティリティを使用した証明書のインポート</span><span class="sxs-lookup"><span data-stu-id="bbf98-154">Importing Certificates Using the CertWizard Utility</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-the-certwizard-utility.md)
