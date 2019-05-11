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
ms.openlocfilehash: ff147004773bfb620898f5e381fd242a6416f158
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357559"
---
# <a name="certificate-wizard-utility"></a><span data-ttu-id="f4778-102">証明書ウィザード ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="f4778-102">Certificate Wizard Utility</span></span>
<span data-ttu-id="f4778-103">CertWizard ユーティリティを使用して Microsoft で使用するためのプライベートまたはパブリック ストアに .pfx または .cer ファイルから証明書をインポートする[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="f4778-103">You use the CertWizard utility to import a certificate from a .pfx or .cer file into a private or public store for use with Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="f4778-104">証明書ウィザードのソース コードが記載されて、 **C:\Program files \microsoft BizTalk Server\<バージョン\>\SDK\Utilities\Certificate ウィザード**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="f4778-104">The source code for the Certificate Wizard can be found in the **C:\Program Files\Microsoft BizTalk Server \<version\>\SDK\Utilities\Certificate Wizard** folder.</span></span> <span data-ttu-id="f4778-105">64 ビット オペレーティング システムとバージョンの BizTalk Server を使用するが、 **C:\Program Files (x86) \Microsoft BizTalk Server\<バージョン\>\SDK\Utilities\Certificate ウィザード**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="f4778-105">With a 64-bit operating system and version of BizTalk Server, it will be in the **C:\Program Files (x86)\Microsoft BizTalk Server \<version\>\SDK\Utilities\Certificate Wizard** folder.</span></span> <span data-ttu-id="f4778-106">Visual Studio を使用してビルドするのに必要がありますまず証明書ウィザードを使用します。</span><span class="sxs-lookup"><span data-stu-id="f4778-106">To use the Certificate Wizard you will first have to build it using Visual Studio.</span></span>  
  
 <span data-ttu-id="f4778-107">CertWizard は、個人用ストアに秘密キーを .pfx ファイルからインポートし、.cer ファイルから公開キーをパブリック ストアにインポートします。</span><span class="sxs-lookup"><span data-stu-id="f4778-107">CertWizard imports a private key from a .pfx file into the personal store, and imports a public key from a .cer file into a public store.</span></span> <span data-ttu-id="f4778-108">秘密キーをインポートするときに、証明書は受信メッセージの復号化証明書または送信メッセージの署名証明書を指定できます。</span><span class="sxs-lookup"><span data-stu-id="f4778-108">When importing a private key, the certificate can be a decryption certificate for incoming messages or a signing certificate for outgoing messages.</span></span>  
  
 <span data-ttu-id="f4778-109">**構文の説明**</span><span class="sxs-lookup"><span data-stu-id="f4778-109">**Syntax Description**</span></span>  
  
 <span data-ttu-id="f4778-110">次の表では、CertWizard ユーティリティを使用する構文の各部について説明します。</span><span class="sxs-lookup"><span data-stu-id="f4778-110">The following table describes each part of the syntax that the CertWizard utility uses.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f4778-111">構文</span><span class="sxs-lookup"><span data-stu-id="f4778-111">Syntax</span></span>|<span data-ttu-id="f4778-112">説明</span><span class="sxs-lookup"><span data-stu-id="f4778-112">Description</span></span>|  
|<span data-ttu-id="f4778-113">プライベート キー</span><span class="sxs-lookup"><span data-stu-id="f4778-113">Privatekey</span></span>|<span data-ttu-id="f4778-114">秘密キーをインポートするために使用します。</span><span class="sxs-lookup"><span data-stu-id="f4778-114">Used to import a private key.</span></span>|  
|<span data-ttu-id="f4778-115">公開鍵</span><span class="sxs-lookup"><span data-stu-id="f4778-115">Publickey</span></span>|<span data-ttu-id="f4778-116">公開キーをインポートするために使用します。</span><span class="sxs-lookup"><span data-stu-id="f4778-116">Used to import a public key.</span></span>|  
|<span data-ttu-id="f4778-117">Rootkey</span><span class="sxs-lookup"><span data-stu-id="f4778-117">Rootkey</span></span>|<span data-ttu-id="f4778-118">ルート キーのインポートに使用される、証明機関から。</span><span class="sxs-lookup"><span data-stu-id="f4778-118">Used to import a root key—from a certification authority.</span></span>|  
|<span data-ttu-id="f4778-119">filename.pfx (または .cer)</span><span class="sxs-lookup"><span data-stu-id="f4778-119">filename.pfx (or .cer)</span></span>|<span data-ttu-id="f4778-120">.Pfx (秘密キー) または .cer (公開キー) ファイルの完全パス。</span><span class="sxs-lookup"><span data-stu-id="f4778-120">Full path for the .pfx (private keys) or .cer (public keys) file.</span></span>|  
|<span data-ttu-id="f4778-121">Filepassword</span><span class="sxs-lookup"><span data-stu-id="f4778-121">Filepassword</span></span>|<span data-ttu-id="f4778-122">.Pfx ファイルのロック解除に必要なパスワード。</span><span class="sxs-lookup"><span data-stu-id="f4778-122">The password required to unlock the .pfx file.</span></span>|  
|<span data-ttu-id="f4778-123">割り当てられていません</span><span class="sxs-lookup"><span data-stu-id="f4778-123">Useridentity</span></span>|<span data-ttu-id="f4778-124">1 つまたは複数の BizTalk ホストを使用するサービス id を指定します。</span><span class="sxs-lookup"><span data-stu-id="f4778-124">A service identity that one or more BizTalk Hosts uses.</span></span> <span data-ttu-id="f4778-125">ホストを指定したくないが、ユーザー アカウントで証明書をインポートする場合は、ユーザー アカウントを入力します。</span><span class="sxs-lookup"><span data-stu-id="f4778-125">Enter a user account if you do not want to specify the host, but want to import a certificate under a user account.</span></span> <span data-ttu-id="f4778-126">**注:** Useridentity スイッチを追加しないと、ユーティリティはインポートし、すべてのユーザーの証明書を設定します。</span><span class="sxs-lookup"><span data-stu-id="f4778-126">**Note:**  If you do not add the Useridentity switch, the utility imports and set the certificate for all users.</span></span> <span data-ttu-id="f4778-127">**注:** Useridentity スイッチを追加する値を入力しない場合は、WMI では、ユーザー id が自動的に生成します。</span><span class="sxs-lookup"><span data-stu-id="f4778-127">**Note:**  If you add the Useridentity switch, but do not enter a value, WMI automatically generates the user identity.</span></span>|  
|<span data-ttu-id="f4778-128">パスワード</span><span class="sxs-lookup"><span data-stu-id="f4778-128">Password</span></span>|<span data-ttu-id="f4778-129">サービス id ユーザーのパスワード。</span><span class="sxs-lookup"><span data-stu-id="f4778-129">The password for the service identity user.</span></span>|  
|<span data-ttu-id="f4778-130">Thumbprint</span><span class="sxs-lookup"><span data-stu-id="f4778-130">Thumbprint</span></span>|<span data-ttu-id="f4778-131">ファイルの場合も、特定の証明書の拇印には、1 つ以上の証明書が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f4778-131">The thumbprint of a specific certificate, in case the file contains more than one certificate.</span></span> <span data-ttu-id="f4778-132">**注:** 公開証明書ファイルの場合、ファイルには、1 つ以上の証明書が含まれていて、拇印を指定しない場合、ユーティリティは、ファイル内のすべての証明書をインポートします。</span><span class="sxs-lookup"><span data-stu-id="f4778-132">**Note:**  For a public certificate file, if the file contains more than one certificate and you do not specify the thumbprint, the utility imports all certificates in the file.</span></span> <span data-ttu-id="f4778-133">プライベート証明書ファイルの場合、ユーティリティにインポートする証明書を選択するように求められます。</span><span class="sxs-lookup"><span data-stu-id="f4778-133">For a private certificate file, the utility prompts you to select the certificate to import.</span></span>|  
|<span data-ttu-id="f4778-134">使用方法</span><span class="sxs-lookup"><span data-stu-id="f4778-134">Usage</span></span>|<span data-ttu-id="f4778-135">インポートしたプライベート証明書の用途。</span><span class="sxs-lookup"><span data-stu-id="f4778-135">The intended usage of the imported private certificate.</span></span> <span data-ttu-id="f4778-136">次のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="f4778-136">Can be one of the following:</span></span><br /><br /> <span data-ttu-id="f4778-137">**サインオン**(の署名証明書)</span><span class="sxs-lookup"><span data-stu-id="f4778-137">**sign** (for a signing certificate)</span></span><br /><br /> <span data-ttu-id="f4778-138">**復号化**(の復号化証明書)</span><span class="sxs-lookup"><span data-stu-id="f4778-138">**decrypt** (for a decryption certificate)</span></span><br /><br /> <span data-ttu-id="f4778-139">**どちらも**(の署名証明書と暗号化解除証明書の両方である証明書)</span><span class="sxs-lookup"><span data-stu-id="f4778-139">**both** (for a certificate that is both a signing certificate and a decryption certificate)</span></span><br /><br /> <span data-ttu-id="f4778-140">**none** (用証明書を署名証明書と暗号化解除証明書の両方)。</span><span class="sxs-lookup"><span data-stu-id="f4778-140">**none** (also for a certificate that is both a signing certificate and a decryption certificate).</span></span> <span data-ttu-id="f4778-141">**注:**/Usage スイッチを none に設定した場合、ウィザードでは、BizTalk ホストと BizTalk グループでの証明書の拇印は設定しません。</span><span class="sxs-lookup"><span data-stu-id="f4778-141">**Note:**  If you set the /Usage switch to none, the wizard will not set the thumbprint for the certificate on the BizTalk Hosts or the BizTalk Group.</span></span>|  
|<span data-ttu-id="f4778-142">エクスポート可能</span><span class="sxs-lookup"><span data-stu-id="f4778-142">Exportable</span></span>|<span data-ttu-id="f4778-143">**True**または**False**します。</span><span class="sxs-lookup"><span data-stu-id="f4778-143">Can be **True** or **False**.</span></span> <span data-ttu-id="f4778-144">場合**True**、秘密キーを再エクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="f4778-144">If **True**, the private key can be re-exported.</span></span>|  
  
 <span data-ttu-id="f4778-145">**秘密キーをインポートするための構文**</span><span class="sxs-lookup"><span data-stu-id="f4778-145">**Syntax for Importing a Private Key**</span></span>  
  
```  
CertWizard /Privatekey <filename>.pfx [/Filepassword <filepassword>] [/Useridentity <useridentity>] [/Password <password>] [/Thumbprint <thumbprint>] [/Usage sign|decrypt|both|none] [/Exportable true|false]  
```  
  
 <span data-ttu-id="f4778-146">**公開キーをインポートするための構文**</span><span class="sxs-lookup"><span data-stu-id="f4778-146">**Syntax for Importing a Public Key**</span></span>  
  
```  
CertWizard /Publickey <filename>.cer [/Thumbprint <thumbprint>]  
```  
  
 <span data-ttu-id="f4778-147">**ルート キーをインポートするための構文**</span><span class="sxs-lookup"><span data-stu-id="f4778-147">**Syntax for Importing a Root Key**</span></span>  
  
```  
CertWizard /Rootkey <filename>.cer [/Thumbprint <thumbprint>]  
```  
  
## <a name="prerequisites"></a><span data-ttu-id="f4778-148">前提条件</span><span class="sxs-lookup"><span data-stu-id="f4778-148">Prerequisites</span></span>  
 <span data-ttu-id="f4778-149">このトピックの手順を実行するための前提条件は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f4778-149">The following are prerequisites for performing the procedures in this topic:</span></span>  
  
- <span data-ttu-id="f4778-150">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4778-150">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-run-the-certificate-wizard"></a><span data-ttu-id="f4778-151">証明書ウィザードを実行するには</span><span class="sxs-lookup"><span data-stu-id="f4778-151">To run the certificate wizard</span></span>  
  
1. <span data-ttu-id="f4778-152">コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="f4778-152">Open a command prompt.</span></span>  
  
2. <span data-ttu-id="f4778-153">移動[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \utilities します。</span><span class="sxs-lookup"><span data-stu-id="f4778-153">Move to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Utilities.</span></span>  
  
3. <span data-ttu-id="f4778-154">コマンド プロンプトで「 **CertWizard**、入力必須および適切なスイッチ、およびキーを押します**Enter**します。</span><span class="sxs-lookup"><span data-stu-id="f4778-154">At the command prompt, type **CertWizard**, type the required and appropriate switches, and then press **Enter**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="f4778-155">CertWizard は、コマンド プロンプトで完全なコマンドを指定しないと、必要な値を指定することが求められます。</span><span class="sxs-lookup"><span data-stu-id="f4778-155">If you do not give the full command at the command prompt, CertWizard will prompt you to provide the required values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4778-156">参照</span><span class="sxs-lookup"><span data-stu-id="f4778-156">See Also</span></span>  
 [<span data-ttu-id="f4778-157">SDK のユーティリティ</span><span class="sxs-lookup"><span data-stu-id="f4778-157">Utilities in the SDK</span></span>](../core/utilities-in-the-sdk.md)