---
title: 証明書のウィザード ユーティリティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5ff72810-c7b3-4f67-8f9f-e127eacc153e
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 184056b6904b38945de836f04008b4a6fe90436a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970609"
---
# <a name="certificate-wizard-utility"></a><span data-ttu-id="870d8-102">証明書ウィザード ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="870d8-102">Certificate Wizard Utility</span></span>
<span data-ttu-id="870d8-103">.pfx ファイルまたは .cer ファイルの証明書をプライベート ストアまたはパブリック ストアにインポートして Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で使用できるようにするには、CertWizard ユーティリティを使用します。</span><span class="sxs-lookup"><span data-stu-id="870d8-103">You use the CertWizard utility to import a certificate from a .pfx or .cer file into a private or public store for use with Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="870d8-104">証明書ウィザードのソース コードが記載されて、 **C:\Program files \microsoft BizTalk Server\<バージョン\>\SDK\Utilities\Certificate ウィザード**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="870d8-104">The source code for the Certificate Wizard can be found in the **C:\Program Files\Microsoft BizTalk Server \<version\>\SDK\Utilities\Certificate Wizard** folder.</span></span> <span data-ttu-id="870d8-105">64 ビット オペレーティング システムとバージョンの BizTalk Server を使用するが、 **C:\Program Files (x86) \Microsoft BizTalk Server\<バージョン\>\SDK\Utilities\Certificate ウィザード**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="870d8-105">With a 64-bit operating system and version of BizTalk Server, it will be in the **C:\Program Files (x86)\Microsoft BizTalk Server \<version\>\SDK\Utilities\Certificate Wizard** folder.</span></span> <span data-ttu-id="870d8-106">Visual Studio を使用してビルドするのに必要がありますまず証明書ウィザードを使用します。</span><span class="sxs-lookup"><span data-stu-id="870d8-106">To use the Certificate Wizard you will first have to build it using Visual Studio.</span></span>  
  
 <span data-ttu-id="870d8-107">CertWizard は、.pfx ファイルの秘密キーを個人用ストアにインポートし、.cer ファイルの公開キーをパブリック ストアにインポートします。</span><span class="sxs-lookup"><span data-stu-id="870d8-107">CertWizard imports a private key from a .pfx file into the personal store, and imports a public key from a .cer file into a public store.</span></span> <span data-ttu-id="870d8-108">秘密キーをインポートする場合は、着信メッセージの証明書に暗号化解除証明書を指定するか、送信メッセージの証明書に署名証明書を指定できます。</span><span class="sxs-lookup"><span data-stu-id="870d8-108">When importing a private key, the certificate can be a decryption certificate for incoming messages or a signing certificate for outgoing messages.</span></span>  
  
 <span data-ttu-id="870d8-109">**構文の説明**</span><span class="sxs-lookup"><span data-stu-id="870d8-109">**Syntax Description**</span></span>  
  
 <span data-ttu-id="870d8-110">次の表に、CertWizard ユーティリティが使用する構文の各要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="870d8-110">The following table describes each part of the syntax that the CertWizard utility uses.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="870d8-111">構文</span><span class="sxs-lookup"><span data-stu-id="870d8-111">Syntax</span></span>|<span data-ttu-id="870d8-112">説明</span><span class="sxs-lookup"><span data-stu-id="870d8-112">Description</span></span>|  
