---
title: 証明書のエクスポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- exporting certificates
- certificates, exporting
ms.assetid: edeeb300-19d6-44a8-b730-dcd15891cdf9
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00fb00a1b256be192ce591b2b11ec70ab9b9d398
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283726"
---
# <a name="exporting-certificates"></a><span data-ttu-id="6ac49-102">証明書のエクスポート</span><span class="sxs-lookup"><span data-stu-id="6ac49-102">Exporting Certificates</span></span>
<span data-ttu-id="6ac49-103">このトピックでは、証明書のエクスポート ウィザードを使用して証明書をエクスポートする方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="6ac49-103">This topic describes how to export a certificate by using the Certificate Export Wizard.</span></span> <span data-ttu-id="6ac49-104">このウィザードを使用すると、パブリック証明書またはプライベート証明書をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="6ac49-104">Use this wizard to export either a public certificate or a private certificate.</span></span>  
  
### <a name="to-export-a-partner-certificate"></a><span data-ttu-id="6ac49-105">パートナーの証明書をエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="6ac49-105">To export a partner certificate</span></span>  
  
1. <span data-ttu-id="6ac49-106">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]順にクリックします[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理コンソール**.</span><span class="sxs-lookup"><span data-stu-id="6ac49-106">Click **Start**, point to **All Programs**, point to **Microsoft**[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] and then click [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **Management Console**.</span></span>  
  
2. <span data-ttu-id="6ac49-107">展開**証明書 (ローカル コンピューター)**、展開**その他のユーザー**、 をクリックし、**証明書**します。</span><span class="sxs-lookup"><span data-stu-id="6ac49-107">Expand **Certificates (Local Computer)**, expand **Other People**, and then click **Certificates**.</span></span>  
  
3. <span data-ttu-id="6ac49-108">右側のウィンドウで、証明書の名前を右クリックして**すべてのタスク**、 をクリックし、**エクスポート**します。</span><span class="sxs-lookup"><span data-stu-id="6ac49-108">In the right pane, right-click the name of the certificate, point to **All Tasks**, and then click **Export**.</span></span>  
  
4. <span data-ttu-id="6ac49-109">**証明書のエクスポート ウィザードへようこそ**] ページで [**次**します。</span><span class="sxs-lookup"><span data-stu-id="6ac49-109">On the **Welcome to the Certificate Export Wizard** page, click **Next**.</span></span>  
  
5. <span data-ttu-id="6ac49-110">**エクスポート ファイルの形式** ページで、ファイルを使用する形式を選択します。</span><span class="sxs-lookup"><span data-stu-id="6ac49-110">On the **Export File Format** page, select the format that you want to use for the file.</span></span> <span data-ttu-id="6ac49-111">この形式は、DER encoded binary x.509 バイナリ エンコードされたファイルをエクスポートするまたは Base 64 エンコード ファイルをエクスポートする base-64 でエンコードされた x.509 のいずれかでは、通常します。</span><span class="sxs-lookup"><span data-stu-id="6ac49-111">This format is generally either DER encoded binary x.509 to export a binary-encoded file, or Base-64 encoded x.509 to export a Base-64 encoded file.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="6ac49-112">Base-64 で証明書をエンコードするには、UNIX サーバーの証明書を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="6ac49-112">Encoding a certificate in Base-64 lets you use the certificate on a UNIX server.</span></span>  
  
6. <span data-ttu-id="6ac49-113">**エクスポートするファイル** ページで **参照**、検索にファイルを保存するには、ファイルの名前を入力、 をクリックして**次へ**、順にクリックします**完了**.</span><span class="sxs-lookup"><span data-stu-id="6ac49-113">On the **File to Export** page, click **Browse**, locate where you want to store the file, type the name of the file, click **Next**, and then click **Finish**.</span></span>  
  
### <a name="to-export-the-home-organization-certificate"></a><span data-ttu-id="6ac49-114">ホーム組織証明書をエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="6ac49-114">To export the home organization certificate</span></span>  
  
1. <span data-ttu-id="6ac49-115">クリックして**開始**、 をクリックして**実行**、型**runas/user:\<サービスをホスト\>mmc**ここで、 \< *hostservice* \> Microsoft をインストールしたときにホスト サービスに関連するサービスの名前を指定[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]、 をクリックし、 **OK**で Microsoft 管理コンソール (MMC) を実行する、ホスト サービスのコンテキスト。</span><span class="sxs-lookup"><span data-stu-id="6ac49-115">Click **Start**, click **Run**, type **runas /user:\<host service\> mmc**, where \<*hostservice*\> is the name of the service that you associated with the host service when you installed Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)], and then click **OK** to run the Microsoft Management Console (MMC) in the context of the host service.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="6ac49-116">実行する、 **runas**コマンドをホーム組織証明書にアクセスするために必要なホスト サービスの id を前提としています。</span><span class="sxs-lookup"><span data-stu-id="6ac49-116">You run the **runas** command to assume the identity of the host service, which is required to access the home-organization certificate.</span></span>  
  
