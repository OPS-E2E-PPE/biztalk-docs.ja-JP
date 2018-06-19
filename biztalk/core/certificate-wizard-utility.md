---
title: 証明書ウィザード ユーティリティ |Microsoft ドキュメント
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
ms.openlocfilehash: 3b0341a11c45cd08f8476d48ea38cbf96bcc49c1
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006179"
---
# <a name="certificate-wizard-utility"></a><span data-ttu-id="17b26-102">証明書ウィザード ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="17b26-102">Certificate Wizard Utility</span></span>
<span data-ttu-id="17b26-103">.pfx ファイルまたは .cer ファイルの証明書をプライベート ストアまたはパブリック ストアにインポートして Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で使用できるようにするには、CertWizard ユーティリティを使用します。</span><span class="sxs-lookup"><span data-stu-id="17b26-103">You use the CertWizard utility to import a certificate from a .pfx or .cer file into a private or public store for use with Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="17b26-104">証明書ウィザードのソース コードは含まれて、 **C:\Program files \microsoft BizTalk Server\<バージョン\>\SDK\Utilities\Certificate ウィザード**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="17b26-104">The source code for the Certificate Wizard can be found in the **C:\Program Files\Microsoft BizTalk Server \<version\>\SDK\Utilities\Certificate Wizard** folder.</span></span> <span data-ttu-id="17b26-105">64 ビット オペレーティング システムとバージョンの BizTalk Server になります、 **C:\Program Files (x86) \Microsoft BizTalk Server\<バージョン\>\SDK\Utilities\Certificate ウィザード**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="17b26-105">With a 64-bit operating system and version of BizTalk Server, it will be in the **C:\Program Files (x86)\Microsoft BizTalk Server \<version\>\SDK\Utilities\Certificate Wizard** folder.</span></span> <span data-ttu-id="17b26-106">Visual Studio を使用して構築するのに必要が最初に証明書ウィザードを使用します。</span><span class="sxs-lookup"><span data-stu-id="17b26-106">To use the Certificate Wizard you will first have to build it using Visual Studio.</span></span>  
  
 <span data-ttu-id="17b26-107">CertWizard は、.pfx ファイルの秘密キーを個人用ストアにインポートし、.cer ファイルの公開キーをパブリック ストアにインポートします。</span><span class="sxs-lookup"><span data-stu-id="17b26-107">CertWizard imports a private key from a .pfx file into the personal store, and imports a public key from a .cer file into a public store.</span></span> <span data-ttu-id="17b26-108">秘密キーをインポートする場合は、着信メッセージの証明書に暗号化解除証明書を指定するか、送信メッセージの証明書に署名証明書を指定できます。</span><span class="sxs-lookup"><span data-stu-id="17b26-108">When importing a private key, the certificate can be a decryption certificate for incoming messages or a signing certificate for outgoing messages.</span></span>  
  
 <span data-ttu-id="17b26-109">**構文の説明**</span><span class="sxs-lookup"><span data-stu-id="17b26-109">**Syntax Description**</span></span>  
  
 <span data-ttu-id="17b26-110">次の表に、CertWizard ユーティリティが使用する構文の各要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="17b26-110">The following table describes each part of the syntax that the CertWizard utility uses.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="17b26-111">構文</span><span class="sxs-lookup"><span data-stu-id="17b26-111">Syntax</span></span>|<span data-ttu-id="17b26-112">Description</span><span class="sxs-lookup"><span data-stu-id="17b26-112">Description</span></span>|  
