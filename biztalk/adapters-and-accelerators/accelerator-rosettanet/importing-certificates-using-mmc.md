---
title: MMC を使用して証明書のインポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates, public keys
- certificates, private keys
- importing certificates
- public keys
- private keys
- certificates, importing
ms.assetid: 58fb1711-e295-4aa6-902e-e28e4a2cd921
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 466917e0656dfa39467a00dfa91285b3cb7cf1a1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25961624"
---
# <a name="importing-certificates-using-mmc"></a><span data-ttu-id="29e9c-102">MMC を使用して証明書のインポート</span><span class="sxs-lookup"><span data-stu-id="29e9c-102">Importing Certificates Using MMC</span></span>
<span data-ttu-id="29e9c-103">デジタルをインポートする方法を説明する証明書[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]を使用して、取引先の認証、受信メッセージの暗号化を解除または暗号化または送信メッセージに署名します。</span><span class="sxs-lookup"><span data-stu-id="29e9c-103">This topic describes how to import a digital certificate that [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] uses to authenticate a trading partner, decrypt an incoming message, or encrypt or sign an outgoing message.</span></span>  
  
 <span data-ttu-id="29e9c-104">この手順では、[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] 管理コンソール (MMC) の証明書スナップインを使用します。</span><span class="sxs-lookup"><span data-stu-id="29e9c-104">This procedure uses the Certificates snap-in for the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Management Console (MMC).</span></span> <span data-ttu-id="29e9c-105">この手動プロセスでは、証明書ストアに証明書をインポートしますが、証明書の使用法は個別に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29e9c-105">This manual process imports a certificate into the certificate store, requiring you to configure certificate use separately.</span></span> <span data-ttu-id="29e9c-106">証明書は CertWizard ユーティリティを使用してインポートすることもできます。この場合、証明書の使用法は自動的に構成されます。</span><span class="sxs-lookup"><span data-stu-id="29e9c-106">You can also import a certificate by using the CertWizard utility that automatically configures certificate use for you.</span></span>  
  
 <span data-ttu-id="29e9c-107">プライベート証明書をインポートするには、BizTalk ホストを実行するユーザー アカウントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29e9c-107">To import private certificates, you must use the user accounts under which the BizTalk Hosts run.</span></span>  
  
### <a name="to-import-a-public-key-certificate"></a><span data-ttu-id="29e9c-108">公開キー証明書をインポートするには</span><span class="sxs-lookup"><span data-stu-id="29e9c-108">To import a public-key certificate</span></span>  
  
1.  <span data-ttu-id="29e9c-109">公開キー (.cer) 証明書ファイルを、サーバーのハードディスク上にある証明書のコピー先にコピーします。</span><span class="sxs-lookup"><span data-stu-id="29e9c-109">Copy the public-key (.cer) certificate file to a location on the hard disk of the server to which you are copying certificates.</span></span>  
  
2.  <span data-ttu-id="29e9c-110">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]、順にクリック[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理コンソール**.</span><span class="sxs-lookup"><span data-stu-id="29e9c-110">Click **Start**, point to **All Programs**, point to **Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], and then click [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **Management Console**.</span></span>  
  
3.  <span data-ttu-id="29e9c-111">[!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)]管理コンソールで、展開**証明書 (ローカル コンピューター)** です。</span><span class="sxs-lookup"><span data-stu-id="29e9c-111">In the [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] Management Console, expand **Certificates (Local Computer)**.</span></span> <span data-ttu-id="29e9c-112">ログインするユーザーは、そのコンピューターの管理権限を持っていなければなりません。</span><span class="sxs-lookup"><span data-stu-id="29e9c-112">The logged-in user must have administrative permissions to the computer.</span></span>  
  
4.  <span data-ttu-id="29e9c-113">右クリック**ほかの人**、 をポイント**すべてのタスク**、クリックして**インポート**です。</span><span class="sxs-lookup"><span data-stu-id="29e9c-113">Right-click **Other People**, point to **All Tasks**, and then click **Import**.</span></span>  
  