2. <span data-ttu-id="6ac49-117">展開**証明書 - 現在のユーザー**、展開**個人**、 をクリックし、**証明書**します。</span><span class="sxs-lookup"><span data-stu-id="6ac49-117">Expand **Certificates - Current User**, expand **Personal**, and then click **Certificates**.</span></span>  
  
3. <span data-ttu-id="6ac49-118">右側のウィンドウで、証明書の名前を右クリックして**すべてのタスク**、 をクリックし、**エクスポート**します。</span><span class="sxs-lookup"><span data-stu-id="6ac49-118">In the right pane, right-click the name of the certificate, point to **All Tasks**, and then click **Export**.</span></span>  
  
4. <span data-ttu-id="6ac49-119">**証明書のエクスポート ウィザードへようこそ**] ページで [**次**します。</span><span class="sxs-lookup"><span data-stu-id="6ac49-119">On the **Welcome to the Certificate Export Wizard** page, click **Next**.</span></span>  
  
5. <span data-ttu-id="6ac49-120">証明書の秘密キーに関連付けられている公開キーをエクスポートするのままに**秘密キーをエクスポートしません**選択します。</span><span class="sxs-lookup"><span data-stu-id="6ac49-120">To export the public key associated with the private key of a certificate, leave **No, do not export the private key** selected.</span></span> <span data-ttu-id="6ac49-121">秘密キーをエクスポートするには、次のように選択します。**はい、秘密キーをエクスポート**します。</span><span class="sxs-lookup"><span data-stu-id="6ac49-121">To export the private key, select **Yes, export the private key**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="6ac49-122">選択した場合**はい、秘密キーをエクスポート**パートナーには、生成されたファイルを送信しないことを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6ac49-122">If you select **Yes, export the private key**, it is highly recommended that you do not send the resulting file to a partner.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="6ac49-123">**はい、秘密キーをエクスポート**されませんを行った場合、秘密キー エクスポート可能な最初にインポートしたときにオプションを実行できなくなります。</span><span class="sxs-lookup"><span data-stu-id="6ac49-123">The **Yes, export the private key** option will not be available if you did not make the private key exportable when you first imported it.</span></span>  
  
6. <span data-ttu-id="6ac49-124">**エクスポート ファイルの形式** ページで、ファイルを使用する形式を選択します。</span><span class="sxs-lookup"><span data-stu-id="6ac49-124">On the **Export File Format** page, select the format that you want to use for the file.</span></span> <span data-ttu-id="6ac49-125">この形式は、DER encoded binary x.509 バイナリ エンコードされたファイルをエクスポートするまたは Base 64 エンコード ファイルをエクスポートする base-64 でエンコードされた x.509 のいずれかでは、通常します。</span><span class="sxs-lookup"><span data-stu-id="6ac49-125">This format is generally either DER encoded binary x.509 to export a binary-encoded file, or Base-64 encoded x.509 to export a Base-64 encoded file.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="6ac49-126">Base-64 で証明書をエンコードするには、UNIX サーバーの証明書を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="6ac49-126">Encoding a certificate in Base-64 lets you use the certificate on a UNIX server.</span></span>  
  
7. <span data-ttu-id="6ac49-127">**エクスポートするファイル** ページで **参照**、検索にファイルを保存するには、ファイルの名前を入力、 をクリックして**次へ**、順にクリックします**完了**.</span><span class="sxs-lookup"><span data-stu-id="6ac49-127">On the **File to Export** page, click **Browse**, locate where you want to store the file, type the name of the file, click **Next**, and then click **Finish**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ac49-128">参照</span><span class="sxs-lookup"><span data-stu-id="6ac49-128">See Also</span></span>  
 [<span data-ttu-id="6ac49-129">証明書の管理</span><span class="sxs-lookup"><span data-stu-id="6ac49-129">Managing Certificates</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/managing-certificates1.md)