|<span data-ttu-id="17b26-113">Privatekey</span><span class="sxs-lookup"><span data-stu-id="17b26-113">Privatekey</span></span>|<span data-ttu-id="17b26-114">秘密キーをインポートするために使用します。</span><span class="sxs-lookup"><span data-stu-id="17b26-114">Used to import a private key.</span></span>|  
|<span data-ttu-id="17b26-115">Publickey</span><span class="sxs-lookup"><span data-stu-id="17b26-115">Publickey</span></span>|<span data-ttu-id="17b26-116">公開キーをインポートするために使用します。</span><span class="sxs-lookup"><span data-stu-id="17b26-116">Used to import a public key.</span></span>|  
|<span data-ttu-id="17b26-117">Rootkey</span><span class="sxs-lookup"><span data-stu-id="17b26-117">Rootkey</span></span>|<span data-ttu-id="17b26-118">ルート キーを証明機関からインポートするために使用します。</span><span class="sxs-lookup"><span data-stu-id="17b26-118">Used to import a root key—from a certification authority.</span></span>|  
|<span data-ttu-id="17b26-119">filename.pfx (または .cer)</span><span class="sxs-lookup"><span data-stu-id="17b26-119">filename.pfx (or .cer)</span></span>|<span data-ttu-id="17b26-120">.pfx (秘密キー) ファイルまたは .cer (公開キー) ファイルの完全なパス。</span><span class="sxs-lookup"><span data-stu-id="17b26-120">Full path for the .pfx (private keys) or .cer (public keys) file.</span></span>|  
|<span data-ttu-id="17b26-121">Filepassword</span><span class="sxs-lookup"><span data-stu-id="17b26-121">Filepassword</span></span>|<span data-ttu-id="17b26-122">.pfx ファイルのロックを解除するために必要なパスワード。</span><span class="sxs-lookup"><span data-stu-id="17b26-122">The password required to unlock the .pfx file.</span></span>|  
|<span data-ttu-id="17b26-123">Useridentity</span><span class="sxs-lookup"><span data-stu-id="17b26-123">Useridentity</span></span>|<span data-ttu-id="17b26-124">1 つまたは複数の BizTalk ホストが使用するサービス ID。</span><span class="sxs-lookup"><span data-stu-id="17b26-124">A service identity that one or more BizTalk Hosts uses.</span></span> <span data-ttu-id="17b26-125">ホストを指定せずに、ユーザー アカウントを使用して証明書をインポートするには、適切なユーザー アカウントを入力します。</span><span class="sxs-lookup"><span data-stu-id="17b26-125">Enter a user account if you do not want to specify the host, but want to import a certificate under a user account.</span></span> <span data-ttu-id="17b26-126">**注:** Useridentity スイッチを追加しない場合、ユーティリティはインポートし、すべてのユーザーの証明書を設定します。</span><span class="sxs-lookup"><span data-stu-id="17b26-126">**Note:**  If you do not add the Useridentity switch, the utility imports and set the certificate for all users.</span></span> <span data-ttu-id="17b26-127">**注:** Useridentity スイッチを追加する値を入力しなかった場合は、WMI に自動的にユーザー id が生成されます。</span><span class="sxs-lookup"><span data-stu-id="17b26-127">**Note:**  If you add the Useridentity switch, but do not enter a value, WMI automatically generates the user identity.</span></span>|  
|<span data-ttu-id="17b26-128">Password</span><span class="sxs-lookup"><span data-stu-id="17b26-128">Password</span></span>|<span data-ttu-id="17b26-129">サービス ID ユーザーのパスワード。</span><span class="sxs-lookup"><span data-stu-id="17b26-129">The password for the service identity user.</span></span>|  
|<span data-ttu-id="17b26-130">Thumbprint</span><span class="sxs-lookup"><span data-stu-id="17b26-130">Thumbprint</span></span>|<span data-ttu-id="17b26-131">ファイルに複数の証明書が含まれている場合に使用する、特定の証明書の拇印。</span><span class="sxs-lookup"><span data-stu-id="17b26-131">The thumbprint of a specific certificate, in case the file contains more than one certificate.</span></span> <span data-ttu-id="17b26-132">**注:** 公開証明書ファイルの場合、ファイルには複数の証明書が含まれていて、拇印を指定しないユーティリティ インポート ファイル内のすべての証明書。</span><span class="sxs-lookup"><span data-stu-id="17b26-132">**Note:**  For a public certificate file, if the file contains more than one certificate and you do not specify the thumbprint, the utility imports all certificates in the file.</span></span> <span data-ttu-id="17b26-133">プライベート証明書ファイルの場合は、インポートする証明書を選択するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="17b26-133">For a private certificate file, the utility prompts you to select the certificate to import.</span></span>|  
|<span data-ttu-id="17b26-134">使用方法</span><span class="sxs-lookup"><span data-stu-id="17b26-134">Usage</span></span>|<span data-ttu-id="17b26-135">インポートしたプライベート証明書の用途。</span><span class="sxs-lookup"><span data-stu-id="17b26-135">The intended usage of the imported private certificate.</span></span> <span data-ttu-id="17b26-136">次のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="17b26-136">Can be one of the following:</span></span><br /><br /> <span data-ttu-id="17b26-137">**サインオン**(の署名証明書の)</span><span class="sxs-lookup"><span data-stu-id="17b26-137">**sign** (for a signing certificate)</span></span><br /><br /> <span data-ttu-id="17b26-138">**復号化**(の暗号化解除証明書の)</span><span class="sxs-lookup"><span data-stu-id="17b26-138">**decrypt** (for a decryption certificate)</span></span><br /><br /> <span data-ttu-id="17b26-139">**両方**(用の証明書を署名する証明書と暗号化解除証明書の両方)</span><span class="sxs-lookup"><span data-stu-id="17b26-139">**both** (for a certificate that is both a signing certificate and a decryption certificate)</span></span><br /><br /> <span data-ttu-id="17b26-140">**none** (用の証明書を署名する証明書と暗号化解除証明書の両方)。</span><span class="sxs-lookup"><span data-stu-id="17b26-140">**none** (also for a certificate that is both a signing certificate and a decryption certificate).</span></span> <span data-ttu-id="17b26-141">**注:** /Usage スイッチを none に設定した場合、ウィザードが設定されていない証明書の拇印、BizTalk ホストと BizTalk グループにします。</span><span class="sxs-lookup"><span data-stu-id="17b26-141">**Note:**  If you set the /Usage switch to none, the wizard will not set the thumbprint for the certificate on the BizTalk Hosts or the BizTalk Group.</span></span>|  
|<span data-ttu-id="17b26-142">Exportable</span><span class="sxs-lookup"><span data-stu-id="17b26-142">Exportable</span></span>|<span data-ttu-id="17b26-143">指定できます**True**または**False**です。</span><span class="sxs-lookup"><span data-stu-id="17b26-143">Can be **True** or **False**.</span></span> <span data-ttu-id="17b26-144">場合**True**、秘密キーを再エクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="17b26-144">If **True**, the private key can be re-exported.</span></span>|  
  
 <span data-ttu-id="17b26-145">**秘密キーをインポートするための構文**</span><span class="sxs-lookup"><span data-stu-id="17b26-145">**Syntax for Importing a Private Key**</span></span>  
  