5.  <span data-ttu-id="29e9c-114">**証明書のインポート ウィザードへようこそ**] ページで [**次**です。</span><span class="sxs-lookup"><span data-stu-id="29e9c-114">On the **Certificate Import Wizard Welcome** page, click **Next**.</span></span>  
  
6.  <span data-ttu-id="29e9c-115">**インポートするファイル** ページで、をクリックして**参照**証明書ファイルを含むフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="29e9c-115">On the **File to Import** page, click **Browse** and locate the folder that contains the certificate files.</span></span> <span data-ttu-id="29e9c-116">クリックして、証明書をインポートするファイルを選択して**開く**です。</span><span class="sxs-lookup"><span data-stu-id="29e9c-116">Select the file from which you want to import the certificate, and then click **Open**.</span></span>  
  
7.  <span data-ttu-id="29e9c-117">**証明書ストア** ページで、いずれかを選択**証明書の種類に基づいて証明書を自動的に選択**または**次のストアに証明書をすべてを配置**.</span><span class="sxs-lookup"><span data-stu-id="29e9c-117">On the **Certificate store** page, select either **Automatically select the certificate based on the type of certificate** or **Place all certificates in the following store**.</span></span> <span data-ttu-id="29e9c-118">選択した場合**次のストアに証明書をすべてを配置**、] をクリックして**参照**証明書ストアを選択してをクリックし、 **[ok]**、順にクリック **[次へ**.</span><span class="sxs-lookup"><span data-stu-id="29e9c-118">If you select **Place all certificates in the following store**, click **Browse**, select the certificate store, click **OK**, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="29e9c-119">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29e9c-119">Click **Finish**.</span></span>  
  
### <a name="to-import-a-private-key-certificate"></a><span data-ttu-id="29e9c-120">秘密キー証明書をインポートするには</span><span class="sxs-lookup"><span data-stu-id="29e9c-120">To import a private-key certificate</span></span>  
  
1.  <span data-ttu-id="29e9c-121">秘密キー (.pfx) 証明書ファイルを、サーバーのハードディスク上にある証明書のコピー先にコピーします。</span><span class="sxs-lookup"><span data-stu-id="29e9c-121">Copy private-key (.pfx) certificate files to a location on the hard disk of the server to which you are copying certificates.</span></span>  
  
2.  <span data-ttu-id="29e9c-122">をクリックして**開始**、 をクリックして**実行**、型 **/user として実行:\<サービスをホスト\>mmc**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="29e9c-122">Click **Start**, click **Run**, type **run as /user:\<host service\> mmc**, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="29e9c-123">\<*サービスをホスト*\>、インストールしたときに、ホスト サービスに対して自動的に選択されたサービスの名前を入力[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="29e9c-123">For \<*host service*\>, type the name of the service that was automatically selected for the host service when you installed [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)].</span></span>  
  
3.  <span data-ttu-id="29e9c-124">パスワードを入力\<*サービスをホスト*\>、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="29e9c-124">Type the password for \<*host service*\>, and then press **Enter**.</span></span>  
  
4.  <span data-ttu-id="29e9c-125">[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]管理コンソールで、**ファイル** メニューのをクリックして**スナップインの追加と削除**です。</span><span class="sxs-lookup"><span data-stu-id="29e9c-125">In [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Management Console, on the **File** menu, click **Add/Remove Snap-in**.</span></span>  
  
5.  <span data-ttu-id="29e9c-126">[スナップインの追加と削除] ダイアログ ボックスで、**追加**です。</span><span class="sxs-lookup"><span data-stu-id="29e9c-126">In the Add/Remove Snap-in dialog box, click **Add**.</span></span>  
  
6.  <span data-ttu-id="29e9c-127">スタンドアロン スナップインの追加 ダイアログ ボックスで、次のように選択します。**証明書**、 をクリック**追加**、 をクリック**閉じる**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="29e9c-127">In the Add Standalone Snap-in dialog box, select **Certificates**, click **Add**, click **Close**, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="29e9c-128">[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]管理コンソールで、展開**証明書 - 現在のユーザー**を右クリックして**個人**、 をポイント**すべてのタスク**、クリックして**インポート**です。</span><span class="sxs-lookup"><span data-stu-id="29e9c-128">In [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Management Console, expand **Certificates - Current User**, right-click **Personal**, point to **All Tasks**, and then click **Import**.</span></span>  
  
8.  <span data-ttu-id="29e9c-129">**証明書のインポート ウィザードへようこそ**] ページで [**次**です。</span><span class="sxs-lookup"><span data-stu-id="29e9c-129">On the **Certificate Import Wizard Welcome** page, click **Next**.</span></span>  
  
9. <span data-ttu-id="29e9c-130">**インポートするファイル** ページで、をクリックして**参照**をインポートする証明書を含む .pfx 証明書ファイルを含むフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="29e9c-130">On the **File to Import** page, click **Browse** and locate the folder that contains the .pfx certificate file that contains the certificate that you want to import.</span></span> <span data-ttu-id="29e9c-131">適切なファイルを選択し、クリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="29e9c-131">Select the appropriate file, and then click **Open**.</span></span>  
  
10. <span data-ttu-id="29e9c-132">**パスワード**] ページの [、**パスワード**ボックスに、秘密キー ファイルのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="29e9c-132">On the **Password** page, in the **Password** box, type the password for the private-key file.</span></span>  
  
11. <span data-ttu-id="29e9c-133">選択**強力な秘密キーの保護を有効にする**または**キーをエクスポート可能としてマーク**、クリックして **[次へ]** です。</span><span class="sxs-lookup"><span data-stu-id="29e9c-133">Select **Enable strong private key protection** or **Mark this key as exportable**, and then click **Next**.</span></span>  
  
12. <span data-ttu-id="29e9c-134">**証明書ストア** ページで、いずれかを選択**証明書の種類に基づいて証明書を自動的に選択**または**次のストアに証明書をすべてを配置**.</span><span class="sxs-lookup"><span data-stu-id="29e9c-134">On the **Certificate store** page, select either **Automatically select the certificate based on the type of certificate** or **Place all certificates in the following store**.</span></span> <span data-ttu-id="29e9c-135">選択した場合**次のストアに証明書をすべてを配置**、 をクリックして**参照**ストアを選択してをクリックし、 **ok**、順にクリック**次へ**です。</span><span class="sxs-lookup"><span data-stu-id="29e9c-135">If you select **Place all certificates in the following store**, click **Browse**, select the store, click **OK**, and then click **Next**.</span></span>  
  
13. <span data-ttu-id="29e9c-136">**証明書のインポート ウィザードの完了**] ページで [**完了**です。</span><span class="sxs-lookup"><span data-stu-id="29e9c-136">On the **Completing the Certificate Import Wizard** page, click **Finish**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29e9c-137">参照</span><span class="sxs-lookup"><span data-stu-id="29e9c-137">See Also</span></span>  
 <span data-ttu-id="29e9c-138">[MMC を使用してインポートされた証明書を構成します。](../../adapters-and-accelerators/accelerator-rosettanet/configuring-certificates-imported-using-mmc.md) </span><span class="sxs-lookup"><span data-stu-id="29e9c-138">[Configuring Certificates Imported Using MMC](../../adapters-and-accelerators/accelerator-rosettanet/configuring-certificates-imported-using-mmc.md) </span></span>  
 [<span data-ttu-id="29e9c-139">CertWizard</span><span class="sxs-lookup"><span data-stu-id="29e9c-139">CertWizard</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/certwizard.md)