---
title: MMC を使用して証明書のインポート |Microsoft Docs
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
ms.openlocfilehash: 0d813adad739f7843308bcd3c53aa242ff97520c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283602"
---
# <a name="importing-certificates-using-mmc"></a><span data-ttu-id="23df6-102">MMC を使用して証明書のインポート</span><span class="sxs-lookup"><span data-stu-id="23df6-102">Importing Certificates Using MMC</span></span>
<span data-ttu-id="23df6-103">このトピックでは、マイクロソフトのデジタル証明書をインポートする方法を説明します[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]を使用して取引先パートナーを認証、受信メッセージの暗号化を解除または暗号化または送信メッセージに署名します。</span><span class="sxs-lookup"><span data-stu-id="23df6-103">This topic describes how to import a digital certificate that Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] uses to authenticate a trading partner, decrypt an incoming message, or encrypt or sign an outgoing message.</span></span>  
  
 <span data-ttu-id="23df6-104">この手順では、Microsoft 管理コンソール (MMC) の証明書スナップインで使用します。</span><span class="sxs-lookup"><span data-stu-id="23df6-104">This procedure uses the Certificates snap-in for the Microsoft Management Console (MMC).</span></span> <span data-ttu-id="23df6-105">この手動プロセスは、証明書の使用を個別に構成することを必要とする証明書ストアに証明書をインポートします。</span><span class="sxs-lookup"><span data-stu-id="23df6-105">This manual process imports a certificate into the certificate store, requiring you to configure certificate use separately.</span></span> <span data-ttu-id="23df6-106">証明書の使用を自動的に構成する CertWizard ユーティリティを使用して、証明書をインポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="23df6-106">You can also import a certificate by using the CertWizard utility that automatically configures certificate use for you.</span></span>  
  
 <span data-ttu-id="23df6-107">プライベート証明書をインポートするには、BizTalk ホストを実行するユーザー アカウントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="23df6-107">To import private certificates, you must use the user accounts under which the BizTalk Hosts run.</span></span>  
  
### <a name="to-import-a-public-key-certificate"></a><span data-ttu-id="23df6-108">公開キー証明書をインポートするには</span><span class="sxs-lookup"><span data-stu-id="23df6-108">To import a public-key certificate</span></span>  
  
1. <span data-ttu-id="23df6-109">公開キー (.cer) 証明書が証明書のコピー先サーバーのハード ディスク上の場所にファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="23df6-109">Copy the public-key (.cer) certificate file to a location on the hard disk of the server to which you are copying certificates.</span></span>  
  
2. <span data-ttu-id="23df6-110">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]、順にクリックします[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理コンソール**.</span><span class="sxs-lookup"><span data-stu-id="23df6-110">Click **Start**, point to **All Programs**, point to **Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], and then click [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **Management Console**.</span></span>  
  
3. <span data-ttu-id="23df6-111">[!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)]管理コンソールで、展開**証明書 (ローカル コンピューター)** します。</span><span class="sxs-lookup"><span data-stu-id="23df6-111">In the [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] Management Console, expand **Certificates (Local Computer)**.</span></span> <span data-ttu-id="23df6-112">ログイン ユーザー、コンピューター管理者のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="23df6-112">The logged-in user must have administrative permissions to the computer.</span></span>  
  
4. <span data-ttu-id="23df6-113">右クリック**その他のユーザー**、 をポイント**すべてのタスク**、 をクリックし、**インポート**します。</span><span class="sxs-lookup"><span data-stu-id="23df6-113">Right-click **Other People**, point to **All Tasks**, and then click **Import**.</span></span>  
  
