---
title: "CertWizard |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- certificates, CertWizard utility
- CertWizard utility
- certificates, importing
ms.assetid: beeab3c0-d7b1-4bb9-8b19-f79b049d5aa1
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea106299a734f79506823ca4a6951a3dad367553
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="certwizard"></a><span data-ttu-id="3d521-102">CertWizard</span><span class="sxs-lookup"><span data-stu-id="3d521-102">CertWizard</span></span>
<span data-ttu-id="3d521-103">.pfx ファイルまたは .cer ファイルの証明書をプライベート ストアまたはパブリック ストアにインポートして [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] で使用できるようにするには、CertWizard ユーティリティを使用します。</span><span class="sxs-lookup"><span data-stu-id="3d521-103">You use the CertWizard utility to import a certificate from a .pfx or .cer file into a private or public store for use with [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].</span></span>  
  
## <a name="location-in-sdk"></a><span data-ttu-id="3d521-104">SDK でのパス</span><span class="sxs-lookup"><span data-stu-id="3d521-104">Location in SDK</span></span>  
 <span data-ttu-id="3d521-105">\<*ドライブ*\>\Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<バージョン\>Accelerator for rosettanet \sdk\\</span><span class="sxs-lookup"><span data-stu-id="3d521-105">\<*drive*\>\Program Files\\[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<version\> Accelerator for RosettaNet\SDK\\</span></span>  
  
## <a name="running-certwizard"></a><span data-ttu-id="3d521-106">CertWizard の実行</span><span class="sxs-lookup"><span data-stu-id="3d521-106">Running CertWizard</span></span>  
  
#### <a name="to-run-certwizard"></a><span data-ttu-id="3d521-107">CertWizard を実行するには</span><span class="sxs-lookup"><span data-stu-id="3d521-107">To run CertWizard</span></span>  
  
1.  <span data-ttu-id="3d521-108">コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="3d521-108">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="3d521-109">移動\<*ドライブ*\>\ Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<バージョン\>Accelerator for rosettanet \sdk\\です。</span><span class="sxs-lookup"><span data-stu-id="3d521-109">Move to \<*drive*\>\ Program Files\\[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<version\> Accelerator for RosettaNet\SDK\\.</span></span>  
  
3.  <span data-ttu-id="3d521-110">コマンド プロンプトで次のように入力します。 **CertWizard**、必須と適切なスイッチを入力して、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="3d521-110">At the command prompt, type **CertWizard**, type the required and appropriate switches, and then press ENTER.</span></span>  
  
## <a name="syntax-for-certwizard"></a><span data-ttu-id="3d521-111">CertWizard の構文</span><span class="sxs-lookup"><span data-stu-id="3d521-111">Syntax for CertWizard</span></span>  
 <span data-ttu-id="3d521-112">次に、このコマンドライン ユーティリティを起動するために使用する構文を示します。</span><span class="sxs-lookup"><span data-stu-id="3d521-112">The following shows the syntax that you use to start this command-line utility:</span></span>  
  
### <a name="syntax-for-importing-a-private-key"></a><span data-ttu-id="3d521-113">秘密キーをインポートするための構文</span><span class="sxs-lookup"><span data-stu-id="3d521-113">Syntax for Importing a Private Key</span></span>  
  
```  
CertWizard /Privatekey <filename>.pfx [/Filepassword <filepassword>] [/Useridentity <useridentity>] [/Password <password>] [/Thumbprint <thumbprint>] [/Usage sign|decrypt|both|none] [/Exportable true|false]  
```  
  
### <a name="syntax-for-importing-a-public-key"></a><span data-ttu-id="3d521-114">公開キーをインポートするための構文</span><span class="sxs-lookup"><span data-stu-id="3d521-114">Syntax for Importing a Public Key</span></span>  
  
```  
CertWizard /Publickey <filename>.cer [/Thumbprint <thumbprint>]  
```  
  
### <a name="syntax-for-importing-a-root-key"></a><span data-ttu-id="3d521-115">ルート キーをインポートするための構文</span><span class="sxs-lookup"><span data-stu-id="3d521-115">Syntax for Importing a Root Key</span></span>  
  
```  
CertWizard /Rootkey <filename>.cer [/Thumbprint <thumbprint>]  
```  
  
### <a name="syntax-description"></a><span data-ttu-id="3d521-116">構文の説明</span><span class="sxs-lookup"><span data-stu-id="3d521-116">Syntax Description</span></span>  
 <span data-ttu-id="3d521-117">次の表に、CertWizard ユーティリティが使用する構文の各要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="3d521-117">The following table describes each part of the syntax that the CertWizard utility uses.</span></span>  
  
|<span data-ttu-id="3d521-118">**構文**</span><span class="sxs-lookup"><span data-stu-id="3d521-118">**Syntax**</span></span>|<span data-ttu-id="3d521-119">**Description**</span><span class="sxs-lookup"><span data-stu-id="3d521-119">**Description**</span></span>|  
|----------------|---------------------|  
|<span data-ttu-id="3d521-120">**プライベート キー**</span><span class="sxs-lookup"><span data-stu-id="3d521-120">**Privatekey**</span></span>|<span data-ttu-id="3d521-121">秘密キーをインポートするために使用します。</span><span class="sxs-lookup"><span data-stu-id="3d521-121">Used to import a private key.</span></span>|  
|<span data-ttu-id="3d521-122">**公開キー**</span><span class="sxs-lookup"><span data-stu-id="3d521-122">**Publickey**</span></span>|<span data-ttu-id="3d521-123">公開キーをインポートするために使用します。</span><span class="sxs-lookup"><span data-stu-id="3d521-123">Used to import a public key.</span></span>|  
|<span data-ttu-id="3d521-124">**ルートキー**</span><span class="sxs-lookup"><span data-stu-id="3d521-124">**Rootkey**</span></span>|<span data-ttu-id="3d521-125">ルート キーを証明機関からインポートするために使用します。</span><span class="sxs-lookup"><span data-stu-id="3d521-125">Used to import a root key—from a certification authority.</span></span>|  
|<span data-ttu-id="3d521-126">**filename.pfx (または .cer)**</span><span class="sxs-lookup"><span data-stu-id="3d521-126">**filename.pfx (or .cer)**</span></span>|<span data-ttu-id="3d521-127">.pfx (秘密キー) ファイルまたは .cer (公開キー) ファイルの完全なパス。</span><span class="sxs-lookup"><span data-stu-id="3d521-127">Full path for the .pfx (private keys) or .cer (public keys) file.</span></span>|  
|<span data-ttu-id="3d521-128">**Filepassword**</span><span class="sxs-lookup"><span data-stu-id="3d521-128">**Filepassword**</span></span>|<span data-ttu-id="3d521-129">.pfx ファイルのロックを解除するために必要なパスワード。</span><span class="sxs-lookup"><span data-stu-id="3d521-129">The password required to unlock the .pfx file.</span></span>|  
|<span data-ttu-id="3d521-130">**割り当てられていません**</span><span class="sxs-lookup"><span data-stu-id="3d521-130">**Useridentity**</span></span>|<span data-ttu-id="3d521-131">1 つまたは複数の BizTalk ホストが使用するサービス ID。</span><span class="sxs-lookup"><span data-stu-id="3d521-131">A service identity that one or more BizTalk Hosts uses.</span></span> <span data-ttu-id="3d521-132">ホストを指定せずに、ユーザー アカウントを使用して証明書をインポートするには、適切なユーザー アカウントを入力します。</span><span class="sxs-lookup"><span data-stu-id="3d521-132">Enter a user account if you do not want to specify the host, but want to import a certificate under a user account.</span></span> <span data-ttu-id="3d521-133">**注:**を追加しない場合、 **Useridentity**切り替えるには、ユーティリティによってインポートし、すべてのユーザーの証明書を設定します。</span><span class="sxs-lookup"><span data-stu-id="3d521-133">**Note:**  If you do not add the **Useridentity** switch, the utility imports and set the certificate for all users.</span></span> <span data-ttu-id="3d521-134">**注:**を追加する場合、 **Useridentity**切り替えるには、ですが、値を入力しない WMI は、ユーザー id を自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="3d521-134">**Note:**  If you add the **Useridentity** switch, but do not enter a value, WMI automatically generates the user identity.</span></span>|  
|<span data-ttu-id="3d521-135">**Password**</span><span class="sxs-lookup"><span data-stu-id="3d521-135">**Password**</span></span>|<span data-ttu-id="3d521-136">サービス ID ユーザーのパスワード。</span><span class="sxs-lookup"><span data-stu-id="3d521-136">The password for the service identity user.</span></span>|  
|<span data-ttu-id="3d521-137">**拇印**</span><span class="sxs-lookup"><span data-stu-id="3d521-137">**Thumbprint**</span></span>|<span data-ttu-id="3d521-138">ファイルに複数の証明書が含まれている場合に使用する、特定の証明書の拇印。</span><span class="sxs-lookup"><span data-stu-id="3d521-138">The thumbprint of a specific certificate, in case the file contains more than one certificate.</span></span> <span data-ttu-id="3d521-139">**注:**公開証明書ファイルの場合、ファイルには複数の証明書が含まれていて、拇印を指定しないユーティリティ インポート ファイル内のすべての証明書。</span><span class="sxs-lookup"><span data-stu-id="3d521-139">**Note:**  For a public certificate file, if the file contains more than one certificate and you do not specify the thumbprint, the utility imports all certificates in the file.</span></span> <span data-ttu-id="3d521-140">プライベート証明書ファイルの場合は、インポートする証明書を選択するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3d521-140">For a private certificate file, the utility prompts you to select the certificate to import.</span></span>|  
|<span data-ttu-id="3d521-141">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="3d521-141">**Usage**</span></span>|<span data-ttu-id="3d521-142">インポートしたプライベート証明書の用途。</span><span class="sxs-lookup"><span data-stu-id="3d521-142">The intended usage of the imported private certificate.</span></span> <span data-ttu-id="3d521-143">sign (署名証明書に使用可能)、decrypt (暗号化解除証明書に使用可能)、both (署名証明書と暗号化解除証明書のいずれでもある証明書に使用可能)、または none (署名証明書と暗号化解除証明書のいずれでもある証明書に使用可能) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="3d521-143">Can be sign (for a signing certificate), decrypt (for a decryption certificate), both (for a certificate that is both a signing certificate and a decryption certificate), or none (also for a certificate that is both a signing certificate and a decryption certificate).</span></span> <span data-ttu-id="3d521-144">**注:**設定した場合、 **/Usage**スイッチを none に、ウィザードでは、BizTalk ホストと BizTalk グループに証明書の拇印は設定しません。</span><span class="sxs-lookup"><span data-stu-id="3d521-144">**Note:**  If you set the **/Usage** switch to none, the wizard will not set the thumbprint for the certificate on the BizTalk Hosts or the BizTalk Group.</span></span>|  
|<span data-ttu-id="3d521-145">**エクスポート可能**</span><span class="sxs-lookup"><span data-stu-id="3d521-145">**Exportable**</span></span>|<span data-ttu-id="3d521-146">Can be `True` or `False`.</span><span class="sxs-lookup"><span data-stu-id="3d521-146">Can be `True` or `False`.</span></span> <span data-ttu-id="3d521-147">`True` に指定すると、秘密キーを再エクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="3d521-147">If `True`, the private key can be re-exported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3d521-148">解説</span><span class="sxs-lookup"><span data-stu-id="3d521-148">Remarks</span></span>  
 <span data-ttu-id="3d521-149">CertWizard は、.pfx ファイルの秘密キーを個人用ストアにインポートし、.cer ファイルの公開キーをパブリック ストアにインポートします。</span><span class="sxs-lookup"><span data-stu-id="3d521-149">CertWizard imports a private key from a .pfx file into the personal store, and imports a public key from a .cer file into a public store.</span></span> <span data-ttu-id="3d521-150">秘密キーをインポートする場合は、着信メッセージの証明書に暗号化解除証明書を指定するか、送信メッセージの証明書に署名証明書を指定できます。</span><span class="sxs-lookup"><span data-stu-id="3d521-150">When importing a private key, the certificate can be a decryption certificate for incoming messages or a signing certificate for outgoing messages.</span></span>  
  
 <span data-ttu-id="3d521-151">コマンド プロンプトで完全なコマンドを指定しないと、必須の値を指定するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3d521-151">If you do not give the full command at the command prompt, CertWizard will prompt you to provide the required values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d521-152">参照</span><span class="sxs-lookup"><span data-stu-id="3d521-152">See Also</span></span>  
 <span data-ttu-id="3d521-153">[ユーティリティ](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md) </span><span class="sxs-lookup"><span data-stu-id="3d521-153">[Utilities](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md) </span></span>  
 [<span data-ttu-id="3d521-154">CertWizard ユーティリティを使用した証明書のインポート</span><span class="sxs-lookup"><span data-stu-id="3d521-154">Importing Certificates Using the CertWizard Utility</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-the-certwizard-utility.md)