```  
CertWizard /Privatekey <filename>.pfx [/Filepassword <filepassword>] [/Useridentity <useridentity>] [/Password <password>] [/Thumbprint <thumbprint>] [/Usage sign|decrypt|both|none] [/Exportable true|false]  
```  
  
 <span data-ttu-id="17b26-146">**公開キーをインポートするための構文**</span><span class="sxs-lookup"><span data-stu-id="17b26-146">**Syntax for Importing a Public Key**</span></span>  
  
```  
CertWizard /Publickey <filename>.cer [/Thumbprint <thumbprint>]  
```  
  
 <span data-ttu-id="17b26-147">**ルート キーをインポートするための構文**</span><span class="sxs-lookup"><span data-stu-id="17b26-147">**Syntax for Importing a Root Key**</span></span>  
  
```  
CertWizard /Rootkey <filename>.cer [/Thumbprint <thumbprint>]  
```  
  
## <a name="prerequisites"></a><span data-ttu-id="17b26-148">前提条件</span><span class="sxs-lookup"><span data-stu-id="17b26-148">Prerequisites</span></span>  
 <span data-ttu-id="17b26-149">このトピックの手順を実行するための前提条件は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="17b26-149">The following are prerequisites for performing the procedures in this topic:</span></span>  
  
-   <span data-ttu-id="17b26-150">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="17b26-150">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-run-the-certificate-wizard"></a><span data-ttu-id="17b26-151">証明書ウィザードを実行するには</span><span class="sxs-lookup"><span data-stu-id="17b26-151">To run the certificate wizard</span></span>  
  
1.  <span data-ttu-id="17b26-152">コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="17b26-152">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="17b26-153">[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Utilities に移動します。</span><span class="sxs-lookup"><span data-stu-id="17b26-153">Move to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Utilities.</span></span>  
  
3.  <span data-ttu-id="17b26-154">コマンド プロンプトで次のように入力します。 **CertWizard**、必須と適切なスイッチを入力して、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="17b26-154">At the command prompt, type **CertWizard**, type the required and appropriate switches, and then press **Enter**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="17b26-155">コマンド プロンプトで完全なコマンドを指定しないと、必須の値を指定するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="17b26-155">If you do not give the full command at the command prompt, CertWizard will prompt you to provide the required values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17b26-156">参照</span><span class="sxs-lookup"><span data-stu-id="17b26-156">See Also</span></span>  
 [<span data-ttu-id="17b26-157">SDK のユーティリティ</span><span class="sxs-lookup"><span data-stu-id="17b26-157">Utilities in the SDK</span></span>](../core/utilities-in-the-sdk.md)