5. <span data-ttu-id="23df6-114">**証明書のインポート ウィザードへようこそ**] ページで [**次**します。</span><span class="sxs-lookup"><span data-stu-id="23df6-114">On the **Certificate Import Wizard Welcome** page, click **Next**.</span></span>  
  
6. <span data-ttu-id="23df6-115">**インポートするファイル**] ページで [**参照**証明書ファイルを含むフォルダーを検索します。</span><span class="sxs-lookup"><span data-stu-id="23df6-115">On the **File to Import** page, click **Browse** and locate the folder that contains the certificate files.</span></span> <span data-ttu-id="23df6-116">クリックして、証明書をインポートするファイルを選択して**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="23df6-116">Select the file from which you want to import the certificate, and then click **Open**.</span></span>  
  
7. <span data-ttu-id="23df6-117">**証明書ストア**いずれかを選択 ページで、**証明書の種類に基づく証明書を自動的に選択**または**次のストアに証明書をすべてを配置**.</span><span class="sxs-lookup"><span data-stu-id="23df6-117">On the **Certificate store** page, select either **Automatically select the certificate based on the type of certificate** or **Place all certificates in the following store**.</span></span> <span data-ttu-id="23df6-118">選択した場合**次のストアに証明書をすべてを配置**、 をクリックして**参照**、証明書ストアを選択**OK**、順にクリックします**次へ**.</span><span class="sxs-lookup"><span data-stu-id="23df6-118">If you select **Place all certificates in the following store**, click **Browse**, select the certificate store, click **OK**, and then click **Next**.</span></span>  
  
8. <span data-ttu-id="23df6-119">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="23df6-119">Click **Finish**.</span></span>  
  
### <a name="to-import-a-private-key-certificate"></a><span data-ttu-id="23df6-120">秘密キー証明書をインポートするには</span><span class="sxs-lookup"><span data-stu-id="23df6-120">To import a private-key certificate</span></span>  
  
1. <span data-ttu-id="23df6-121">証明書のコピー先サーバーのハード ディスク上の場所にファイルの秘密キー (.pfx) 証明書のコピー。</span><span class="sxs-lookup"><span data-stu-id="23df6-121">Copy private-key (.pfx) certificate files to a location on the hard disk of the server to which you are copying certificates.</span></span>  
  
2. <span data-ttu-id="23df6-122">をクリックして**開始**、 をクリックして**実行**、型 **/user として実行:\<サービスをホスト\>mmc**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="23df6-122">Click **Start**, click **Run**, type **run as /user:\<host service\> mmc**, and then click **OK**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="23df6-123">\<*サービスをホスト*\>、インストールしたときに、ホスト サービスに対して自動的に選択されたサービスの名前を入力[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="23df6-123">For \<*host service*\>, type the name of the service that was automatically selected for the host service when you installed [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)].</span></span>  
  
3. <span data-ttu-id="23df6-124">パスワードを入力します\<*サービスをホスト*\>、し、キーを押します**Enter**します。</span><span class="sxs-lookup"><span data-stu-id="23df6-124">Type the password for \<*host service*\>, and then press **Enter**.</span></span>  
  
4. <span data-ttu-id="23df6-125">Microsoft 管理コンソールでの**ファイル** メニューのをクリックして**スナップインの追加と削除**します。</span><span class="sxs-lookup"><span data-stu-id="23df6-125">In Microsoft Management Console, on the **File** menu, click **Add/Remove Snap-in**.</span></span>  
  
5. <span data-ttu-id="23df6-126">[スナップインの追加と削除] ダイアログ ボックスで、**追加**します。</span><span class="sxs-lookup"><span data-stu-id="23df6-126">In the Add/Remove Snap-in dialog box, click **Add**.</span></span>  
  
6. <span data-ttu-id="23df6-127">スタンドアロン スナップインの追加 ダイアログ ボックスで、**証明書**、 をクリックして**追加**、 をクリックして**閉じる**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="23df6-127">In the Add Standalone Snap-in dialog box, select **Certificates**, click **Add**, click **Close**, and then click **OK**.</span></span>  
  
7. <span data-ttu-id="23df6-128">Microsoft 管理コンソールで **証明書 - 現在のユーザー**を右クリックして**個人**、 をポイント**すべてのタスク**、 をクリックし、**インポート**.</span><span class="sxs-lookup"><span data-stu-id="23df6-128">In Microsoft Management Console, expand **Certificates - Current User**, right-click **Personal**, point to **All Tasks**, and then click **Import**.</span></span>  
  
8. <span data-ttu-id="23df6-129">**証明書のインポート ウィザードへようこそ**] ページで [**次**します。</span><span class="sxs-lookup"><span data-stu-id="23df6-129">On the **Certificate Import Wizard Welcome** page, click **Next**.</span></span>  
  
9. <span data-ttu-id="23df6-130">**インポートするファイル**] ページで [**参照**をインポートする証明書を含む .pfx 証明書ファイルを含むフォルダーを検索します。</span><span class="sxs-lookup"><span data-stu-id="23df6-130">On the **File to Import** page, click **Browse** and locate the folder that contains the .pfx certificate file that contains the certificate that you want to import.</span></span> <span data-ttu-id="23df6-131">適切なファイルを選択し、クリックして**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="23df6-131">Select the appropriate file, and then click **Open**.</span></span>  
  
10. <span data-ttu-id="23df6-132">**パスワード**ページで、**パスワード**ボックスに、秘密キー ファイルのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="23df6-132">On the **Password** page, in the **Password** box, type the password for the private-key file.</span></span>  
  
11. <span data-ttu-id="23df6-133">選択**強力な秘密キーの保護を有効にする**または**キーをエクスポート可能としてマーク**、順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="23df6-133">Select **Enable strong private key protection** or **Mark this key as exportable**, and then click **Next**.</span></span>  
  
12. <span data-ttu-id="23df6-134">**証明書ストア**いずれかを選択 ページで、**証明書の種類に基づく証明書を自動的に選択**または**次のストアに証明書をすべてを配置**.</span><span class="sxs-lookup"><span data-stu-id="23df6-134">On the **Certificate store** page, select either **Automatically select the certificate based on the type of certificate** or **Place all certificates in the following store**.</span></span> <span data-ttu-id="23df6-135">選択した場合**次のストアに証明書をすべてを配置**、 をクリックして**参照**、ストアの選択**OK**、順にクリックします**次へ**。</span><span class="sxs-lookup"><span data-stu-id="23df6-135">If you select **Place all certificates in the following store**, click **Browse**, select the store, click **OK**, and then click **Next**.</span></span>  
  
13. <span data-ttu-id="23df6-136">**証明書のインポート ウィザードの完了**] ページで [**完了**します。</span><span class="sxs-lookup"><span data-stu-id="23df6-136">On the **Completing the Certificate Import Wizard** page, click **Finish**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23df6-137">参照</span><span class="sxs-lookup"><span data-stu-id="23df6-137">See Also</span></span>  
 <span data-ttu-id="23df6-138">[MMC を使用してインポートされた証明書を構成します。](../../adapters-and-accelerators/accelerator-rosettanet/configuring-certificates-imported-using-mmc.md) </span><span class="sxs-lookup"><span data-stu-id="23df6-138">[Configuring Certificates Imported Using MMC](../../adapters-and-accelerators/accelerator-rosettanet/configuring-certificates-imported-using-mmc.md) </span></span>  
 [<span data-ttu-id="23df6-139">CertWizard</span><span class="sxs-lookup"><span data-stu-id="23df6-139">CertWizard</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/certwizard.md)