|<span data-ttu-id="870d8-113">Privatekey</span><span class="sxs-lookup"><span data-stu-id="870d8-113">Privatekey</span></span>|<span data-ttu-id="870d8-114">秘密キーをインポートするために使用します。</span><span class="sxs-lookup"><span data-stu-id="870d8-114">Used to import a private key.</span></span>|  
|<span data-ttu-id="870d8-115">Publickey</span><span class="sxs-lookup"><span data-stu-id="870d8-115">Publickey</span></span>|<span data-ttu-id="870d8-116">公開キーをインポートするために使用します。</span><span class="sxs-lookup"><span data-stu-id="870d8-116">Used to import a public key.</span></span>|  
|<span data-ttu-id="870d8-117">Rootkey</span><span class="sxs-lookup"><span data-stu-id="870d8-117">Rootkey</span></span>|<span data-ttu-id="870d8-118">ルート キーを証明機関からインポートするために使用します。</span><span class="sxs-lookup"><span data-stu-id="870d8-118">Used to import a root key—from a certification authority.</span></span>|  
|<span data-ttu-id="870d8-119">filename.pfx (または .cer)</span><span class="sxs-lookup"><span data-stu-id="870d8-119">filename.pfx (or .cer)</span></span>|<span data-ttu-id="870d8-120">.pfx (秘密キー) ファイルまたは .cer (公開キー) ファイルの完全なパス。</span><span class="sxs-lookup"><span data-stu-id="870d8-120">Full path for the .pfx (private keys) or .cer (public keys) file.</span></span>|  
|<span data-ttu-id="870d8-121">Filepassword</span><span class="sxs-lookup"><span data-stu-id="870d8-121">Filepassword</span></span>|<span data-ttu-id="870d8-122">.pfx ファイルのロックを解除するために必要なパスワード。</span><span class="sxs-lookup"><span data-stu-id="870d8-122">The password required to unlock the .pfx file.</span></span>|  
|<span data-ttu-id="870d8-123">Useridentity</span><span class="sxs-lookup"><span data-stu-id="870d8-123">Useridentity</span></span>|<span data-ttu-id="870d8-124">1 つまたは複数の BizTalk ホストが使用するサービス ID。</span><span class="sxs-lookup"><span data-stu-id="870d8-124">A service identity that one or more BizTalk Hosts uses.</span></span> <span data-ttu-id="870d8-125">ホストを指定せずに、ユーザー アカウントを使用して証明書をインポートするには、適切なユーザー アカウントを入力します。</span><span class="sxs-lookup"><span data-stu-id="870d8-125">Enter a user account if you do not want to specify the host, but want to import a certificate under a user account.</span></span> <span data-ttu-id="870d8-126">**注:** Useridentity スイッチを追加しない場合、ユーティリティはインポートし、すべてのユーザーの証明書を設定します。</span><span class="sxs-lookup"><span data-stu-id="870d8-126">**Note:**  If you do not add the Useridentity switch, the utility imports and set the certificate for all users.</span></span> <span data-ttu-id="870d8-127">**注:** Useridentity スイッチを追加する値を入力しない場合は、WMI に自動的にユーザー id が生成されます。</span><span class="sxs-lookup"><span data-stu-id="870d8-127">**Note:**  If you add the Useridentity switch, but do not enter a value, WMI automatically generates the user identity.</span></span>|  
|<span data-ttu-id="870d8-128">パスワード</span><span class="sxs-lookup"><span data-stu-id="870d8-128">Password</span></span>|<span data-ttu-id="870d8-129">サービス ID ユーザーのパスワード。</span><span class="sxs-lookup"><span data-stu-id="870d8-129">The password for the service identity user.</span></span>|  
|<span data-ttu-id="870d8-130">Thumbprint</span><span class="sxs-lookup"><span data-stu-id="870d8-130">Thumbprint</span></span>|<span data-ttu-id="870d8-131">ファイルに複数の証明書が含まれている場合に使用する、特定の証明書の拇印。</span><span class="sxs-lookup"><span data-stu-id="870d8-131">The thumbprint of a specific certificate, in case the file contains more than one certificate.</span></span> <span data-ttu-id="870d8-132">**注:** 公開証明書ファイルの場合、ファイルには 1 つ以上の証明書が含まれていて、拇印を指定しないユーティリティ インポート ファイル内のすべての証明書。</span><span class="sxs-lookup"><span data-stu-id="870d8-132">**Note:**  For a public certificate file, if the file contains more than one certificate and you do not specify the thumbprint, the utility imports all certificates in the file.</span></span> <span data-ttu-id="870d8-133">プライベート証明書ファイルの場合は、インポートする証明書を選択するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="870d8-133">For a private certificate file, the utility prompts you to select the certificate to import.</span></span>|  
|<span data-ttu-id="870d8-134">使用方法</span><span class="sxs-lookup"><span data-stu-id="870d8-134">Usage</span></span>|<span data-ttu-id="870d8-135">インポートしたプライベート証明書の用途。</span><span class="sxs-lookup"><span data-stu-id="870d8-135">The intended usage of the imported private certificate.</span></span> <span data-ttu-id="870d8-136">次のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="870d8-136">Can be one of the following:</span></span><br /><br /> <span data-ttu-id="870d8-137">**サインオン**(の署名証明書)</span><span class="sxs-lookup"><span data-stu-id="870d8-137">**sign** (for a signing certificate)</span></span><br /><br /> <span data-ttu-id="870d8-138">**復号化**(の復号化証明書)</span><span class="sxs-lookup"><span data-stu-id="870d8-138">**decrypt** (for a decryption certificate)</span></span><br /><br /> <span data-ttu-id="870d8-139">**どちらも**(の署名証明書と暗号化解除証明書の両方である証明書)</span><span class="sxs-lookup"><span data-stu-id="870d8-139">**both** (for a certificate that is both a signing certificate and a decryption certificate)</span></span><br /><br /> <span data-ttu-id="870d8-140">**none** (用証明書を署名証明書と暗号化解除証明書の両方)。</span><span class="sxs-lookup"><span data-stu-id="870d8-140">**none** (also for a certificate that is both a signing certificate and a decryption certificate).</span></span> <span data-ttu-id="870d8-141">**注:** /Usage スイッチを none に設定した場合、ウィザードには設定されません証明書の拇印、BizTalk ホストと BizTalk グループ。</span><span class="sxs-lookup"><span data-stu-id="870d8-141">**Note:**  If you set the /Usage switch to none, the wizard will not set the thumbprint for the certificate on the BizTalk Hosts or the BizTalk Group.</span></span>|  
|<span data-ttu-id="870d8-142">Exportable</span><span class="sxs-lookup"><span data-stu-id="870d8-142">Exportable</span></span>|<span data-ttu-id="870d8-143">**True**または**False**します。</span><span class="sxs-lookup"><span data-stu-id="870d8-143">Can be **True** or **False**.</span></span> <span data-ttu-id="870d8-144">場合**True**、秘密キーを再エクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="870d8-144">If **True**, the private key can be re-exported.</span></span>|  
  
 <span data-ttu-id="870d8-145">**秘密キーをインポートするための構文**</span><span class="sxs-lookup"><span data-stu-id="870d8-145">**Syntax for Importing a Private Key**</span></span>  
  
```  
CertWizard /Privatekey <filename>.pfx [/Filepassword <filepassword>] [/Useridentity <useridentity>] [/Password <password>] [/Thumbprint <thumbprint>] [/Usage sign|decrypt|both|none] [/Exportable true|false]  
```  
  
 <span data-ttu-id="870d8-146">**公開キーをインポートするための構文**</span><span class="sxs-lookup"><span data-stu-id="870d8-146">**Syntax for Importing a Public Key**</span></span>  
  
```  
CertWizard /Publickey <filename>.cer [/Thumbprint <thumbprint>]  
```  
  
 <span data-ttu-id="870d8-147">**ルート キーをインポートするための構文**</span><span class="sxs-lookup"><span data-stu-id="870d8-147">**Syntax for Importing a Root Key**</span></span>  
  
```  
CertWizard /Rootkey <filename>.cer [/Thumbprint <thumbprint>]  
```  
  
## <a name="prerequisites"></a><span data-ttu-id="870d8-148">前提条件</span><span class="sxs-lookup"><span data-stu-id="870d8-148">Prerequisites</span></span>  
 <span data-ttu-id="870d8-149">このトピックの手順を実行するための前提条件は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="870d8-149">The following are prerequisites for performing the procedures in this topic:</span></span>  
  
- <span data-ttu-id="870d8-150">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="870d8-150">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-run-the-certificate-wizard"></a><span data-ttu-id="870d8-151">証明書ウィザードを実行するには</span><span class="sxs-lookup"><span data-stu-id="870d8-151">To run the certificate wizard</span></span>  
  
1. <span data-ttu-id="870d8-152">コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="870d8-152">Open a command prompt.</span></span>  
  
2. <span data-ttu-id="870d8-153">[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Utilities に移動します。</span><span class="sxs-lookup"><span data-stu-id="870d8-153">Move to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Utilities.</span></span>  
  
3. <span data-ttu-id="870d8-154">コマンド プロンプトで「 **CertWizard**、入力必須および適切なスイッチ、およびキーを押します**Enter**します。</span><span class="sxs-lookup"><span data-stu-id="870d8-154">At the command prompt, type **CertWizard**, type the required and appropriate switches, and then press **Enter**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="870d8-155">コマンド プロンプトで完全なコマンドを指定しないと、必須の値を指定するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="870d8-155">If you do not give the full command at the command prompt, CertWizard will prompt you to provide the required values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="870d8-156">参照</span><span class="sxs-lookup"><span data-stu-id="870d8-156">See Also</span></span>  
 [<span data-ttu-id="870d8-157">SDK のユーティリティ</span><span class="sxs-lookup"><span data-stu-id="870d8-157">Utilities in the SDK</span></span>](../core/utilities-in-the-sdk.md)